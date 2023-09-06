---
title: "Flusso di cassa in Adobe Commerce"
description: "Panoramica della [!DNL Quick Checkout] flusso in Adobe Commerce."
exl-id: 82761627-a0d4-4cb0-aad1-9865fcb550d4
feature: Checkout, Services, Storefront
source-git-commit: 6ba5a283d9138b4c1be11b80486826304c63247f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# [!DNL Quick Checkout] Flusso

Questa sezione fornisce una panoramica della tipica esperienza di pagamento tramite [!DNL Quick Checkout] per l’estensione Adobe Commerce.

Un [!DNL Quick Checkout] Flusso è costituito dai seguenti passaggi:

1. Apri la vetrina e aggiungi oggetti al carrello.
1. Procedi con il pagamento.

![Pagamento](assets/proceed-checkout.png){width="200" zoomable="yes"}

>[!NOTE]
>
> Puoi abilitare l’accesso automatico per il tuo esercente. Consulta [Argomento Abilita accesso automatico di Bolt](https://help.bolt.com/products/embedded/direct-api/auto-login/) per ulteriori informazioni.

1. Quando richiesto, immetti un indirizzo e-mail associato a un [!DNL Bolt] account.
1. Immettere la password monouso (OTP) inviata a tale [!DNL Bolt] indirizzo e-mail o numero di telefono dell’account.

![Popup](assets/new-logo-otp-email.png){width="300" zoomable="yes"}

1. Una volta effettuato l’accesso con il tuo [!DNL Bolt] account, i dettagli di pagamento vengono compilati automaticamente:

   - Informazioni spedizione
   - Metodo di pagamento

   >[!NOTE]
   >
   > È possibile utilizzare le informazioni del portafoglio esistenti (indirizzo o informazioni sulla carta di credito) anche se i dettagli di pagamento vengono compilati automaticamente.

1. Ordinate.

Il [!DNL Quick Checkout] è compatibile con le opzioni di pagamento standard aggiuntive di Adobe Commerce, ad esempio [gift card](https://docs.magento.com/user-guide/catalog/product-gift-card.html) o [codici sconto](https://docs.magento.com/user-guide/marketing/price-rules-cart-coupon.html).

## [!DNL Quick Checkout] casi d’uso

Il [!DNL Quick Checkout] consente più casi d’uso durante un flusso di pagamento:

- [Utente ospite](../quick-checkout/checkout-bolt.md) con un nuovo o registrato [!DNL Bolt] account.
- Un esistente [Utente Adobe Commerce](../quick-checkout/checkout-adobe-commerce.md) con o senza un [!DNL Bolt] account.

## Ottieni aiuto

Contatta il supporto Adobe Commerce tramite [Centro assistenza Adobe Commerce](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html) per qualsiasi assistenza.
