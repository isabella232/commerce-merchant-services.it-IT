---
title: Sincronizzazione catalogo
description: Scopri come esportare i dati dei prodotti dal [!DNL Commerce] server a [!DNL Commerce Services] mantenere costantemente aggiornati i servizi.
exl-id: 19d29731-097c-4f5f-b8c0-12f9c91848ac
source-git-commit: 3931a8c2e19f0024017682b029451bf1670d94b1
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 0%

---

# Sincronizzazione catalogo

Adobe Commerce e Magenti Open Source utilizzano gli indici per compilare i dati del catalogo in tabelle. Il processo viene attivato automaticamente da [events](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html#events-that-trigger-full-reindexing) ad esempio una modifica al prezzo di un prodotto o al livello di inventario.

Il processo di sincronizzazione del catalogo viene eseguito ogni ora per consentire [!DNL Commerce] servizi per l’utilizzo dei dati di catalogo. La sincronizzazione del catalogo esporta i dati di prodotto dal [!DNL Commerce] server a [!DNL Commerce] servizi su base continuativa per mantenere i servizi aggiornati. Ad esempio: [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) richiede informazioni di catalogo correnti per restituire con precisione i consigli con nomi, prezzi e disponibilità corretti. È possibile utilizzare _Sincronizzazione catalogo_ dashboard per osservare e gestire il processo di sincronizzazione o [interfaccia a riga di comando](#resynccmdline) per attivare la sincronizzazione del catalogo e reindicizzare i dati del prodotto per consumo [!DNL Commerce] servizi.

>[!NOTE]
>
> Per utilizzare _Sincronizzazione catalogo_ dashboard o interfaccia a riga di comando, è necessario disporre di un [Chiave API e spazio dati SaaS configurato](saas.md).

## Accesso al dashboard di sincronizzazione catalogo

>[!NOTE]
>
> La _Sincronizzazione catalogo_ il dashboard è disponibile solo quando _Recommendations di prodotto_ i moduli sono installati e riflettono le proiezioni dei dati relative solo a tale funzione. Supporto per altri servizi commerce, ad esempio _Live Search_ e _Servizio catalogo_ sono pianificate per il futuro.

Per accedere al dashboard Sincronizzazione catalogo, seleziona **Sistema** > _Trasferimento dati_ > **Sincronizzazione catalogo**.

Con la **Sincronizzazione catalogo** dashboard puoi:

- Visualizza lo stato di sincronizzazione (**In corso**, **Completato**, **Non riuscito**)
- Visualizza il numero totale di prodotti sincronizzati, in caso di esito positivo
- Cerca i prodotti sincronizzati per visualizzarne lo stato corrente
- Cerca catalogo store per nome, SKU e così via
- Visualizzare i dettagli dei prodotti sincronizzati in JSON per diagnosticare una discrepanza di sincronizzazione
- Riavvia il processo di sincronizzazione

### Ultima sincronizzazione

Segnala uno stato di sincronizzazione di:

- **Completato** - Visualizza la data e l’ora di completamento della sincronizzazione e il numero di prodotti aggiornati
- **Non riuscito** - Visualizza la data e l&#39;ora del tentativo di sincronizzazione
- **In corso** - Visualizza la data e l&#39;ora dell&#39;ultima sincronizzazione riuscita

>[!NOTE]
>
> Il processo di sincronizzazione del catalogo viene eseguito automaticamente ogni ora. Tuttavia, se non visualizzi i prodotti sulla vetrina o se i prodotti non riflettono le modifiche recenti apportate, puoi risolvere [problemi di sincronizzazione del catalogo](#resolvesync).

### Prodotti sincronizzati

Visualizza il numero totale di prodotti sincronizzati dal tuo [!DNL Commerce] catalogo. Dopo la sincronizzazione iniziale, dovresti aspettarti che vengano sincronizzati solo i prodotti modificati.

## Resync {#resync}

Se è necessario avviare una risincronizzazione del catalogo prima che si verifichi la sincronizzazione pianificata oraria, è possibile forzare una risincronizzazione.

>[!NOTE]
>
> L&#39;imposizione di una risincronizzazione attiva una risincronizzazione dell&#39;intero catalogo dei prodotti, che può aumentare il carico sulle risorse hardware.

1. Da _Sincronizzazione catalogo_ dashboard, seleziona **Impostazioni**.

   La _Impostazioni di sincronizzazione del catalogo_ viene visualizzata la pagina .

1. In _Risincronizzazione dei dati_ sezione, fai clic su [!UICONTROL Resync].

   [!DNL Commerce] sincronizza il catalogo durante la prossima finestra di sincronizzazione pianificata. A seconda delle dimensioni del catalogo, questa operazione può richiedere molto tempo.


## Prodotti di catalogo sincronizzati

La **Prodotti di catalogo sincronizzati** nella tabella vengono visualizzate le informazioni seguenti.

| Campo | Descrizione |
|---|---|
| ID | Identificatore univoco del prodotto |
| Nome | Nome della vetrina del prodotto |
| Tipo | Identifica il tipo di prodotto, ad esempio semplice, configurabile, scaricabile e così via |
| Ultimo esportazione | Data dell’ultima esportazione del prodotto dal catalogo |
| Ultima modifica | Data dell’ultima modifica apportata al prodotto nel catalogo |
| SKU | Visualizza l&#39;unità di conservazione del prodotto |
| Prezzo | Prezzo del prodotto |
| Visibilità | L’impostazione di visibilità di un prodotto come definito nella [!DNL Commerce] catalogo |

## Risolvere i problemi di sincronizzazione del catalogo {#resolvesync}

Quando si attiva una risincronizzazione dei dati, l’aggiornamento dei dati può richiedere fino a un’ora e può riflettersi nei componenti dell’interfaccia utente, come le unità dei consigli. Tuttavia, se dopo un&#39;ora di attesa noti ancora discrepanze tra il catalogo e ciò che appare sulla vetrina, o se la sincronizzazione del catalogo non è riuscita, consulta quanto segue:

### Discordanza dei dati

1. Visualizza la visualizzazione dettagliata del prodotto in questione nei risultati della ricerca.
1. Copia l’output JSON e verifica che il contenuto corrisponda a quello presente nel [!DNL Commerce] catalogo.
1. Se il contenuto non corrisponde, apporta una modifica minore al prodotto nel catalogo, ad esempio l’aggiunta di uno spazio o di un punto.
1. Attendi una risincronizzazione o [attivare la risincronizzazione manuale](#resync).

### Sincronizzazione non in esecuzione

Se la sincronizzazione non è in esecuzione su una pianificazione o non viene sincronizzato nulla, vedi [KnowledgeBase](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/troubleshoot-product-recommendations-module-in-magento-commerce.html).

### Sincronizzazione non riuscita

Se la sincronizzazione del catalogo ha uno stato di **Non riuscito**, invia un [biglietto di supporto](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket).

## Interfaccia della riga di comando {#resynccmdline}

La `saas:resync` fa parte del `magento/saas-export` pacchetto. Puoi installare questo pacchetto utilizzando uno dei [!DNL Commerce Services] prodotti, quali [[!DNL Product Recommendations]](/help/product-recommendations/install-configure.md) o [[!DNL Live Search]](/help/live-search/install.md).

>[!NOTE]
>
> Quando esegui una sincronizzazione dati per la prima volta, è importante eseguire il `productattributes` feed, seguito da `productoverrides`, prima di eseguire `products` feed.

Opzioni di comando:

```bash
bin/magento saas:resync --feed <feed name> [no-reindex]
```

Nella tabella seguente viene descritta la `saas:resync` parametri e descrizioni.

| Parametro | Descrizione | Obbligatorio |
|---| ---| ---|
| `feed` | Specifica l&#39;entità da risincronizzare, ad esempio `products` | Sì |
| `no-reindex` | Invia nuovamente i dati del catalogo esistenti a [!DNL Commerce Services] senza reindicizzazione. Se questo parametro non viene specificato, il comando esegue una reindicizzazione completa prima della sincronizzazione dei dati. | No |

Il nome del feed può essere uno dei seguenti:

- `products`— Prodotti nel catalogo
- `categories`— Categorie nel catalogo
- `variants`— Variazioni di prodotto di un prodotto configurabile, quali colore e dimensioni
- `productattributes`— Attributi del prodotto quali `activity`, `gender`, `tops`, `bottoms`e così via
- `productoverrides`— Regole di determinazione dei prezzi e visibilità del catalogo specifiche per i clienti, ad esempio quelle basate sulle autorizzazioni per le categorie

Quando si attiva una risincronizzazione dei dati dalla riga di comando, l’aggiornamento dei dati potrebbe richiedere fino a un’ora.

Se utilizzi [Indicizzazione dei prezzi SaaS](../price-index/index.md) e per eseguire nuovamente la sincronizzazione, esegui il seguente comando:

```bash
bin/magento saas:resync --feed=scopesCustomerGroup
bin/magento saas:resync --feed=scopesWebsite
bin/magento saas:resync --feed=prices
```

### Esempi

L’esempio seguente reindicizza i dati del prodotto dal [!DNL Commerce] catalogo e risincronizzazione in Commerce Services:

```bash
bin/magento saas:resync --feed products
```

Se non desideri eseguire un reindice completo dei prodotti, puoi invece sincronizzare i dati del prodotto già generati:

```bash
bin/magento saas:resync --feed products --no-reindex
```
