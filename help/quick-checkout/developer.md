---
title: '"[!DNL Quick Checkout] per informazioni per sviluppatori Adobe Commerce"'
description: '"[!DNL Quick Checkout] informazioni per gli sviluppatori."'
exl-id: 8926eda4-b4de-4938-a86c-b095616f61f6
source-git-commit: 9841db7616c8aa6d5bc5af3e6e92c0abe9a4a1e2
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# [!DNL Quick Checkout] informazioni per gli sviluppatori

Questo argomento contiene informazioni per gli sviluppatori che lavorano a stretto contatto con Adobe Commerce e il codice di Magento Open Source e desiderano apprendere informazioni dettagliate sul [!DNL Quick Checkout] estensione.

## Punti di estensione

Utilizza i punti di estensione per personalizzare [!DNL Quick Checkout].

Utilizzando i punti di estensione, puoi effettuare personalizzazioni senza modificare effettivamente i componenti core nel codice dell&#39;applicazione.

## Passaggio dei dettagli di spedizione

Un punto di estensione può essere utilizzato per personalizzare la navigazione dei passaggi automatizzata dopo l&#39;accesso con [!DNL Bolt].

Una volta che un acquirente effettua l&#39;accesso con [!DNL Bolt], tutte le informazioni valide vengono precompilate e reindirizzate alla fase dei dettagli di pagamento per inserire l&#39;ordine. Consulta la sezione [flusso di cassa](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/manage-checkout/checkout-flow.html) per ulteriori informazioni.

Questo punto di estensione consente di impedire la navigazione a un passaggio di pagamento e può essere utile nel caso in cui ci siano estensioni che richiedono un acquirente per eseguire azioni aggiuntive sulla fase di spedizione. Vedi un esempio seguente su come utilizzare il punto di estensione con un mixin:

1. Registrare un nuovo mixin `require-config.js` file che si trova in `app/code/Vendor/ModuleName/view/frontend/`.

   ```js
   var config = {
       config: {
           mixins: {
               "Magento_ExpressCheckout/js/model/can-navigate-to-payment": {
                   "Vendor/ModuleName/js/model/can-navigate-to-payment-mixin": true
               }
           }
       }
   };
   ```

1. Estende il modello nel `can-navigate-to-payment.js` file che si trova in `app/code/Vendor/ModuleName/view/frontend/web/js/model/`.

   ```js
   define([
       'Magento_Checkout/js/model/quote',
       'mage/utils/wrapper',
   ], function (quote, wrapper) {
       'use strict';
       return function (canNavigateToPayment) {
           return wrapper.wrap(canNavigateToPayment, function (originalAction) {
               /* Include custom checks or conditions to stay on the shipping step,i.e: your shopper is from Germany */
               return originalAction() && quote.shippingAddress().countryId !== 'DE');
           });
       };
   });
   ```

>[!WARNING]
>
> Questo è un esempio per un acquirente in Germania (DE) che vuole rimanere sul passo dei dettagli di spedizione.

Controlla [[!DNL Bolt] guida per sviluppatori](https://help.bolt.com/developers/) per ulteriori informazioni su [!DNL Bolt] per sviluppatori.
