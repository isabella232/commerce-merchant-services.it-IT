---
title: Configurare la sandbox di prova
description: Utilizzare un account sandbox PayPal per utilizzare [!DNL Payment Services] in modalità di prova.
exl-id: 99c14b4e-e6cf-48f9-9546-5c0d5c71464d
source-git-commit: 5aba246ce2a7802954a90c08c7dac2247a71ff6d
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 0%

---

# Configurare la sandbox di prova

Prima di iniziare l&#39;onboarding della sandbox, devi registrarti per un account PayPal Developer gratuito e creare sia un commerciante (da utilizzare per l&#39;onboarding) che account di acquisto (da utilizzare per testare il pagamento). Se necessario, puoi creare più account sviluppatore.

Un account sandbox PayPal consente di utilizzare [!DNL Payment Services] in modalità di prova. PayPal richiede l&#39;utilizzo di un account di prova della sandbox aziendale generato da PayPal Developer Portal, e-mail e password per l&#39;onboarding della sandbox. *Non creare un altro account durante il processo di onboarding della sandbox.*

## onboarding sandbox

Per completare l’onboarding della sandbox:

1. Passa a [Pagina Account sviluppatore PayPal](https://developer.paypal.com/developer/accounts/).
1. Fai clic su **[!UICONTROL Log in to Dashboard]** e accedi con il tuo account di test della sandbox aziendale generato da PayPal Developer Portal esistente oppure fai clic su **Iscriviti** per creare un account.
1. Crea un account sandbox PayPal:
   1. Vai a _[!UICONTROL Testing Tools]_>**[!UICONTROL Sandbox Accounts]**.
   1. Fai clic su **[!UICONTROL Create account]**.

      Se hai creato un account sandbox PayPal durante il processo di onboarding di PayPal nella sandbox, devi [reimpostare la sandbox di onboarding](#reset-your-sandbox-account) perché o non puoi verificare il tuo messaggio e-mail.

   1. Seleziona **[!UICONTROL Business]** come Tipo di account e fai clic su **[!UICONTROL Create]**.
   1. In _[!UICONTROL Sandbox Accounts]_fai clic sui tre punti nella sezione_[!UICONTROL Manage accounts]_ per l’account sandbox creato.
   1. Fai clic su **[!UICONTROL View/edit account]**.

      ![PayPal - Visualizza/modifica account sandbox](assets/onboarding-viewedit-sandbox.png)

   1. Copia e salva l’ID e-mail e la password generata dal sistema per un utilizzo futuro.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Fai clic su **[!UICONTROL Sandbox onboarding]**.

   Questa opzione è visibile se non hai ancora completato l’onboarding della sandbox per [!DNL Payment Services].

   Un ID commerciante sandbox viene generato automaticamente e popolato in [impostazioni](settings.md). Non modificare o modificare questo ID.

   Ti viene presentata una finestra PayPal per la connessione di un account PayPal per iniziare ad accettare pagamenti.

1. Immetti l&#39;e-mail e la password dell&#39;account sandbox PayPal generato al passaggio 3 (non le informazioni sull&#39;account commerciale PayPal) e il tuo paese o regione.
1. Fai clic su **[!UICONTROL Next]**.

   ![PayPal - Connessione dell&#39;account PayPal per i pagamenti](assets/paypal-connectacct.png)

1. Continua a seguire il flusso PayPal utilizzando le credenziali dell’account sandbox salvate in precedenza.
1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   La **[!UICONTROL Sandbox onboarding]** Il pulsante non è più visibile e viene visualizzato il testo &quot;Pagamenti sandbox in sospeso&quot;.

Quando l&#39;onboarding della sandbox PayPal è approvato, dovresti vedere una notifica in cui si informa che il sistema di pagamento è attualmente in modalità sandbox e non sta elaborando pagamenti live.

>[!IMPORTANT]
>
>Se revochi il consenso a [!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] per l&#39;elaborazione dei pagamenti (nelle impostazioni del tuo account PayPal), gli ordini nel tuo negozio non possono essere elaborati da [!DNL Payment Services]. Nella home di Payment Services viene visualizzato un avviso relativo al consenso revocato. Per ignorare l’avviso, fai clic su **[!UICONTROL Do not show again]**.

### Ripristino dell’account sandbox

Se hai creato un account sandbox PayPal durante il processo di onboarding di PayPal, devi reimpostare la sandbox di onboarding perché o non puoi verificare il tuo messaggio e-mail.

Per ripristinare l’account sandbox:

1. Fai clic su **[!UICONTROL Reset sandbox]**. [Crea un account sandbox aziendale PayPal](https://developer.paypal.com/docs/api-basics/sandbox/accounts/#create-a-business-sandbox-account).
1. Fai clic su **[!UICONTROL Sandbox onboarding]** e completa il successivo set di passaggi.

## Abilita il numero di telefono del contatto

Contatta il numero di telefono ti consente di ottenere i numeri di telefono di contatto che PayPal raccoglie dai tuoi clienti. PayPal raccoglie sempre i numeri telefonici dei titolari di account PayPal per confermare la loro identità e contattarli per risolvere i problemi sui loro account o per completare i loro processi di realizzazione. Tuttavia, PayPal scoraggia l&#39;uso di numeri di telefono di contatto direttamente dal commerciante perché può avere un impatto negativo sulle vendite. Consulta la sezione [PayPal ottieni numeri di telefono di contatto](https://developer.paypal.com/docs/admin/checkout-settings/#get-contact-telephone-numbers) documentazione per ulteriori informazioni.

Questa funzione è `off` per impostazione predefinita. Quando lo abiliti, gli amministratori degli archivi possono visualizzare i numeri di telefono quando un cliente completa un flusso di cassa con marchio al di fuori della pagina di pagamento.

>[!IMPORTANT]
>
>Questa impostazione non si applica ad altri flussi di pagamento.

## Test in ambiente sandbox

Vedi [Test e convalida](test-validate.md) per ulteriori informazioni.
