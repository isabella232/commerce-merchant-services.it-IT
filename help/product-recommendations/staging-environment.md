---
title: Test in ambiente di staging
description: Scopri come utilizzare [!DNL Product Recommendations] dall’ambiente di produzione nell’ambiente di staging a scopo di test.
exl-id: 178ff2aa-7821-45f7-85f1-d490d8182817
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Test in ambiente di staging

Prima di distribuire i consigli nell’ambiente di produzione, è necessario eseguire il test in un ambiente non di produzione per garantire che tutto funzioni come previsto.

[!DNL Product Recommendations] restituisce i prodotti in base a [dati comportamentali degli acquirenti](behavioral-data.md) raccolti dalla vostra vetrina. In un ambiente non di produzione, tuttavia, è probabile che non si dispone di dati comportamentali da parte degli acquirenti. L’unico tipo di raccomandazione che è possibile sottoporre a test senza dati comportamentali è `More like this`. Questo tipo di raccomandazione non richiede dati di input, in quanto utilizza una corrispondenza diretta con somiglianza del contenuto.

I seguenti tipi di consigli richiedono dati comportamentali:

- Più visualizzato
- Ho visualizzato questo, visto che
- Ho comprato questo, l&#39;ho comprato

Come si possono testare i consigli in un ambiente non di produzione utilizzando i dati comportamentali? Ci sono un paio di opzioni.

## Recupera consigli dall’ambiente di produzione (consigliato)

Adobe Commerce consente di recuperare i consigli dall’ambiente di produzione e visualizzarli in anteprima nell’ambiente non di produzione tramite [commutazione](settings.md) lo spazio dati SaaS.

Per recuperare i consigli dall’ambiente di produzione, è necessario assicurarsi che:

- Raccolta dati di Storefront [configurato e abilitato](install-configure.md) alla produzione.
- Il catalogo dell’ambiente non di produzione è in gran parte lo stesso di quello di produzione. L’utilizzo di cataloghi simili assicura che i prodotti restituiti nelle unità di raccomandazione imitino strettamente quelli in produzione.

## Generare dati comportamentali in ambiente non di produzione

1. Distribuisci `magento/product-recommendations` in un ambiente non di produzione in cui i dati del catalogo sono simili al catalogo di produzione.

1. Utilizza uno degli ID spazio dati non di produzione per [configurazione](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) nell&#39;amministratore.

1. Genera i dati da solo cliccando sulla vetrina per simulare il comportamento degli acquirenti effettivi (o crea uno script di automazione). Mediante il test, puoi generare eventi comportamentali nell’ambiente non di produzione. Tali eventi vengono utilizzati per generare affinità di prodotto che alimentano i consigli. Per le prove, [!DNL Commerce] suggerisce di interagire con i seguenti tipi di consigli:

   - Più visualizzato - Richiede dati di input minimi. Gli utenti devono visualizzare i prodotti.
   - Visualizzato, visualizzato questo - Richiede più utenti per visualizzare più prodotti.
   - Acquistato questo, acquistato - Richiede più utenti per acquistare più prodotti.

### Avvertenze

- I dati comportamentali e di catalogo provenienti da SaaS Data Space non di produzione identificano un ambiente isolato in cui le raccomandazioni sui prodotti risultanti si basano interamente sui dati comportamentali generati sulla vetrina associata.

- Poiché non si dispone di grandi quantità di dati comportamentali, i dati di input per l&#39;elaborazione delle associazioni di prodotti sono sparsi. Tuttavia, tali dati vengono comunque inviati a Sensei per calcolare i modelli di apprendimento automatico e fornire consigli basati sui dati generati in questo ambiente.
