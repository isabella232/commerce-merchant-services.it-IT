---
title: Sincronizzazione catalogo
description: Scopri come esportare i dati di prodotto da [!DNL Commerce] server a [!DNL Commerce Services] su base continuativa per mantenere aggiornati i servizi.
exl-id: 19d29731-097c-4f5f-b8c0-12f9c91848ac
feature: Catalogs, Data Import/Export, Catalog Service
source-git-commit: d803cd9c78ac8c5529eadf39f361d7e46045359e
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 0%

---

# Sincronizzazione catalogo

Adobe Commerce e Magenti Open Source utilizzano gli indicizzatori per compilare i dati del catalogo nelle tabelle. Il processo viene attivato automaticamente da [Eventi](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html#events-that-trigger-full-reindexing) ad esempio una modifica al prezzo di un prodotto o al livello di magazzino.

Il processo di sincronizzazione del catalogo viene eseguito ogni ora per consentire [!DNL Commerce] servizi per utilizzare i dati del catalogo. La sincronizzazione del catalogo esporta i dati di prodotto da [!DNL Commerce] server a [!DNL Commerce] servizi su base continuativa per mantenere aggiornati i servizi. Ad esempio: [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) necessita delle informazioni aggiornate sul catalogo per restituire in modo accurato i consigli con nomi, prezzi e disponibilità corretti. È possibile utilizzare _Sincronizzazione catalogo_ dashboard per osservare e gestire il processo di sincronizzazione o [interfaccia della riga di comando](#resynccmdline) per attivare la sincronizzazione del catalogo e reindicizzare i dati di prodotto per l&#39;utilizzo da parte di [!DNL Commerce] servizi.

>[!NOTE]
>
> Per utilizzare _Sincronizzazione catalogo_ o l&#39;interfaccia della riga di comando, è necessario disporre di un [Chiave API e spazio dati SaaS configurati](saas.md).

## Accesso al dashboard di sincronizzazione del catalogo

>[!NOTE]
>
> Il _Sincronizzazione catalogo_ è disponibile solo quando _Recommendations del prodotto_ vengono installati e riflettono le proiezioni di dati relative solo a tale funzione. Supporto per altri servizi Commerce come _Live Search_ e _Servizio catalogo_ sono pianificate per il futuro.

Per accedere al dashboard Sincronizzazione catalogo, seleziona **Sistema** > _Trasferimento dati_ > **Sincronizzazione catalogo**.

Con il **Sincronizzazione catalogo** dashboard è possibile:

- Visualizza stato di sincronizzazione (**In corso**, **Completato**, **Non riuscito**)
- Visualizza il numero totale di prodotti sincronizzati, in caso di esito positivo
- Cerca i prodotti sincronizzati per visualizzarne lo stato corrente
- Cerca nel catalogo del negozio per nome, SKU e così via
- Visualizza i dettagli del prodotto sincronizzato in JSON per diagnosticare una discrepanza di sincronizzazione
- Riavvia il processo di sincronizzazione

### Ultima sincronizzazione

Segnala uno stato di sincronizzazione di:

- **Completato** - Visualizza la data e l&#39;ora di completamento della sincronizzazione e il numero di prodotti aggiornati
- **Non riuscito** - Visualizza la data e l&#39;ora del tentativo di sincronizzazione
- **In corso** - Visualizza la data e l&#39;ora dell&#39;ultima sincronizzazione riuscita

>[!NOTE]
>
> Il processo di sincronizzazione del catalogo viene eseguito automaticamente ogni ora. Tuttavia, se non vedi i prodotti nella vetrina o se i prodotti non riflettono le modifiche recenti apportate, puoi risolvere [problemi di sincronizzazione catalogo](#resolvesync).

### Prodotti sincronizzati

Visualizza il numero totale di prodotti sincronizzati dal [!DNL Commerce] catalogo. Dopo la sincronizzazione iniziale, è possibile che vengano sincronizzati solo i prodotti modificati.

## Risincronizza {#resync}

Se è necessario avviare una risincronizzazione del catalogo prima che venga eseguita la sincronizzazione oraria pianificata, è possibile forzare una risincronizzazione.

>[!NOTE]
>
> L&#39;imposizione di una risincronizzazione attiva una risincronizzazione dell&#39;intero catalogo prodotti, che può aumentare il carico sulle risorse hardware.

1. Dalla sezione _Sincronizzazione catalogo_ dashboard, seleziona **Impostazioni**.

   Il _Impostazioni sincronizzazione catalogo_ viene visualizzata.

1. In _Risincronizza dati_ , fare clic su [!UICONTROL Resync].

   [!DNL Commerce] sincronizza il catalogo durante la successiva finestra di sincronizzazione pianificata. A seconda delle dimensioni del catalogo, questa operazione può richiedere molto tempo.


## Prodotti catalogo sincronizzati

Il **Prodotti catalogo sincronizzati** nella tabella vengono visualizzate le informazioni seguenti.

| Campo | Descrizione |
|---|---|
| ID | Identificatore univoco del prodotto |
| Nome | Nome vetrina del prodotto |
| Tipo | Identifica il tipo di prodotto, ad esempio semplice, configurabile, scaricabile e così via |
| Ultima esportazione | Data dell’ultima esportazione del prodotto dal catalogo |
| Ultima modifica | Data dell’ultima modifica del prodotto nel catalogo |
| SKU | Visualizza l&#39;unità di gestione delle scorte per il prodotto |
| Prezzo | Prezzo del prodotto |
| Visibilità | L’impostazione di visibilità di un prodotto, definita nella sezione [!DNL Commerce] catalogo |

## Risolvi problemi di sincronizzazione catalogo {#resolvesync}

Quando attivi una risincronizzazione dei dati, l’aggiornamento dei dati può richiedere fino a un’ora e può essere incluso nei componenti dell’interfaccia utente, ad esempio le unità per i consigli. Tuttavia, se dopo un’ora di attesa noti ancora delle discrepanze tra il catalogo e ciò che appare sulla vetrina, o se la sincronizzazione del catalogo non è riuscita, consulta quanto segue:

### Discrepanza dei dati

1. Visualizzare la visualizzazione dettagliata del prodotto in questione nei risultati della ricerca.
1. Copia l’output JSON e verifica che il contenuto corrisponda a quello presente in [!DNL Commerce] catalogo.
1. Se il contenuto non corrisponde, apporta una piccola modifica al prodotto nel catalogo, ad esempio aggiungendo uno spazio o un punto.
1. Attendere la risincronizzazione o [attivare una risincronizzazione manuale](#resync).

### Sincronizzazione non in esecuzione

Se la sincronizzazione non è in esecuzione su una pianificazione o non è stato sincronizzato nulla, vedere [KnowledgeBase](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/troubleshoot-product-recommendations-module-in-magento-commerce.html).

### Sincronizzazione non riuscita

Se lo stato della sincronizzazione del catalogo è **Non riuscito**, invia una [ticket di supporto](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket).

## Interfaccia della riga di comando {#resynccmdline}

Il `saas:resync` il comando fa parte del `magento/saas-export` pacchetto. È possibile installare questo pacchetto utilizzando uno dei [!DNL Commerce Services] prodotti, come [[!DNL Product Recommendations]](/help/product-recommendations/install-configure.md) o [[!DNL Live Search]](/help/live-search/install.md).

>[!NOTE]
>
> Quando si esegue una sincronizzazione dati per la prima volta, è importante eseguire `productattributes` primo feed, seguito da `productoverrides`, prima di eseguire `products` feed.

Opzioni comando:

```bash
bin/magento saas:resync --feed <feed name> [no-reindex]
```

La tabella seguente descrive `saas:resync` parametri e descrizioni.

| Parametro | Descrizione | Obbligatorio |
|---| ---| ---|
| `feed` | Specifica l&#39;entità da risincronizzare, ad esempio `products` | Sì |
| `no-reindex` | Invia nuovamente i dati del catalogo esistenti a [!DNL Commerce Services] senza reindicizzazione. Se questo parametro non è specificato, il comando esegue una reindicizzazione completa prima di sincronizzare i dati. | No |

Il nome del feed può essere uno dei seguenti:

- `products`— Prodotti nel catalogo
- `categories`— Categorie nel catalogo
- `variants`— varianti di prodotto di un prodotto configurabile, ad esempio colore e dimensioni
- `productattributes`— Attributi del prodotto come `activity`, `gender`, `tops`, `bottoms`, e così via
- `productoverrides`regole specifiche per il cliente per la visibilità dei prezzi e dei cataloghi, ad esempio quelle basate sulle autorizzazioni per le categorie

Quando si attiva la risincronizzazione dei dati dalla riga di comando, l&#39;aggiornamento dei dati potrebbe richiedere fino a un&#39;ora.

Se sta usando [Indicizzazione dei prezzi SaaS](../price-index/index.md) e deve essere risincronizzato, esegui il seguente comando:

```bash
bin/magento saas:resync --feed=scopesCustomerGroup
bin/magento saas:resync --feed=scopesWebsite
bin/magento saas:resync --feed=prices
```

### Esempi

L’esempio seguente reindicizza i dati di prodotto dalla sezione [!DNL Commerce] e lo risincronizza con Commerce Services:

```bash
bin/magento saas:resync --feed products
```

Se non desideri eseguire una reindicizzazione completa dei prodotti, puoi invece sincronizzare i dati del prodotto già generati:

```bash
bin/magento saas:resync --feed products --no-reindex
```
