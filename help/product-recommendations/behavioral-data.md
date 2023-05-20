---
title: Dati comportamentali
description: Scopri i dati comportamentali e quando puoi iniziare a utilizzarli.
exl-id: d68a97b9-1497-4603-a72c-4aaaf6e048cb
source-git-commit: 840b091638aedd3f6ac097a010d035eff997ffe2
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 0%

---

# Dati comportamentali

Alcuni tipi di consigli utilizzano i dati comportamentali dei tuoi acquirenti per addestrare modelli di apprendimento automatico per creare consigli personalizzati. Altri tipi di consigli utilizzano solo i dati di catalogo e non utilizzano dati comportamentali. Per iniziare rapidamente, puoi utilizzare i seguenti tipi di consigli solo per catalogo:

- `More like this`
- `Visual similarity`

Quando puoi iniziare a utilizzare i tipi di consigli che utilizzano i dati comportamentali? Dipende. Tale procedura è denominata _Avvio a freddo_ problema.

Il _Avvio a freddo_ Il problema è una misura del tempo che un modello deve allenarsi prima di poter essere considerato di alta qualità. Nei consigli di prodotto, si traduce nell’attendere che Adobe Sensei adotti i modelli di apprendimento automatico prima di distribuire unità di consigli sul sito. Maggiore è il numero di dati di questi modelli, più accurati e utili sono i consigli. La raccolta di questi dati richiede tempo e varia in base al volume di traffico. Poiché questi dati possono essere raccolti solo su un sito di produzione, è nel tuo interesse distribuire la raccolta dati il prima possibile. Per eseguire questa operazione: [installazione e configurazione](install-configure.md) il `magento/production-recommendations` modulo.

La tabella seguente fornisce alcune indicazioni generali sul tempo necessario per raccogliere dati sufficienti per ogni tipo di consiglio:

| Tipo di consiglio | Tempo di formazione | Note |
|---|---|---|
| Basato sulla popolarità (`Most viewed`, `Most purchased`, `Most added to cart`) | Varia | Dipende dal volume degli eventi: le visualizzazioni sono più comuni e quindi apprende più rapidamente; quindi aggiunge al carrello, quindi acquista |
| `Viewed this, viewed that` | Richiede più formazione | Il volume delle visualizzazioni dei prodotti è decisamente elevato |
| `Viewed this, bought that`, `Bought this, bought that` | Richiede il massimo della formazione | Gli eventi di acquisto sono gli eventi più rari sul sito di commerce, soprattutto rispetto alle visualizzazioni di prodotto |
| `Trending` | Richiede tre giorni di dati per stabilire una baseline di popolarità | Il trend è una misura dello slancio recente nella popolarità di un prodotto rispetto alla sua linea di base di popolarità. Il punteggio di tendenza di un prodotto viene calcolato utilizzando un set in primo piano (popolarità recente superiore a 24 ore) e un set in background (linea di base di popolarità superiore a 72 ore). Se un elemento è diventato molto più popolare nelle ultime 24 ore rispetto alla popolarità della sua linea di base, riceve un punteggio di tendenza elevato. Ogni prodotto ha questo punteggio, e quelli più alti in qualsiasi momento comprendono il set di prodotti di tendenza principali. |

Altre variabili che possono influire sul tempo necessario per la formazione:

- Un volume di traffico più elevato contribuisce a un apprendimento più rapido
- Alcuni tipi di consigli si addestrano più rapidamente di altri
- Adobe Commerce ricalcola i dati comportamentali ogni quattro ore. Recommendations diventa più preciso quanto più a lungo vengono utilizzati sul tuo sito.

Per aiutarti a visualizzare l’avanzamento della formazione di ciascun tipo di consiglio, [crea consiglio](create.md) nella pagina vengono visualizzati gli indicatori di preparazione.

Durante la raccolta dei dati sulla produzione e la formazione dei modelli di apprendimento automatico, puoi implementare [attività rimanenti](implementation-workflow.md) necessario per distribuire i consigli nella vetrina. Al termine del test e della configurazione dei consigli, i modelli di apprendimento automatico hanno raccolto e calcolato dati sufficienti per generare consigli rilevanti e quindi distribuire i consigli nella vetrina.

Se il traffico è insufficiente (visualizzazioni, prodotti acquistati, tendenze) per la maggior parte delle SKU, i dati potrebbero non essere sufficienti per completare il processo di apprendimento. In questo modo l’indicatore di preparazione nell’amministratore potrebbe sembrare bloccato.
Gli indicatori di preparazione hanno lo scopo di fornire agli esercenti un altro punto di dati nella scelta del tipo di consigli migliore per il negozio. I numeri sono una guida e potrebbero non raggiungere mai il 100%.

## Raccomandazioni per il backup {#backuprecs}

Se i dati di input non sono sufficienti per fornire tutti gli elementi di consigli richiesti in un&#39;unità, Adobe Commerce fornisce consigli di backup per popolare le unità di consigli. Ad esempio, se distribuisci `Recommended for you` tipo di consiglio nella tua pagina principale: un acquirente sul tuo sito non ha generato sufficienti dati comportamentali per consigliare accuratamente prodotti personalizzati. In questo caso, Adobe Commerce fa emergere gli elementi in base al `Most viewed` tipo di consiglio a questo acquirente.

I seguenti tipi di consigli sono di fallback su `Most viewed` tipo di consiglio se non sono stati raccolti dati di input sufficienti:

- `Recommended for you`
- `Viewed this, viewed that`
- `Viewed this, bought that`
- `Bought this, bought that`
- `Trending`
- `Conversion (view to purchase)`
- `Conversion (view to cart)`
