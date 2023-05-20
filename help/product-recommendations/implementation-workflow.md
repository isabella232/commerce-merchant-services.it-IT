---
title: Flusso di lavoro di implementazione
description: Scopri i passaggi per implementare correttamente [!DNL Product Recommendations] sul vetrina.
exl-id: 766e1191-0330-4515-9331-e45318539dc9
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Flusso di lavoro di implementazione

[!DNL Product Recommendations] utilizza sia i dati comportamentali che quelli di catalogo:

- Comportamento: dati del coinvolgimento di un acquirente sul tuo sito, ad esempio visualizzazioni di prodotti, elementi aggiunti al carrello e acquisti. Adobe Commerce e Adobe Sensei non raccolgono informazioni personali.

- Catalogo: metadati del prodotto come nome, prezzo e disponibilità.

Quando si installa `magento/product-recommendations module`, Adobe Sensei aggrega i dati comportamentali e di catalogo e crea [!DNL Product Recommendations] per ogni tipo di consiglio. Il [!DNL Product Recommendations] Il servizio distribuisce quindi tali consigli nella vetrina. Per aiutarti a implementare i consigli di prodotto nella vetrina, utilizza il seguente flusso di lavoro:

>[!NOTE]
>
> Se la vetrina è implementata utilizzando PWA Studi, consulta [Documentazione di PWA](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/). Se utilizzi una tecnologia front-end personalizzata come React o Vue JS, scopri come [integrare](headless.md) [!DNL Product Recommendations] nella vetrina headless.

## Flusso di lavoro

1. **Distribuire la raccolta dati in produzione**

   Distribuzione [!DNL Product Recommendations] richiede due [origini dati](type.md): catalogo e comportamento. Poiché la produzione è l’unico ambiente in cui le azioni degli acquirenti vengono acquisite e analizzate, è nel tuo interesse iniziare la raccolta dei dati sulla produzione il prima possibile. [Scopri](behavioral-data.md) in che modo Adobe Sensei addestra modelli di apprendimento automatico che generano consigli di qualità superiore. Come ulteriore vantaggio, quando inizi a raccogliere dati comportamentali sulla produzione, puoi [recupera consigli](verify.md) basati su questi dati di produzione mentre si lavora in ambienti non di produzione. Puoi quindi testare e sperimentare diversi consigli calcolati in base ai dati reali dell’acquirente raccolti in produzione.

   Per distribuire la raccolta dati in produzione, è necessario [installare e configurare](install-configure.md) il [!DNL Product Recommendations] fornendo un [Chiave API](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html).

   >[!TIP]
   >
   > L’implementazione della raccolta dati non cambia l’aspetto della vetrina o l’esperienza degli acquirenti. Solo la creazione e la distribuzione di unità di consigli modifica l’esperienza del cliente nella vetrina. Prima di implementare in produzione, assicurati di eseguire il test nell’ambiente non di produzione. Inoltre, non creare unità di consigli fino a quando non personalizzi il modello. Vedere il passaggio successivo.

1. **Personalizza il modello in base al tuo stile**

   La vetrina rappresenta il tuo marchio, quindi assicurati di modificare il modello di consigli di prodotto in modo che corrisponda al tema del sito.

   >[!TIP]
   >
   > Personalizzando il modello, è possibile specificare il foglio di stile, sovrascrivere la posizione in cui un&#39;unità di consigli viene visualizzata in una pagina e così via.

   Consulta [Personalizza](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/customize.html) per informazioni su come completare questo passaggio, consulta la documentazione per sviluppatori.

1. **Consigli di test per l’ambiente non di produzione**

   È sempre consigliabile testare una nuova tecnologia nell’ambiente non di produzione prima di implementarla in produzione. Il test dei consigli sull’ambiente non di produzione consente di riprodurre con diversi tipi di unità, posizioni e pagine per i consigli. Puoi estrarre i consigli in base ai dati comportamentali già raccolti durante il test in un ambiente non di produzione, in modo che i risultati dei consigli si basino sul comportamento di acquisto dei clienti effettivi.

   >[!TIP]
   >
   > Assicurati che il catalogo dell’ambiente non di produzione sia in gran parte lo stesso di quello esistente in produzione. L’utilizzo di cataloghi simili garantisce che i prodotti restituiti nelle unità di raccomandazione imitino strettamente i prodotti in produzione.

   Consulta [Recupera](staging-environment.md) dati comportamentali dall’ambiente di produzione per scoprire come completare questo passaggio.

1. **Creare e distribuire consigli nella vetrina di produzione**

   Ora che hai implementato la raccolta di dati comportamentali in produzione, modificato il modello di consigli di prodotto e testato i consigli utilizzando il comportamento effettivo degli acquirenti, sei pronto a promuovere tutto il codice in produzione e [creare](create.md) consigli sui prodotti live.
