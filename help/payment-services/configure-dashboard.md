---
title: Configura nel dashboard
description: Dopo l'installazione, è possibile configurare [!DNL Payment Services] nel dashboard.
role: Admin, User
level: Intermediate
exl-id: 015c5c8c-8184-45c1-932a-f4365ddf5a30
source-git-commit: bae0eeac349fe3c266d868f8d94c5e033390a661
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---

# Configura nel dashboard

Puoi personalizzare [!DNL Payment Services] in base alle tue esigenze, con utili opzioni di configurazione nel dashboard.

Quando fai clic su [!UICONTROL Settings] nel dashboard puoi configurare rapidamente [!DNL Payment Services] per Adobe Commerce e Magenti Open Source. Queste opzioni di configurazione si applicano solo all’ambiente impostato nel [!UICONTROL Payment mode] nelle impostazioni generali.

Consulta la sezione [[!UICONTROL General] sezione impostazioni](#general-settings) per ulteriori informazioni.

>[!IMPORTANT]
>
> Per la configurazione multi-store o legacy, fai riferimento alla [Configura nell’amministratore](configure-admin.md) argomento.

## Configurare i servizi di pagamento

È possibile attivare [!DNL Payment Services] per il tuo sito web e abilita test sandbox o pagamenti live in [!UICONTROL General] sezione delle impostazioni .

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Vista dashboard](assets/payment-services-menu-small.png)

1. Nel dashboard, fai clic su **[!UICONTROL Settings]** in alto a destra nella pagina.

   La _[!UICONTROL General]_include le opzioni di configurazione utilizzate per impostare [!DNL Payment Services] come metodo di pagamento.

1. Per l’opzione di attivazione/disattivazione nella parte superiore (**[!UICONTROL Enable Payment Services as payment method]**), impostala su `Yes` per abilitare [!DNL Payment Services] per il sito web.

1. Per **Modalità di pagamento**, imposta su `Sandbox` se stai ancora testando [!DNL Payment Services] per il vostro negozio o `Production` se sei pronto per abilitare i pagamenti live.

   >[!WARNING]
   >
   >Le [!UICONTROL Sandbox Merchant ID] e [!UICONTROL Production Merchant ID] sono generati automaticamente e presenti nei rispettivi campi al termine dell’onboarding per la sandbox e/o la produzione. Non rimuovere o modificare questi ID.

1. Per modificare le impostazioni predefinite per le funzioni di pagamento e la visualizzazione della vetrina, impostare le opzioni aggiuntive necessarie:

   - [Campi carta di credito](#credit-card-fields)
   - [Pulsanti smart PayPal](#paypal-smart-buttons)
   - [Stile pulsante](#button-style)

1. Per salvare le modifiche, fai clic su **[!UICONTROL Save]** in alto a destra nella pagina.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

### Campi carta di credito

La [!UICONTROL Credit Card Fields] le opzioni di pagamento forniscono un pagamento semplice e sicuro per le modalità di pagamento con carta di credito o con carta di debito.

Vedi [Opzioni di pagamento](payments-options.md#paypal-smart-buttons) per ulteriori informazioni.

1. Per **[!UICONTROL Checkout title]**, immettere il testo (se necessario) per modificare il nome del metodo di pagamento visualizzato durante l&#39;estrazione.
1. A [imposta l&#39;azione di pagamento](production.md#set-payment-services-as-payment-method), set **[!UICONTROL Payment action]** a `Authorize` o `Authorize and Capture`.
1. Per **[!UICONTROL Debug Mode]**, attiva il selettore per attivare la modalità di debug.
1. Per salvare le modifiche, fai clic su **[!UICONTROL Save]** in alto a destra nella pagina.
1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

### Pulsanti smart PayPal

La [!DNL PayPal Smart Buttons] le opzioni di pagamento forniscono al cliente un processo di pagamento semplice, rapido e sicuro. Vedi [Opzioni di pagamento](payments-options.md#paypal-smart-buttons) per ulteriori informazioni.

Puoi abilitare le opzioni di pagamento dei pulsanti intelligenti PayPal all&#39;interno del dashboard:

1. Per modificare il nome del metodo di pagamento come mostrato durante il pagamento, modifica il valore nel **[!UICONTROL Checkout Title]** campo .
1. A [imposta l&#39;azione di pagamento](production.md#set-payment-services-as-payment-method), set **[!UICONTROL Payment action]** a `Authorize` o `Authorize and Capture`.
1. Usa i selettori di attivazione/disattivazione [!DNL PayPal smart button] caratteristiche di visualizzazione:
   - **[!UICONTROL Show buttons on product detail page]**
   - **[!UICONTROL Show buttons in mini cart preview]**
   - **[!UICONTROL Show buttons on cart page]**
   - **[!UICONTROL Show Venmo button]**.
   - **[!UICONTROL PayPal Pay Later enabled]** per abilitare l’opzione per visualizzare il pulsante durante il pagamento.

1. Per modificare la variabile [Messaggi di pagamento in un secondo momento](payments-options.md#pay-later-button) (se desiderato), attiva/disattiva la **[!UICONTROL Display Pay Later message]** opzione .
1. Per abilitare la modalità di debug, fai clic su **[!UICONTROL Debug Mode]**,
1. Per salvare le modifiche, fai clic su **[!UICONTROL Save]** in alto a destra nella pagina.
1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

### Stile pulsante

Puoi anche configurare le _[!UICONTROL Button style]_opzioni dei pulsanti intelligenti PayPal all&#39;interno del dashboard:

1. Per modificare la variabile **[!UICONTROL Layout]**, seleziona `Vertical` o `Horizontal`.
1. Per abilitare l’asse di visualizzazione in un layout orizzontale, fai clic su **[!UICONTROL Show tagline]**.
1. Per modificare il **[!UICONTROL Color]**, seleziona l’opzione di colore desiderata.
1. Per modificare la variabile **[!UICONTROL Shape]**, seleziona `Pill` o `Rect`.
1. Per abilitare il selettore dell’altezza del pulsante, fai clic su **[!UICONTROL Responsive button height]**.
1. Per modificare il **[!UICONTROL Label]**, seleziona l’opzione di etichetta desiderata.
1. Per salvare le modifiche, fai clic su **[!UICONTROL Save]** in alto a destra nella pagina.
1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

Puoi configurare [!DNL PayPal Smart Buttons] nell’amministratore o nel dashboard. Vedi [Guida allo stile dei pulsanti di PayPal](https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/) per ulteriori informazioni.
