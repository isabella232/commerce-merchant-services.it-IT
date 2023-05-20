---
title: "[!DNL Quick Checkout] per informazioni per gli sviluppatori di Adobe Commerce"
description: "[!DNL Quick Checkout] informazioni per gli sviluppatori."
exl-id: 8926eda4-b4de-4938-a86c-b095616f61f6
source-git-commit: b89427124cf76e7f36076454949191ee1d88f52c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# [!DNL Quick Checkout] Informazioni per sviluppatori

Questo argomento contiene informazioni per gli sviluppatori che lavorano a stretto contatto con Adobe Commerce e [!DNL Magento Open Source] e vuoi scoprire informazioni dettagliate sulla [!DNL Quick Checkout] estensione.

## Punti di estensione

Utilizzare i punti di estensione per personalizzare [!DNL Quick Checkout].

Utilizzando i punti di estensione, puoi effettuare personalizzazioni senza alterare effettivamente i componenti core nel codice dell’applicazione.

## Passaggio dettagli spedizione

Un punto di estensione può essere utilizzato per personalizzare la navigazione automatizzata dei passaggi dopo l’accesso con [!DNL Bolt].

Una volta che un acquirente accede con [!DNL Bolt], tutte le informazioni valide vengono precompilate e reindirizzate alla fase dei dettagli di pagamento per effettuare l&#39;ordine. Consulta la [flusso di pagamento](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/manage-checkout/checkout-flow.html) per ulteriori informazioni.

Questo punto di estensione consente di impedire la navigazione a una fase di pagamento e può essere utile nel caso in cui vi siano estensioni che richiedono a un acquirente di eseguire azioni aggiuntive sulla fase di spedizione. Di seguito è riportato un esempio su come utilizzare il punto di estensione con un mixin:

1. Registra un nuovo mixin in `require-config.js` file situato in `app/code/Vendor/ModuleName/view/frontend/`.

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

1. Estendere il modello in `can-navigate-to-payment.js` file situato in `app/code/Vendor/ModuleName/view/frontend/web/js/model/`.

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
> Questo è un esempio per un acquirente in Germania (DE) che vuole rimanere nella fase dei dettagli di spedizione.

Verifica [[!DNL Bolt] guida per sviluppatori](https://help.bolt.com/developers/) per ulteriori informazioni su [!DNL Bolt] per sviluppatori.
