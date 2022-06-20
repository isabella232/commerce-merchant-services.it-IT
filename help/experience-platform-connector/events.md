---
title: Eventi
description: Scopri quali eventi acquisiscono i dati e visualizza la definizione completa dello schema.
source-git-commit: ce1ce5a7e028d1c957a9a36c73c371eedfb1e1e8
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Eventi beacon di progetto

Di seguito sono elencati i [!DNL Commerce] eventi disponibili quando installi l’estensione del connettore Experience Platform. I dati raccolti da questi eventi vengono inviati al server Edge di Adobe Experience Platform. Puoi anche creare [eventi personalizzati](custom-events.md) raccogliere dati aggiuntivi non forniti al momento.

Fai clic sul nome dell’evento per visualizzare la definizione completa dello schema.

| Evento | Tipo |
|---|---|---|
| [Aggiungi al carrello](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/addToCartAEP.ts) | Vetrina |
| [Visualizza carrello](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/viewAEP.ts) | Vetrina |
| [Visualizza pagina](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/page/viewAEP.ts) | Vetrina |
| [Visualizza prodotto](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/viewAEP.ts) | Vetrina |
| [Avvia pagamento](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/initiateCheckoutAEP.ts) | Vetrina |
| Pagamento completo | Vetrina |
| [Accesso](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signInAEP.ts) | Profilo |
| [Esci](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signOutAEP.ts) | Profilo |
| [Crea account](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/createAccountAEP.ts) | Profilo |
| [Modifica account](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/editAccountAEP.ts) | Profilo |

>[!NOTE]
>
> La `Sign In`, `Sign Out`, `Create Account`e `Update Account` gli eventi vengono attivati quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.
