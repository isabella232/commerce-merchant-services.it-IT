---
title: Eventi
description: Scopri quali eventi acquisiscono i dati e visualizza la definizione completa dello schema.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
source-git-commit: 2b735c292920bb0e9052d86bf152748e7ce96079
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Eventi del connettore Experience Platform

Di seguito sono elencati gli eventi Commerce disponibili quando installi l’estensione del connettore Experience Platform. I dati raccolti da questi eventi vengono inviati al server Edge di Adobe Experience Platform. Puoi anche creare [eventi personalizzati](custom-events.md) raccogliere dati aggiuntivi non forniti al momento.

Fai clic sul nome dell’evento per visualizzare la definizione completa dello schema.

| Evento | Tipo |
|---|---|
| [Aggiungi al carrello](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/addToCartAEP.ts) | Vetrina |
| [Visualizza carrello](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/viewAEP.ts) | Vetrina |
| [Visualizza pagina](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/page/viewAEP.ts) | Vetrina |
| [Visualizza prodotto](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/viewAEP.ts) | Vetrina |
| [Avvia pagamento](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/initiateCheckoutAEP.ts) | Vetrina |
| [Pagamento completo](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/checkout/placeOrderAEP.ts) | Vetrina |
| [Accesso](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signInAEP.ts) | Profilo |
| [Esci](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signOutAEP.ts) | Profilo |
| [Crea account](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/createAccountAEP.ts) | Profilo |
| [Modifica account](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/editAccountAEP.ts) | Profilo |
| [Richiesta di ricerca inviata](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/search/searchRequestSentAEP.ts) | Ricerca |
| [Risposta alla ricerca ricevuta](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/search/searchResponseReceivedAEP.ts) | Ricerca |

>[!NOTE]
>
> La `Sign In`, `Sign Out`, `Create Account`e `Update Account` gli eventi vengono attivati quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.
