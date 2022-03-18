---
title: Installa Live Search
description: Scopri come installare, aggiornare e disinstallare Live Search da Adobe Commerce.
exl-id: aa251bb0-d52c-4cff-bccb-76a08ae2a3b2
source-git-commit: 19f0c987ab6b43b6fac1cad266b5fd47a7168e73
workflow-type: tm+mt
source-wordcount: '1490'
ht-degree: 0%

---

# Installa [!DNL Live Search]

[!DNL Live Search] è un insieme autonomo [pacchetti](#live-search-packages) che sostituisce le funzionalità di ricerca standard di Magenti Open Source e Adobe Commerce. La [!DNL Live Search] Il modulo viene installato dalla riga di comando del server e si connette all’installazione di Adobe Commerce come [servizio](https://docs.magento.com/user-guide/system/saas.html). Al termine del processo, [!DNL Live Search] appare sul *Marketing* menu sotto *SEO e ricerca* in [!DNL Commerce] Amministratore.

Sul lato Adobe Commerce sono inclusi l’hosting dell’amministratore della ricerca, la sincronizzazione dei dati del catalogo e l’esecuzione del servizio di query.

![Diagramma dell’architettura di Live Search](assets/architecture-diagram.svg)

Dopo la [!DNL Live Search] è installato e configurato il modulo (con moduli di catalogo come dipendenze), [!DNL Commerce] inizia a condividere i dati di ricerca e catalogo con i servizi SaaS. A questo punto, gli utenti amministratori possono impostare, personalizzare e gestire facet di ricerca, sinonimi e regole di merchandising.

Questo argomento fornisce istruzioni su come effettuare le seguenti operazioni:

* [Installa [!DNL Live Search]](#before-you-begin) (Metodi 1 e 2)
* [Aggiorna [!DNL Live Search]](#update)
* [Disinstalla [!DNL Live Search]](#uninstall)

## Requisiti {#requirements}

* [Adobe Commerce](https://magento.com/products/magento-commerce) 2.4.x
* PHP 7.3 / 7.4
* [!DNL Composer]

### Piattaforme supportate

* Adobe Commerce su prem (EE) : 2.4.x
* Adobe Commerce on Cloud (ECE) : 2.4.x

## Limiti e soglie

Al momento, l’API di ricerca categorie/categoria Live Search ha i seguenti limiti supportati e limiti statici:

### Indicizzazione

* Indici fino a 300 attributi di prodotto per visualizzazione store
* Indici solo prodotti dal database Adobe Commerce
* Non indicizza le pagine CMS

### Funzionalità

* Vetrina [Ricerca avanzata (modulo)](https://docs.magento.com/user-guide/catalog/search-advanced.html) modulo
* [Gruppi di clienti](https://docs.magento.com/user-guide/customers/customer-groups.html)
* [Gruppi di prezzi personalizzati](https://docs.magento.com/user-guide/catalog/product-price-group.html)
* Più posizioni di inventario utilizzate da [MCOM](https://docs.magento.com/user-guide/mcom.html) o altre estensioni OMS
* [Funzionalità B2B integrate](https://business.adobe.com/products/magento/b2b-ecommerce.html)

### Query

* Live Search non ha accesso all’intera tassonomia della struttura delle categorie, il che rende alcuni scenari di ricerca di navigazione a più livelli oltre la sua portata.
* Live Search utilizza un endpoint GraphQL univoco per le query per supportare funzioni quali il faceting intelligente e la ricerca come-tu-type. Anche se simile al [API GraphQL di Magento](https://devdocs.magento.com/guides/v2.4/graphql), esistono alcune differenze e alcuni campi potrebbero non essere completamente compatibili al momento.

### Progressive Web Application (PWA)

* Live Search non supporta [PWA](https://developer.adobe.com/commerce/pwa-studio/) in questo momento.

## Prima di iniziare {#before-you-begin}

Effettua le seguenti operazioni:

1. Conferma che [lavori cron](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html) e [indicizzatori](https://docs.magento.com/user-guide/system/index-management.html) stanno correndo.

1. Scegli il metodo di onboarding che soddisfa le tue esigenze e segui le istruzioni.

   * [Metodo 1](#method-1): Installazione senza [!DNL Elasticsearch]
   * [Metodo 2](#method-2): Installa con [!DNL Elasticsearch] (Nessun tempo di inattività)

   >[!TIP]
   >
   >Per immettere le istruzioni sulla riga di comando, posiziona il puntatore del mouse sull&#39;estrema destra della casella di codice e fai clic sul pulsante [!UICONTROL **Copia**] link. Quindi, incollalo nella riga di comando. Se non hai esperienza di lavoro dalla riga di comando, chiedi assistenza al tuo integratore di sistema o sviluppatore.

## Metodo 1: Installazione senza Elasticsearch {#method-1}

Questo metodo di onboarding è consigliato durante l&#39;installazione [!DNL Live Search] a:

* Nuovo [!DNL Commerce] installazione
* Ambiente di staging

In questo scenario, le operazioni di vetrina vengono interrotte mentre il [!DNL Live Search] il servizio indicizza tutti i prodotti del catalogo. Durante l&#39;installazione, [!DNL Live Search] i moduli sono abilitati e [!DNL Elasticsearch] i moduli sono disabilitati.

1. Installa Adobe Commerce 2.4.x senza [!DNL Live Search].

1. Per scaricare i `live-search` esegui quanto segue dalla riga di comando:

   ```bash
   composer require magento/DNL live-search
   ```

   Per ulteriori informazioni, consulta l’elenco di [!DNL Live Search] [dipendenze](#dependencies) catturati da [!DNL Composer].

1. Esegui i seguenti comandi per disabilitare [!DNL Elasticsearch] e i relativi moduli, e installare [!DNL Live Search]:

   ```bash
   bin/magento module:disable Magento_Elasticsearch Magento_Elasticsearch6 Magento_Elasticsearch7 Magento_ElasticsearchCatalogPermissions Magento_AdvancedSearch  Magento_InventoryElasticsearch
   ```

   ```bash
   bin/magento setup:upgrade
   ```

   >[!WARNING]
   >
   > Mentre i dati sono indicizzati e sincronizzati, le operazioni di ricerca e ricerca per categorie non sono disponibili nella vetrina. A seconda delle dimensioni del catalogo, il processo può richiedere almeno un&#39;ora dal `cron` esegue per sincronizzare i dati con [!DNL Live Search] servizi.

1. Verifica quanto segue [indicizzatori](https://docs.magento.com/user-guide/system/index-management.html) sono impostati su `Update by Schedule`:

   * Feed di prodotto
   * Feed variante di prodotto
   * Feed attributi del catalogo

1. Configura le [Chiavi API](#configure-api-keys) a [sincronizzare](#synchronize-catalog-data) i dati del catalogo in [!DNL Live Search] servizi.

1. Per rendere i facet disponibili come filtri nella vetrina, aggiungi [facet](https://docs.magento.com/user-guide/live-search/facets-add.html) è necessario, secondo il [requisiti](https://docs.magento.com/user-guide/live-search/facets.html).

   Dovresti essere in grado di aggiungere facet dopo `cron` esegue i feed degli attributi ed esporta i metadati degli attributi.

1. Attendi almeno un&#39;ora dopo `cron` esegue per sincronizzare i dati. Allora, [verify](#verify-export) che i dati sono stati esportati.

1. [Test](#test-the-connection) la connessione dalla vetrina.

## Metodo 2: Installa con Elasticsearch {#method-2}

Questo metodo di onboarding è consigliato durante l&#39;installazione [!DNL Live Search] a:

* Una produzione esistente [!DNL Commerce] installazione

In questo scenario, [!DNL Elasticsearch] gestisce temporaneamente le richieste di ricerca dalla vetrina mentre il [!DNL Live Search] il servizio indicizza tutti i prodotti in background, senza interruzioni alle normali operazioni di vetrina. [!DNL Elasticsearch] è disabilitato e [!DNL Live Search] abilitati dopo che tutti i dati del catalogo sono indicizzati e sincronizzati.

1. Per scaricare i `live-search` esegui quanto segue dalla riga di comando:

   ```bash
   composer require magento/live-search
   ```

   Per ulteriori informazioni, consulta l’elenco di [!DNL Live Search] [dipendenze](#live-search-dependencies) catturati da [!DNL Composer].

1. Esegui il comando seguente per disattivare temporaneamente il [!DNL Live Search] moduli che distribuiscono i risultati della ricerca in vetrina.

   ```bash
   bin/magento module:disable Magento_LiveSearchAdapter Magento_LiveSearchStorefrontPopover
   ```

   ```bash
   bin/magento setup:upgrade
   ```

   [!DNL Elasticsearch] continua a gestire le richieste di ricerca dalla vetrina mentre il [!DNL Live Search] sincronizza i dati del catalogo e indicizza i prodotti in background.

1. Verifica quanto segue [indicizzatori](https://docs.magento.com/user-guide/system/index-management.html) sono impostati su `Update by Schedule`:

   * Feed di prodotto
   * Feed variante di prodotto
   * Feed attributi del catalogo

1. Configura le [Chiavi API](#configure-api-keys) a [sincronizzare](#synchronize-catalog-data) i dati del catalogo in [!DNL Live Search] servizi.

1. Per rendere i facet disponibili come filtri nella vetrina, aggiungi [facet](https://docs.magento.com/user-guide/live-search/facets-add.html) è necessario, secondo il [requisiti](https://docs.magento.com/user-guide/live-search/facets.html).

   Dovresti essere in grado di aggiungere facet dopo `cron` esegue i feed di prodotto e attributo ed esporta i metadati degli attributi in [!DNL Live Search] servizi.

1. Attendi almeno un’ora per l’indicizzazione e la sincronizzazione dei dati. Quindi, utilizza il [Campo giochi GraphQL](https://devdocs.magento.com/live-search/graphql-support.html) con la query predefinita per verificare quanto segue:

   * Il conteggio dei prodotti restituito è simile a quello previsto per la visualizzazione store
   * Vengono restituiti i facet

1. Esegui i seguenti comandi per disabilitare [!DNL Elasticsearch] moduli, abilita [!DNL Live Search] moduli ed esecuzione `setup`:

   ```bash
   bin/magento module:enable Magento_LiveSearchAdapter Magento_LiveSearchStorefrontPopover
   ```

   ```bash
   bin/magento module:disable Magento_Elasticsearch Magento_Elasticsearch6 Magento_Elasticsearch7 Magento_ElasticsearchCatalogPermissions Magento_AdvancedSearch Magento_InventoryElasticsearch
   ```

   ```bash
   bin/magento setup:upgrade
   ```

1. [Test](#test-the-connection) la connessione dalla vetrina.

## Configurare le chiavi API {#configure-api-keys}

Per connettersi è necessaria la chiave API di Adobe Commerce e la relativa chiave privata associata [!DNL Live Search] a un’installazione di Adobe Commerce. La chiave API viene generata e mantenuta nell’account della [!DNL Commerce] titolare della licenza, che può condividerlo con lo sviluppatore o con SI. Lo sviluppatore può quindi creare e gestire gli spazi dati SaaS per conto del titolare della licenza.

### Titolare della licenza Adobe Commerce

Per generare una chiave API e una chiave privata, fai riferimento a [Connettore Commerce Services](https://docs.magento.com/user-guide/system/saas.html).

### Sviluppatore Adobe Commerce o SI

Lo sviluppatore o l’SI configura lo spazio dati SaaS come descritto nella sezione Commerce Services della configurazione. Commerce Services diventa disponibile nella barra laterale Configurazione amministratore quando viene installato un modulo SaaS .

## Sincronizzazione dei dati del catalogo {#synchronize-catalog-data}

[!DNL Live Search] richiede dati di prodotto sincronizzati per le operazioni di ricerca e dati di attributi sincronizzati per configurare i facet. La sincronizzazione iniziale tra il catalogo dei prodotti e il servizio catalogo inizia quando [!DNL Live Search] è collegato per la prima volta. A seconda del metodo di installazione e delle dimensioni del catalogo, possono essere necessarie fino a otto ore per l’esportazione e l’indicizzazione dei dati da parte di [!DNL Live Search]. L’elenco dei dati sincronizzati e condivisi con il servizio catalogo si trova nello schema, definito in:

`vendor/magento/module-catalog-data-exporter/etc/et_schema.xml`

### Verifica esportazione {#verify-export}

Per verificare che i dati del catalogo siano stati esportati dall’istanza di Adobe Commerce e siano sincronizzati per [!DNL Live Search], cerca le voci nelle tabelle seguenti:

* `catalog_data_exporter_products`
* `catalog_data_exporter_product_attributes`

Per ulteriore assistenza, consulta [[!DNL Live Search] catalogo non sincronizzato](https://support.magento.com/hc/en-us/articles/4405637804301-Live-search-catalog-not-synchronized) nella Knowledge Base del supporto.

### Aggiornamenti futuri dei prodotti

Dopo la sincronizzazione iniziale, possono essere necessari fino a quindici minuti perché gli aggiornamenti incrementali dei prodotti siano disponibili per la ricerca in vetrina. Per ulteriori informazioni, vai a [Aggiornamenti dei prodotti in streaming](https://devdocs.magento.com/live-search/indexing.html).

## Verificare la connessione {#test-connection}

Nella vetrina, verifica quanto segue:

* La [!UICONTROL Search] box restituisce correttamente i risultati
* Il browser delle categorie restituisce correttamente i risultati
* I facet sono disponibili come filtri nelle pagine dei risultati di ricerca

Se tutto funziona correttamente, congratulazioni! [!DNL Live Search] è installato, collegato e pronto per l&#39;uso.

Se riscontri problemi nella vetrina, controlla la `var/log/system.log` per errori o errori di comunicazione API sul lato servizi.

## Aggiornamento [!DNL Live Search] {#update}

Per aggiornare [!DNL Live Search], esegui quanto segue dalla riga di comando:

```bash
composer update magento/live-search --with-dependencies
```

Per eseguire l’aggiornamento a una versione principale, ad esempio da 1.0 a 2.0, modifica la directory principale del progetto [!DNL Composer] `.json` file come segue:

1. Apri la radice `composer.json` file e cerca `magento/live-search`.

1. In `require` aggiorna il numero di versione come segue:

   ```json
   "require": {
      ...
      "magento/live-search": "^2.0",
      ...
    }
   ```

1. **Salva** `composer.json`. Esegui quindi quanto segue dalla riga di comando:

   ```bash
   composer update magento/live-search –-with-dependencies
   ```

## Disinstallazione [!DNL Live Search] {#uninstall}

Per disinstallare [!DNL Live Search], fare riferimento a [Disinstallare i moduli](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-uninstall-mods.html).

## [!DNL Live Search] pacchetti {#packages}

| Pacchetto | Descrizione |
|--- |--- |
| `module-live-search` | Consente agli esercenti di configurare le impostazioni di ricerca per faceting, sinonimi, regole di query, ecc. e fornisce l’accesso a un parco giochi GraphQL di sola lettura per testare le query dall’amministratore. |
| `module-live-search-adapter` | Invia richieste di ricerca dalla vetrina al [!DNL Live Search] ed esegue il rendering dei risultati nella vetrina. <br />- Navigazione tra categorie - Routes richieste dalla vetrina [navigazione superiore](https://docs.magento.com/user-guide/catalog/navigation-top.html) al servizio di ricerca.<br />- Ricerca globale - Richieste di percorsi da [ricerca rapida](https://docs.magento.com/user-guide/catalog/search-quick.html) in alto a destra della vetrina [!DNL Live Search] servizio. |
| `module-live-search-storefront-popover` | Il puntatore &quot;Ricerca durante la digitazione&quot; sostituisce la ricerca rapida standard e restituisce suggerimenti di prodotto dinamici e miniature dei risultati di ricerca principali. |

## [!DNL Live Search] dipendenze {#dependencies}

I seguenti [!DNL Live Search] le dipendenze vengono acquisite da [!DNL Composer]:

| Dipendenza | Descrizione |
|--- |--- |
| Moduli di esportazione | I seguenti moduli raccolgono e sincronizzano i dati del catalogo:<br />`saas-export`<br />`module-bundle-product-exporter`<br />`module-catalog-data-exporter`<br />`module-catalog-inventory-data-exporter`<br />`module-catalog-url-rewrite-data-exporter`<br />`module-configurable-product-data-exporter`<br />`module-data-exporter`<br />`module-parent-product-data-exporter` |
| `services-connector` | Obbligatorio per configurare la connessione a Commerce Services. |
| `module-services-id` | Obbligatorio per configurare la connessione a Commerce Services. |
