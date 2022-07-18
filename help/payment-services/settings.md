---
title: Impostazioni dei servizi di pagamento
description: Dopo l'installazione, è possibile configurare [!DNL Payment Services] nella casa.
role: Admin, User
level: Intermediate
exl-id: 108f2b24-39c1-4c87-8deb-d82ee1c24d55
source-git-commit: 7c02bb8dcb7b5daa68664bd12672ac389f84cfa1
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Impostazioni

Puoi personalizzare [!DNL Payment Services] per soddisfare le tue esigenze con le impostazioni disponibili nella sezione [!DNL Payment Services] Casa.

Per configurare [!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] click **[!UICONTROL Settings]**. Queste opzioni di configurazione si applicano solo all’ambiente impostato nel _[!UICONTROL Payment mode]_in Impostazioni generali.

Consulta la sezione [[!UICONTROL General] sezione impostazioni](#general-settings) per ulteriori informazioni.

>[!IMPORTANT]
>
> Per la configurazione multi-store o legacy, fai riferimento alla [Configura nell’amministratore](configure-admin.md) argomento.

## Abilita servizi di pagamento

È possibile attivare [!DNL Payment Services] per il tuo sito web e abilita test sandbox o pagamenti live, nel [!UICONTROL General] sezione .

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Vista Home](assets/payment-services-menu-small.png)

1. Clic **[!UICONTROL Settings]**. Vedi [Introduzione a [!DNL Payment Services] Pagina principale](payments-home.md) per ulteriori informazioni.

   La _[!UICONTROL General]_include le impostazioni utilizzate per abilitare [!DNL Payment Services] come metodo di pagamento.

1. Per abilitare [!DNL Payment Services] come metodo di pagamento per il tuo negozio, attiva (**[!UICONTROL Enable Payment Services as payment method]**) a `Yes`.

1. Se stai ancora testando [!DNL Payment Services] per il tuo negozio, imposta **Modalità di pagamento** a `Sandbox`. Se sei pronto per abilitare i pagamenti live, impostalo su `Production`.

   >[!WARNING]
   >
   >Le _[!UICONTROL Sandbox Merchant ID]_e_[!UICONTROL Production Merchant ID]_ sono generati automaticamente e presenti nei rispettivi campi al termine dell’onboarding per la sandbox e/o la produzione. Non rimuovere o modificare questi ID.

1. Seleziona la vista Store nella **[!UICONTROL Scope]** menu a discesa, per il quale si desidera abilitare un metodo di pagamento.
1. Per modificare le impostazioni predefinite per le funzioni di pagamento e la visualizzazione della vetrina, impostare le opzioni aggiuntive necessarie:

   - [Campi carta di credito](#credit-card-fields)
   - [Pulsanti di pagamento](#payment-buttons)
   - [Stile pulsante](#button-style)

1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

### Campi carta di credito

La _[!UICONTROL Credit Card Fields]_Le impostazioni forniscono un&#39;opzione di pagamento semplice e sicura per i metodi di pagamento con carta di credito o con carta di debito.

Vedi [Opzioni di pagamento](payments-options.md#paypal-smart-buttons) per ulteriori informazioni.

1. Per modificare il nome del metodo di pagamento visualizzato durante il pagamento, modificare il valore nel **[!UICONTROL Checkout title]** campo .
1. A [imposta l&#39;azione di pagamento](production.md#set-payment-services-as-payment-method), interruttore **[!UICONTROL Payment action]** a `Authorize` o `Authorize and Capture`.
1. Per abilitare la modalità di debug, attiva **[!UICONTROL Debug Mode]** selettore.

   Quando si attiva la modalità di debug, ulteriori informazioni di debug sul pagamento della carta di credito vengono scritte nel `var/log/payment.log` file. Queste informazioni possono fornire ulteriori informazioni su un pagamento specifico per facilitare la risoluzione dei problemi.

1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

### Pulsanti di pagamento

La [!DNL PayPal Smart Buttons] le opzioni di pagamento forniscono al cliente un processo di pagamento semplice, rapido e sicuro. Vedi [Opzioni di pagamento](payments-options.md#paypal-smart-buttons) per ulteriori informazioni.

È possibile abilitare e configurare i pulsanti di pagamento:

1. Per modificare il nome del metodo di pagamento come mostrato durante il pagamento, modifica il valore nel **[!UICONTROL Checkout Title]** campo .
1. A [imposta l&#39;azione di pagamento](production.md#set-payment-services-as-payment-method), interruttore **[!UICONTROL Payment action]** a `Authorize` o `Authorize and Capture`.
1. Usa i selettori di attivazione/disattivazione [!DNL PayPal smart button] caratteristiche di visualizzazione:
   - **[!UICONTROL Show PayPal buttons on product detail page]**
   - **[!UICONTROL Show PayPal buttons on mini cart preview]**
   - **[!UICONTROL Show PayPal buttons on cart page]**
   - **[!UICONTROL Show PayPal Pay Later button]**
   - **[!UICONTROL Show Venmo button]**

1. Per modificare la variabile [Messaggi di pagamento in un secondo momento](payments-options.md#pay-later-button), attiva/disattiva **[!UICONTROL Show PayPal Pay Later message]** opzione .
1. Per abilitare la modalità di debug, attiva **[!UICONTROL Debug Mode]** selettore.

   Quando si abilita la modalità di debug, ulteriori informazioni di debug sul pagamento PayPal vengono scritte nel `var/log/payment.log` file. Queste informazioni possono fornire ulteriori informazioni su un pagamento specifico per facilitare la risoluzione dei problemi.

1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

#### Stile pulsante

Puoi anche configurare le _[!UICONTROL Button style]_opzioni dei pulsanti di pagamento:

1. Per modificare la variabile **[!UICONTROL Layout]**, seleziona `Vertical` o `Horizontal`.

   >[!NOTE]
   >
   > Se lo stile del pulsante è configurato come `Horizontal` e il tuo negozio è configurato per mostrare più pulsanti di pagamento, puoi visualizzare solo due pulsanti sulla pagina del prodotto, la pagina di pagamento e il mini carrello, e un pulsante visualizzato nel carrello.

1. Per attivare la linea di graduazione in un layout orizzontale, attiva la **[!UICONTROL Show tagline]** selettore.
1. Per modificare il **[!UICONTROL Color]**, seleziona l’opzione di colore desiderata.
1. Per modificare il **[!UICONTROL Shape]**, seleziona `Pill` o `Rect`.
1. Per abilitare il selettore dell’altezza del pulsante, attiva/disattiva **[!UICONTROL Responsive button height]** selettore.
1. Per modificare il **[!UICONTROL Label]**, seleziona l’opzione di etichetta desiderata.
1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

Puoi configurare [!DNL PayPal Smart Buttons] stile in Admin o [!DNL Payment Services Home]. Vedi [Guida allo stile dei pulsanti di PayPal](https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/) per ulteriori informazioni.
