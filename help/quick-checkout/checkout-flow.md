---
title: "Flusso di pagamento in Adobe Commerce"
description: "Panoramica del [!DNL Quick Checkout] Flusso in Adobe Commerce."
exl-id: 82761627-a0d4-4cb0-aad1-9865fcb550d4
source-git-commit: f790732804e110aad298689c0ddf74547ff17618
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# [!DNL Quick Checkout] Flusso

Questa sezione fornisce una panoramica della tipica esperienza di pagamento tramite l’ [!DNL Quick Checkout] per l&#39;estensione Adobe Commerce.

Un successo [!DNL Quick Checkout] il flusso consiste dei seguenti passaggi:

1. Apri la vetrina e aggiungi oggetti nel carrello.
1. Procedi al pagamento.

![Pagamento](assets/proceed-checkout.png)

>[!NOTE]
>
> Puoi abilitare l&#39;accesso automatico per il tuo commerciante. Vedi [Argomento Bolt&#39;s Enable Automatic Login](https://help.bolt.com/products/embedded/direct-api/auto-login/) per ulteriori informazioni.

1. Quando richiesto, immetti un indirizzo e-mail associato a un [!DNL Bolt] conto.
1. Inserisci la Password una tantum (OTP) inviata a [!DNL Bolt] indirizzo e-mail o numero di telefono dell&#39;account.

![Popup OTP](assets/new-logo-otp-email.png)

1. Una volta effettuato l&#39;accesso con il tuo [!DNL Bolt] account, i dettagli del pagamento vengono compilati automaticamente:

   - Informazioni sulla spedizione
   - Metodo di pagamento

   >[!NOTE]
   >
   > È possibile utilizzare le informazioni sul portafoglio esistenti (indirizzo o informazioni sulla carta di credito) anche se i dettagli del pagamento vengono compilati automaticamente.

1. Ordine.

La [!DNL Quick Checkout] è compatibile con le opzioni di pagamento Adobe Commerce aggiuntive standard, come [carte regalo](https://docs.magento.com/user-guide/catalog/product-gift-card.html) o [codici a sconto](https://docs.magento.com/user-guide/marketing/price-rules-cart-coupon.html).

## [!DNL Quick Checkout] casi d&#39;uso

La [!DNL Quick Checkout] consente più casi d’uso durante un flusso di checkout:

- [Utente ospite](../quick-checkout/checkout-bolt.md) con un [!DNL Bolt] conto.
- Una esistente [Utente Adobe Commerce](../quick-checkout/checkout-adobe-commerce.md) con o senza registrazione [!DNL Bolt] conto.

## Assistenza

Contatta il supporto Adobe Commerce tramite [Centro assistenza Adobe Commerce](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html) per qualsiasi assistenza.
