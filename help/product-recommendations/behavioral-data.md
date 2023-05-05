---
title: Dati comportamentali
description: Scopri i dati comportamentali e quando puoi iniziare a usarli.
exl-id: d68a97b9-1497-4603-a72c-4aaaf6e048cb
source-git-commit: 840b091638aedd3f6ac097a010d035eff997ffe2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Dati comportamentali

Alcuni tipi di consigli utilizzano i dati comportamentali degli acquirenti per addestrare i modelli di apprendimento automatico per generare consigli personalizzati. Altri tipi di consigli utilizzano solo dati di catalogo e non utilizzano dati comportamentali. Per iniziare rapidamente, potete utilizzare i seguenti tipi di consigli solo catalogo:

- `More like this`
- `Visual similarity`

Quindi quando puoi iniziare a utilizzare tipi di consigli che utilizzano dati comportamentali? Dipende. Viene indicato come _Avvio a freddo_ problema.

La _Avvio a freddo_ il problema è una misura di quanto tempo un modello deve addestrare prima che possa essere considerato di alta qualità. Nei consigli sui prodotti, si traduce in attesa che Adobe Sensei formi i suoi modelli di apprendimento automatico prima di distribuire le unità di raccomandazione sul sito. Maggiore è il numero di dati disponibili per questi modelli, maggiore è l&#39;accuratezza e l&#39;utilità delle raccomandazioni. La raccolta di questi dati richiede tempo e varia in base al volume del traffico. Poiché questi dati possono essere raccolti solo su un sito di produzione, è nel tuo interesse distribuire la raccolta dati il prima possibile. Puoi farlo tramite [installazione e configurazione](install-configure.md) la `magento/production-recommendations` modulo .

La tabella seguente fornisce alcune indicazioni generali sul tempo necessario per raccogliere dati sufficienti per ciascun tipo di raccomandazione:

| Tipo di raccomandazione | Tempo di formazione | Note |
|---|---|---|
| Basato sulla popolarità (`Most viewed`, `Most purchased`, `Most added to cart`) | Varie | Dipende dal volume degli eventi: le visualizzazioni sono più comuni e quindi imparano più rapidamente; poi si aggiunge al carrello, poi acquista |
| `Viewed this, viewed that` | Richiede più formazione | Le visualizzazioni dei prodotti sono decisamente alte in volume |
| `Viewed this, bought that`, `Bought this, bought that` | Richiede il massimo livello di formazione | Gli eventi di acquisto sono gli eventi più rari sul sito di e-commerce, in particolare rispetto alle visualizzazioni di prodotto |
| `Trending` | Richiede tre giorni di dati per stabilire una linea di base di popolarità | La tendenza è una misura del recente slancio nella popolarità di un prodotto rispetto alla sua linea di base di popolarità. Il punteggio di tendenza di un prodotto viene calcolato utilizzando un set in primo piano (popolarità recente su 24 ore) e un set di sfondo (previsione di popolarità su 72 ore). Se un articolo è diventato molto più popolare nelle ultime 24 ore rispetto alla sua popolarità di base, allora riceve un punteggio di tendenza elevato. Ogni prodotto ha questo punteggio, e quelli più alti in qualsiasi momento comprendono il set di prodotti di tendenza più importanti. |

Altre variabili che possono influire sul tempo necessario alla formazione:

- Un volume di traffico più elevato contribuisce a un apprendimento più rapido
- Alcuni tipi di consigli si allenano più velocemente di altri
- Adobe Commerce ricalcola i dati comportamentali ogni quattro ore. Recommendations diventa più preciso per quanto tempo vengono utilizzati sul sito.

Per visualizzare l&#39;avanzamento del training di ciascun tipo di raccomandazione, l&#39; [creare un consiglio](create.md) In questa pagina vengono visualizzati gli indicatori di preparazione.

Mentre i dati vengono raccolti sui modelli di produzione e apprendimento automatico vengono addestrati, è possibile implementare [altre attività](implementation-workflow.md) necessario per distribuire consigli alla vetrina. Al termine dei test e della configurazione dei consigli, i modelli di apprendimento automatico hanno raccolto e calcolato dati sufficienti per generare consigli rilevanti, consentendo così di distribuire i consigli sulla vetrina.

Se il traffico (visualizzazioni, prodotti acquistati, tendenze) per la maggior parte degli SKU è insufficiente, potrebbero non essere disponibili dati sufficienti per completare il processo di apprendimento. Questo potrebbe causare l’aspetto dell’indicatore di preparazione nell’amministratore come se fosse bloccato.
Gli indicatori di preparazione hanno lo scopo di fornire ai commercianti un altro punto dati nella scelta del tipo di raccomandazioni migliore per il loro archivio. I numeri sono una guida e potrebbero non raggiungere mai il 100%.

## Raccomandazioni di backup {#backuprecs}

Se i dati di input non sono sufficienti per fornire tutti gli elementi di raccomandazione richiesti in un&#39;unità, Adobe Commerce fornisce consigli di backup per popolare le unità di raccomandazione. Ad esempio, se distribuisci `Recommended for you` tipo di raccomandazione per la pagina principale, un nuovo acquirente sul sito non ha generato dati comportamentali sufficienti per consigliare accuratamente i prodotti personalizzati. In questo caso, Adobe Commerce superfici gli elementi in base alla `Most viewed` tipo di raccomandazione per l&#39;acquirente.

I seguenti tipi di consigli si basano su `Most viewed` tipo di raccomandazione se non sono raccolti dati di input sufficienti:

- `Recommended for you`
- `Viewed this, viewed that`
- `Viewed this, bought that`
- `Bought this, bought that`
- `Trending`
- `Conversion (view to purchase)`
- `Conversion (view to cart)`
