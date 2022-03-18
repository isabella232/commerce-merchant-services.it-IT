---
title: Flusso di cassa
description: Panoramica [!DNL Express Checkout] Flusso in Adobe Commerce.
exl-id: 82761627-a0d4-4cb0-aad1-9865fcb550d4
source-git-commit: 163dd5260908b4ea3a8bfbcfdb834531d1603734
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# [!DNL Express Checkout] flusso

>[!IMPORTANT]
>
> Questa funzione è disponibile solo per gli utenti del programma Early Adopter (EAP) e non è ancora accessibile per tutti i clienti. Attualmente limitato ai clienti statunitensi. Per assistenza e domande, contatta il supporto Adobe Commerce.

Questa sezione fornisce una panoramica della tipica esperienza di pagamento tramite l’ [!DNL Express Checkout] per l&#39;estensione Adobe Commerce.

Un successo [!DNL Express Checkout] il flusso consiste dei seguenti passaggi:

1. Apri la vetrina e aggiungi oggetti nel carrello.
1. Procedi al pagamento.

![Pagamento](../assets/proceed-checkout.png)

1. Quando richiesto, immetti un indirizzo e-mail associato a un account Bolt.
1. Inserisci la Password una tantum (OTP) inviata all’indirizzo e-mail o al numero di telefono dell’account Bolt.
1. Una volta effettuato l&#39;accesso con il tuo account Bolt, i dettagli del pagamento vengono automaticamente inseriti:

   - Informazioni sulla spedizione
   - Metodo di pagamento

   >[!NOTE]
   >
   > È possibile utilizzare le informazioni sul portafoglio esistenti (indirizzo o informazioni sulla carta di credito) anche se i dettagli del pagamento vengono compilati automaticamente.

1. Ordine.

La [!DNL Express Checkout] è compatibile con le opzioni di pagamento Adobe Commerce aggiuntive standard, come [carte regalo](https://docs.magento.com/user-guide/catalog/product-gift-card.html) o [codici a sconto](https://docs.magento.com/user-guide/marketing/price-rules-cart-coupon.html).

## [!DNL Express Checkout] casi d&#39;uso

La [!DNL Express Checkout] consente più casi d’uso durante un flusso di checkout:

- Utente ospite con un account Bolt registrato.
- Utente ospite con un nuovo account Bolt.
- Un utente Adobe Commerce esistente con/senza un account Bolt registrato.

## Pagamento utente ospite: Come funziona

L’esperienza di pagamento degli ospiti è diversa dall’esperienza di accesso. Quando un acquirente inserisce un indirizzo e-mail nel checkout, il [!DNL Express Checkout] lo convalida per trovare un account Bolt esistente.

### Account Bolt registrato

Se viene trovato un account Bolt, gli acquirenti continuano con i loro [!DNL Express Checkout] esperienza di pagamento diretta:

1. Inserisci la Password una tantum (OTP, One-Time Password) inviata all’indirizzo e-mail o mobile dell’account Bolt, a seconda delle preferenze dell’utente nell’account Bolt.
1. Una volta effettuato l’accesso con il tuo account Bolt, vengono compilati automaticamente i dettagli del checkout:

   - Informazioni sulla spedizione
   - Metodo di pagamento

1. Ordine.

>[!TIP]
>
> L’utente ospite inserisce l’ordine e può registrarsi in Adobe Commerce.

### Nuovo conto Bolt

Se non viene trovato alcun account Bolt, gli acquirenti continuano con il loro checkout predefinito Adobe Commerce e l&#39;acquirente fornisce tutti i dettagli necessari per effettuare l&#39;ordine:

- Informazioni di spedizione e fatturazione
- Metodo di spedizione
- Revisione del metodo di pagamento
- Viene visualizzata una casella di controllo per la registrazione in Bolt per i checkout più rapidi prima di effettuare l&#39;ordine. Possono accettare i termini e le condizioni per creare il loro conto Bolt.

   ![Ricorda bullone](../assets/checked-bolt.png)

- L’utente ospite inserisce l’ordine e può registrarsi in Adobe Commerce.

## Un utente Adobe Commerce esistente: Come funziona

Un utente esistente può selezionare i dettagli esistenti quando l&#39;utente effettua un ordine con [!DNL Express Checkout] per un’esperienza di pagamento più rapida.

Quando un acquirente inserisce un indirizzo e-mail nel checkout, il [!DNL Express Checkout] lo convalida per trovare un account Bolt esistente.

### Account Bolt registrato con un utente Adobe Commerce

Se viene trovato un account Bolt, gli acquirenti continuano con il loro checkout predefinito Adobe Commerce e l&#39;acquirente fornisce tutti i dettagli necessari e poi inserisce l&#39;ordine:

- Informazioni di spedizione e fatturazione
- Metodo di spedizione
- Revisione del metodo di pagamento

Fai riferimento a [risoluzione](../express-checkout/troubleshooting.md) argomento per ulteriori informazioni in caso di problemi durante l’ordine come utente Adobe Commerce esistente.

>[!NOTE]
>
> Se l’utente dispone di un account Bolt e l’e-mail non viene visualizzata come registrata in Adobe Commerce, attiva l’accesso tramite password una tantum (OTP, One-Time Password). Consulta la sezione [conto Bolt registrato](#registered-bolt-account) flusso.

### Nuovo conto Bolt

Se non viene trovato alcun account Bolt, gli acquirenti continuano con il loro checkout Adobe Commerce predefinito e l&#39;acquirente seleziona tutti i dettagli necessari dalle informazioni salvate per inserire l&#39;ordine:

- Informazioni di spedizione e fatturazione
- Metodo di spedizione
- Revisione del metodo di pagamento
- Viene visualizzata una casella di controllo per la registrazione in Bolt per i checkout più rapidi prima di effettuare l&#39;ordine. Possono accettare i termini e le condizioni per creare il loro conto Bolt.

   ![Ricorda bullone](../assets/checked-bolt.png)

## Assistenza

Per assistenza e domande, contatta il supporto Adobe Commerce.
