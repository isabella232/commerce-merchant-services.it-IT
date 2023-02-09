---
title: "Flusso di pagamento per un utente Adobe Commerce"
description: "Panoramica del [!DNL Quick Checkout] flusso per un utente Adobe Commerce."
exl-id: 085e393b-15f6-4d5a-a04d-927b1f95b74e
source-git-commit: 66082614ffe6456e2c24a1e8d9baaa1113fb7ffb
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Un utente Adobe Commerce esistente: Come funziona

Un utente Adobe Commerce esistente può selezionare i dettagli di spedizione e pagamento salvati quando effettua un ordine con il [!DNL Quick Checkout] per un’esperienza di pagamento più rapida.

Quando un acquirente inserisce il proprio indirizzo e-mail al momento del pagamento, il [!DNL Quick Checkout] lo convalida e trova un [!DNL Bolt] conto.

## Utente registrato sia in Adobe Commerce che [!DNL Bolt]

Quando un acquirente è un utente registrato sia in Adobe Commerce che [!DNL Bolt] reti, entrambe le reti sono fornite dati relativi alla spedizione e al pagamento.

Se [!DNL Bolt] account trovato durante il pagamento, gli acquirenti possono continuare con il loro [!DNL Quick Checkout] esperienza di pagamento diretta:

1. Inserisci la Password una tantum (OTP) inviata a [!DNL Bolt] indirizzo e-mail o mobile dell&#39;account, a seconda [preferenze dell&#39;utente nella [!DNL Bolt] account](https://help.bolt.com/shoppers/account/account-settings/#how-to-set-preferred-login-method){target=_blank}.

![Popup OTP](assets/pop-up.png)

1. Una volta effettuato l&#39;accesso con il tuo [!DNL Bolt] account, i dettagli vengono aggiunti automaticamente:

   - Informazioni sulla spedizione
   - Metodo di pagamento

1. Ordinate.

>[!NOTE]
>
> Il pop-up Bolt OTP viene visualizzato solo quando l&#39;acquirente si trova nella pagina di pagamento. L&#39;acquirente può rinunciare all&#39;accesso a Bolt chiudendo la finestra a comparsa.

Se l&#39;acquirente ha effettuato l&#39;accesso ad Adobe Commerce prima del pagamento, il [!DNL Bolt] Il pop-up OTP non verrà visualizzato durante il pagamento, ma viene visualizzato un messaggio che suggerisce all&#39;acquirente di effettuare l&#39;accesso per accedere al loro portafoglio Bolt.

Se riscontri problemi quando inserisci un ordine come utente Adobe Commerce esistente, consulta la [Risolvere i problemi relativi all’estrazione rapida](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/quick-checkout-issues.html) nell&#39;Aiuto di Adobe Commerce.

## Accesso automatico

Il componente Accesso automatico rileva quando un acquirente ha una sessione Bolt attiva e registra automaticamente l’acquirente. Questo ignora il rilevamento dell’account e i passaggi del codice a password una tantum (OTP) perché l’acquirente li ha completati in una sessione precedente.

È possibile configurare un accesso automatico per [!DNL Quick Checkout] utenti. È possibile abilitare una configurazione per accedere automaticamente a un utente durante il pagamento.

1. Sulla _Amministratore_ barra laterale, passare a **Negozi** > **Configurazione** > **Pagamento** per accedere alla pagina di configurazione generale di Checkout Admin.
1. In _Impostazioni del servizio_ sezione per [!DNL Quick Checkout], fornisce tutti i dettagli necessari per impostare l’accesso automatico.

Vedi [[!DNL Quick Checkout] configurare le impostazioni del servizio](../quick-checkout/onboarding.md#configure-service-settings) per ulteriori informazioni.

>[!NOTE]
>
> Primo accesso quando **accesso automatico** è abilitato richiede il consenso dell’utente per autorizzarlo accettando una finestra a comparsa.

## Nuovo [!DNL Bolt] account

Se no [!DNL Bolt] viene trovato l&#39;account, gli acquirenti continuano con il loro checkout predefinito Adobe Commerce e l&#39;acquirente seleziona tutti i dettagli necessari dalle informazioni salvate per inserire l&#39;ordine:

- Informazioni di spedizione e fatturazione
- Metodo di spedizione
- Revisione del metodo di pagamento
- L&#39;opzione per registrarsi [!DNL Bolt] per i checkout più veloci prima di inserire l&#39;ordine viene visualizzato. L&#39;acquirente può accettare i termini e le condizioni per creare le proprie [!DNL Bolt] conto.

   ![Ricorda [!DNL Bolt]](assets/checkbox-remember-bolt.png)
