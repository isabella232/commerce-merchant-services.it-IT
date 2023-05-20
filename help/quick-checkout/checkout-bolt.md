---
title: "Flusso di cassa di un utente Bolt in Adobe Commerce"
description: Panoramica di [!DNL Quick Checkout] flusso per un utente Bolt in Adobe Commerce.
exl-id: 12f58b7e-1f86-4891-b225-9f4be82c2d5d
source-git-commit: f790732804e110aad298689c0ddf74547ff17618
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Utenti ospiti

L’esperienza di pagamento degli Adobi è diversa da quella degli utenti ospiti. Quando un acquirente inserisce un indirizzo e-mail nel pagamento, il [!DNL Quick Checkout] lo convalida e trova un [!DNL Bolt] account.

>[!WARNING]
>
> Il [!DNL In-Store Pickup] (ISPU) non è supportata quando [!DNL Quick Checkout] è abilitato.

## Registrato [!DNL Bolt] account

Se un [!DNL Bolt] l&#39;account è stato trovato, gli acquirenti continuano con [!DNL Quick Checkout] esperienza di pagamento senza soluzione di continuità:

1. Immettere la password monouso (OTP) inviata a tale [!DNL Bolt] indirizzo e-mail dell’account o cellulare, a seconda di [preferenze dell&#39;utente in [!DNL Bolt] account](https://help.bolt.com/shoppers/account/account-settings/#how-to-set-preferred-login-method){target=_blank}.

![Popup](assets/new-logo-otp-email.png)

1. Una volta effettuato l’accesso con il tuo [!DNL Bolt] account, i dettagli vengono aggiunti automaticamente:

   - Informazioni spedizione
   - Metodo di pagamento

1. Effettua l’ordine.

>[!TIP]
>
> L’utente ospite effettua l’ordine e, facoltativamente, può registrarsi in Adobe Commerce.

## Nuovo [!DNL Bolt] account

In caso negativo [!DNL Bolt] L’account viene trovato, gli acquirenti continuano con il pagamento predefinito di Adobe Commerce e forniscono tutti i dettagli necessari per effettuare l’ordine:

- Informazioni su spedizione e fatturazione
- Metodo di spedizione
- Verifica metodo di pagamento
- Viene visualizzata una casella di controllo per la registrazione a [!DNL Bolt] per effettuare pagamenti più veloci prima di effettuare l&#39;ordine. L&#39;acquirente può accettare i termini e le condizioni per creare il proprio [!DNL Bolt] account.
- L’utente ospite effettua l’ordine e, facoltativamente, può registrarsi in Adobe Commerce.
