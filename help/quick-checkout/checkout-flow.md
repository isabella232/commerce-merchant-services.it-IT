---
title: '"Flusso di pagamento"'
description: '"Panoramica del [!DNL Quick Checkout] Flusso in Adobe Commerce."'
exl-id: 82761627-a0d4-4cb0-aad1-9865fcb550d4
source-git-commit: 9841db7616c8aa6d5bc5af3e6e92c0abe9a4a1e2
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 0%

---

# [!DNL Quick Checkout] flusso

Questa sezione fornisce una panoramica della tipica esperienza di pagamento tramite l’ [!DNL Quick Checkout] per l&#39;estensione Adobe Commerce.

Un successo [!DNL Quick Checkout] il flusso consiste dei seguenti passaggi:

1. Apri la vetrina e aggiungi oggetti nel carrello.
1. Procedi al pagamento.

![Pagamento](assets/proceed-checkout.png)

1. Quando richiesto, immetti un indirizzo e-mail associato a un [!DNL Bolt] conto.
1. Inserisci la Password una tantum (OTP) inviata a [!DNL Bolt] indirizzo e-mail o numero di telefono dell’account.
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

- Utente ospite con una registrazione [!DNL Bolt] conto.
- Utente ospite con un nuovo [!DNL Bolt] conto.
- Un utente Adobe Commerce esistente con/senza una registrazione [!DNL Bolt] conto.

## Pagamento utente ospite: Come funziona

L’esperienza di pagamento degli ospiti è diversa dall’esperienza di accesso. Quando un acquirente inserisce un indirizzo e-mail nel checkout, il [!DNL Quick Checkout] lo convalida per trovare un [!DNL Bolt] conto.

### Registrato [!DNL Bolt] account

Se [!DNL Bolt] account trovato, gli acquirenti continuano con il loro [!DNL Quick Checkout] esperienza di pagamento diretta:

1. Inserisci la Password una tantum (OTP) inviata a [!DNL Bolt] indirizzo e-mail o mobile dell’account, a seconda delle preferenze dell’utente nella [!DNL Bolt] conto.
1. Una volta effettuato l&#39;accesso con il tuo [!DNL Bolt] account, riempie automaticamente i dettagli del pagamento:

   - Informazioni sulla spedizione
   - Metodo di pagamento

1. Ordine.

>[!TIP]
>
> L’utente ospite inserisce l’ordine e può registrarsi in Adobe Commerce.

### Nuovo [!DNL Bolt] account

Se no [!DNL Bolt] viene trovato l&#39;account, gli acquirenti continuano con il loro checkout predefinito Adobe Commerce e l&#39;acquirente fornisce tutti i dettagli necessari per effettuare l&#39;ordine:

- Informazioni di spedizione e fatturazione
- Metodo di spedizione
- Revisione del metodo di pagamento
- Viene visualizzata una casella di controllo per la registrazione in [!DNL Bolt] per pagamenti più rapidi prima di effettuare l&#39;ordine. Possono accettare i termini e le condizioni per creare le loro [!DNL Bolt] conto.

   ![Ricorda [!DNL Bolt]](assets/checked-bolt.png)

- L’utente ospite inserisce l’ordine e può registrarsi in Adobe Commerce.

## Un utente Adobe Commerce esistente: Come funziona

Un utente esistente può selezionare i dettagli esistenti quando l&#39;utente effettua un ordine con [!DNL Quick Checkout] per un’esperienza di pagamento più rapida.

Quando un acquirente inserisce un indirizzo e-mail nel checkout, il [!DNL Quick Checkout] lo convalida per trovare un [!DNL Bolt] conto.

### Registrato [!DNL Bolt] account con un utente Adobe Commerce

Se [!DNL Bolt] viene trovato l&#39;account, gli acquirenti continuano con il loro checkout predefinito di Adobe Commerce e l&#39;acquirente fornisce tutti i dettagli necessari e poi inserisce l&#39;ordine:

- Informazioni di spedizione e fatturazione
- Metodo di spedizione
- Revisione del metodo di pagamento

Fai riferimento a [risoluzione](../quick-checkout/troubleshooting.md) argomento per ulteriori informazioni in caso di problemi durante l’ordine come utente Adobe Commerce esistente.

>[!NOTE]
>
> Se l&#39;utente ha una [!DNL Bolt] l’account e-mail non vengono visualizzati come registrati in Adobe Commerce, bensì attivano l’accesso tramite password una tantum (OTP, One-Time Password). Consulta la sezione [registrato [!DNL Bolt] account](#registered-bolt-account) flusso.

### Nuovo [!DNL Bolt] account

Se no [!DNL Bolt] l&#39;account viene trovato, gli acquirenti continuano con il loro checkout Adobe Commerce predefinito e l&#39;acquirente seleziona tutti i dettagli necessari dalle informazioni salvate per inserire l&#39;ordine:

- Informazioni di spedizione e fatturazione
- Metodo di spedizione
- Revisione del metodo di pagamento
- Viene visualizzata una casella di controllo per la registrazione in [!DNL Bolt] per pagamenti più rapidi prima di effettuare l&#39;ordine. Possono accettare i termini e le condizioni per creare le loro [!DNL Bolt] conto.

   ![Ricorda [!DNL Bolt]](assets/checked-bolt.png)

## Assistenza

Contatto [Supporto Adobe Commerce](mailto:quick-checkout-support@adobe.com) per qualsiasi assistenza.
