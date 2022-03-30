---
title: Flusso di lavoro di implementazione
description: Scopri i passaggi per implementare correttamente [!DNL Product Recommendations] sulla vetrina.
source-git-commit: 4ad607c8595b25d01b5f5020b787fc1d35d4df25
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---

# Flusso di lavoro di implementazione

[!DNL Product Recommendations] utilizza sia i dati comportamentali che quelli di catalogo:

- Comportamento : dati provenienti dal coinvolgimento di un acquirente sul tuo sito, ad esempio visualizzazioni di prodotto, elementi aggiunti a un carrello e acquisti. Adobe Commerce e Adobe Sensei non raccolgono informazioni personali identificabili.

- Catalogo : metadati del prodotto, ad esempio nome, prezzo e disponibilità.

Quando installi `magento/product-recommendations module`, Adobe Sensei aggrega i dati comportamentali e di catalogo e crea [!DNL Product Recommendations] per ogni tipo di raccomandazione. La [!DNL Product Recommendations] quindi distribuisce tali raccomandazioni alla vetrina. Per implementare i consigli di prodotto nella vetrina, utilizza il seguente flusso di lavoro:

>[!NOTE]
>
> Se la vetrina è implementata utilizzando PWA Studi, consulta [Documentazione di PWA](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/). Se utilizzi una tecnologia front-end personalizzata come React o Vue JS, scopri come [integrare](headless.md) [!DNL Product Recommendations] nella tua vetrina senza testa.

## Flusso di lavoro

1. **Distribuire la raccolta dati in produzione**

   Distribuzione [!DNL Product Recommendations] richiede due [origini dati](type.md): catalogo e comportamento. Poiché la produzione è l&#39;unico ambiente in cui le azioni degli acquirenti vengono acquisite e analizzate, è nel tuo interesse iniziare la raccolta dei dati sulla produzione il prima possibile. [Scopri](behavioral-data.md) come Adobe Sensei addestra i modelli di apprendimento automatico che consentono di ottenere consigli di qualità superiore. Inoltre, quando inizi a raccogliere dati comportamentali sulla produzione, puoi [recuperare consigli](verify.md) basati su questi dati di produzione mentre operano in ambienti non di produzione. Puoi quindi testare e sperimentare diverse raccomandazioni calcolate in base ai dati reali dell’acquirente raccolti in produzione.

   Per distribuire la raccolta dati in produzione, devi [installare e configurare](install-configure.md) la [!DNL Product Recommendations] modulo fornendo un [Chiave API](https://docs.magento.com/user-guide/system/saas.html#apikey).

   >[!TIP]
   >
   > La distribuzione della raccolta dati non modifica l&#39;aspetto della vetrina o l&#39;esperienza degli acquirenti. Solo la creazione e la distribuzione di unità per i consigli altera l&#39;esperienza del cliente sulla vetrina. Assicurati di eseguire il test sull&#39;ambiente non di produzione prima di distribuirlo in produzione. Inoltre, non create unità di consigli finché non personalizzate il modello. Vedi il passaggio successivo.

1. **Personalizzare il modello in base allo stile**

   La vetrina rappresenta il tuo marchio, quindi assicurati di modificare il modello di consigli di prodotto in modo che corrisponda al tema del sito.

   >[!TIP]
   >
   > Personalizzando il modello, potete specificare il foglio di stile, sovrascrivere dove appare un&#39;unità di raccomandazione su una pagina e così via.

   Vedi [Personalizza](https://devdocs.magento.com/recommendations/customize.html) per informazioni su come completare questo passaggio, consulta la documentazione per gli sviluppatori .

1. **Sottoporre a test i consigli nell’ambiente non di produzione**

   È sempre consigliabile testare una nuova tecnologia nell’ambiente non di produzione prima di distribuirla in produzione. Il test dei consigli nell’ambiente non di produzione consente di giocare con diversi tipi di unità di consigli, posizionamento e pagine. È possibile richiamare consigli in base ai dati comportamentali già raccolti durante il test nell’ambiente non di produzione, in modo che i risultati dei consigli siano basati sul comportamento di acquisto dei clienti effettivi.

   >[!TIP]
   >
   > Assicurati che il catalogo dell&#39;ambiente non di produzione sia in gran parte uguale a quello di produzione. L’utilizzo di cataloghi simili assicura che i prodotti restituiti nelle unità di raccomandazione imitino i prodotti in produzione.

   Vedi [Recupero](staging-environment.md) dati comportamentali provenienti dall’ambiente di produzione per scoprire come completare questo passaggio.

1. **Creare e distribuire consigli nella vetrina di produzione**

   Dopo aver implementato la raccolta dei dati comportamentali in produzione, modificato il modello di raccomandazioni del prodotto e verificato i consigli utilizzando il comportamento effettivo dell’acquirente, puoi promuovere tutto il codice per la produzione e [creare](create.md) consigli sul prodotto live.
