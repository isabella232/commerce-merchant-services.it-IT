---
title: Impostazioni dei servizi di pagamento
description: Dopo l'installazione, è possibile configurare [!DNL Payment Services] nella casa.
role: Admin, User
level: Intermediate
exl-id: 108f2b24-39c1-4c87-8deb-d82ee1c24d55
source-git-commit: 0bd6137ec7cd5da04ae6a48f06cd5aec254b46ef
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 0%

---

# Impostazioni

Puoi personalizzare [!DNL Payment Services] per soddisfare le tue esigenze con le impostazioni disponibili nella sezione [!DNL Payment Services] Casa.

Per configurare [!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] click **[!UICONTROL Settings]**. Queste opzioni di configurazione si applicano solo all’ambiente impostato nel _[!UICONTROL Payment mode]_campo_[!UICONTROL Settings]_ > _[!UICONTROL General]_.

>[!IMPORTANT]
>
> Per la configurazione multi-store o legacy, fai riferimento alla [Configura nell’amministratore](configure-admin.md) argomento.

## Abilita servizi di pagamento

È possibile attivare [!DNL Payment Services] per il tuo sito web e abilita test sandbox o pagamenti live, nel [!UICONTROL General] sezione .

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Vista Home](assets/payment-services-menu-small.png)

1. Clic **[!UICONTROL Settings]**. Vedi [Introduzione a [!DNL Payment Services] Pagina principale](payments-home.md) per ulteriori informazioni.

   La _[!UICONTROL General]_include le impostazioni utilizzate per abilitare [!DNL Payment Services] come metodo di pagamento.

1. Per abilitare [!DNL Payment Services] come metodo di pagamento per il tuo negozio, nel _[!UICONTROL General]_sezione, interruttore (**[!UICONTROL Enable Payment Services as payment method]**) a `Yes`.

1. Se stai ancora testando [!DNL Payment Services] per il tuo negozio, imposta **Modalità di pagamento** a `Sandbox`. Se sei pronto per abilitare i pagamenti live, impostalo su `Production`.

   >[!NOTE]
   >
   >Le _[!UICONTROL Sandbox Merchant ID]_e_[!UICONTROL Production Merchant ID]_ sono generati automaticamente e presenti nei rispettivi campi al termine dell’onboarding per la sandbox e/o la produzione.

1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

È ora possibile modificare le impostazioni predefinite per [opzioni di pagamento](#configure-payment-options) funzioni e visualizzazione della vetrina.

### Opzioni di configurazione generali

| Campo | Ambito | Descrizione |
|---|---|---|
| [!UICONTROL Enable] | sito web | Attiva o disattiva [!DNL Payment Services] per il sito web. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Payment mode] | vista store | Imposta il metodo o l&#39;ambiente per l&#39;archivio. Opzioni: [!UICONTROL Sandbox] / [!UICONTROL Production] |
| [!UICONTROL Sandbox Merchant ID] | vista store | Il tuo ID commerciante sandbox, generato automaticamente durante l’onboarding della sandbox. |
| [!UICONTROL Production Merchant ID] | vista store | Il tuo ID commerciante di produzione, generato automaticamente durante l’onboarding della sandbox. |

## Configurare le opzioni di pagamento

Ora che hai abilitato Servizi di pagamento per il tuo sito web, puoi modificare le impostazioni predefinite per le funzioni di pagamento e la visualizzazione della vetrina.

### Campi carta di credito

La _[!UICONTROL Credit Card Fields]_Le impostazioni forniscono un&#39;opzione di pagamento semplice e sicura per i metodi di pagamento con carta di credito o con carta di debito.

Vedi [Opzioni di pagamento](payments-options.md#credit-card-fields) per ulteriori informazioni.

1. Seleziona la vista Store nella **[!UICONTROL Scope]** menu a discesa, per il quale si desidera abilitare un metodo di pagamento.
1. Per modificare il nome del metodo di pagamento visualizzato durante il pagamento, modificare il valore nel **[!UICONTROL Checkout title]** campo .
1. A [imposta l&#39;azione di pagamento](production.md#set-payment-services-as-payment-method), interruttore **[!UICONTROL Payment action]** a `Authorize` o `Authorize and Capture`.
1. Per abilitare la modalità di debug, attiva **[!UICONTROL Debug Mode]** selettore.
1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

#### Opzioni di configurazione

| Campo | Ambito | Descrizione |
|---|---|---|
| [!UICONTROL Title] | vista store | Aggiungere il testo da visualizzare come titolo per questa opzione di pagamento nella visualizzazione Metodo di pagamento durante il pagamento. Opzioni: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | sito web | La [azione di pagamento](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target=&quot;_blank&quot;} per il metodo di pagamento specificato. Opzioni: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Debug Mode] | sito web | Attiva o disattiva la modalità di debug. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |

### Pulsanti di pagamento

La [!DNL PayPal Smart Buttons] le opzioni di pagamento forniscono al cliente un processo di pagamento semplice, rapido e sicuro. Vedi [Opzioni di pagamento](payments-options.md#paypal-smart-buttons) per ulteriori informazioni.

Puoi abilitare e configurare le opzioni di pagamento dei pulsanti intelligenti PayPal:

1. Seleziona la vista Store nella **[!UICONTROL Scope]** menu a discesa, per il quale si desidera abilitare un metodo di pagamento.
1. Per modificare il nome del metodo di pagamento come mostrato durante il pagamento, modifica il valore nel **[!UICONTROL Checkout Title]** campo .
1. A [imposta l&#39;azione di pagamento](production.md#set-payment-services-as-payment-method), interruttore **[!UICONTROL Payment action]** a `Authorize` o `Authorize and Capture`.
1. Usa i selettori di attivazione/disattivazione [!DNL PayPal smart button] caratteristiche di visualizzazione:
   - **[!UICONTROL Show PayPal buttons on product detail page]**
   - **[!UICONTROL Show PayPal buttons in mini-cart preview]**
   - **[!UICONTROL Show PayPal buttons on cart page]**
   - **[!UICONTROL Show PayPal Pay Later button]**
   - **[!UICONTROL Show PayPal Pay Later message]**
   - **[!UICONTROL Show Venmo button]**
   - **[!UICONTROL Show Apple Pay button]**

      >[!NOTE]
      >
      > Per utilizzare Apple Paga [deve avere un account Apple Developer](test-validate.md#test-in-sandbox-environment) (completo di false carte di credito e informazioni di fatturazione) per testarlo. Quando sei pronto a utilizzare Apple Pay in sandbox *o* modalità di produzione, dopo aver completato [test e convalida](test-validate.md), contatta il tuo rappresentante commerciale per abilitarlo per i tuoi store live.

      Quando si attiva/disattiva la visibilità dei pulsanti di pagamento o il messaggio PayPal Pay Later, viene visualizzata un&#39;anteprima visiva della configurazione nella parte inferiore della pagina Settings (Impostazioni).

1. Per abilitare la modalità di debug, attiva **[!UICONTROL Debug Mode]** selettore.
1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

#### Opzioni di configurazione

| Campo | Ambito | Descrizione |
|---|---|---|
| [!UICONTROL Title] | vista store | Aggiungere il testo da visualizzare come titolo per questa opzione di pagamento nella visualizzazione Metodo di pagamento durante il pagamento. Opzioni: campo di testo |
| [!UICONTROL Payment Action] | sito web | La [azione di pagamento](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target=&quot;_blank&quot;} per il metodo di pagamento specificato. Opzioni: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Show PayPal buttons on product detail page] | vista store | Attiva o disattiva [!DNL PayPal Smart Buttons] nella pagina dei dettagli del prodotto. Opzioni: [!UICONTROL  Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal buttons in mini-cart preview] | vista store | Attiva o disattiva [!DNL PayPal Smart Buttons] nell’anteprima del mini-carrello. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal buttons on cart page] | vista store | Attiva o disattiva [!DNL PayPal Smart Buttons] nella pagina del carrello. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal Pay Later button] | vista store | Attiva o disattiva l&#39;aspetto dell&#39;opzione di pagamento successivo in cui vengono visualizzati i pulsanti di pagamento. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal Pay Later Message] | sito web | Attiva o disattiva la messaggistica Paga in seguito nel carrello, nella pagina del prodotto, nel mini-carrello e durante il flusso di pagamento. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show Venmo button] | vista store | Attiva o disattiva l&#39;opzione di pagamento Venmo in cui vengono visualizzati i pulsanti di pagamento. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show Apple Pay button] | vista store | Attiva o disattiva l&#39;opzione Pagamento Apple in cui vengono visualizzati i pulsanti di pagamento. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Debug Mode] | sito web | Attiva o disattiva la modalità di debug. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |

### Stile pulsante

Puoi anche configurare le _[!UICONTROL Button style]_opzioni dei pulsanti intelligenti PayPal:

1. Per modificare la variabile **[!UICONTROL Layout]**, seleziona `Vertical` o `Horizontal`.

   >[!NOTE]
   >
   > Se lo stile del pulsante è configurato come `Horizontal` e il tuo negozio è configurato per mostrare più pulsanti intelligenti PayPal, puoi visualizzare solo due pulsanti sulla pagina del prodotto, la pagina di pagamento e il mini-carrello, e un pulsante visualizzato nel carrello.

1. Per attivare la linea di graduazione in un layout orizzontale, attiva la **[!UICONTROL Show tagline]** selettore.
1. Per modificare il **[!UICONTROL Color]**, seleziona l’opzione di colore desiderata.
1. Per modificare il **[!UICONTROL Shape]**, seleziona `Pill` o `Rect`.
1. Per abilitare il selettore dell’altezza del pulsante, attiva/disattiva **[!UICONTROL Responsive button height]** selettore.
1. Per modificare il **[!UICONTROL Label]**, seleziona l’opzione di etichetta desiderata.

   Quando si modificano le opzioni di configurazione per layout, colore, forma, altezza ed etichetta, viene visualizzata un&#39;anteprima visiva della configurazione nella parte inferiore della pagina Impostazioni.

1. Clic **[!UICONTROL Save]**.

   Se tenti di allontanarti da questa visualizzazione senza salvare le modifiche, viene visualizzato un modale che richiede di ignorare le modifiche, continuare a modificare o salvare le modifiche.

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

Puoi configurare [!DNL PayPal Smart Buttons] stile [nella configurazione Legacy in Admin](configure-admin.md#configure-paypal-smart-buttons) o qui [!DNL Payment Services Home]. Vedi [Guida allo stile dei pulsanti di PayPal](https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/) per ulteriori informazioni sulle opzioni.

#### Opzioni di configurazione

| Campo | Ambito | Descrizione |
|--- |--- |--- |
| [!UICONTROL Layout] | Visualizzazione store | Definire lo stile del layout dei pulsanti di pagamento. Opzioni: [!UICONTROL Vertical] / [!UICONTROL Horizontal] |
| [!UICONTROL Tagline] | Visualizzazione store | Attiva/disattiva la linea di tag. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Color] | Visualizzazione store | Definire il colore dei pulsanti di pagamento. Opzioni: [!UICONTROL Blue] / [!UICONTROL Gold] / [!UICONTROL Silver] / [!UICONTROL White] / [!UICONTROL Black] |
| [!UICONTROL Shape] | Visualizzazione store | Definire la forma dei pulsanti di pagamento. Opzioni: [!UICONTROL Rectangular] / [!UICONTROL Pill] |
| [!UICONTROL Responsive Button Height] | Visualizzazione store | Definisce se i pulsanti di pagamento utilizzano un&#39;altezza predefinita. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Height] | Visualizzazione store | Definire l’altezza dei pulsanti di pagamento. Valore predefinito: nessuno |
| [!UICONTROL Label] | Visualizzazione store | Definire l’etichetta visualizzata nei pulsanti di pagamento. Opzioni: [!UICONTROL PayPal] / [!UICONTROL Checkout] / [!UICONTROL Buynow] / [!UICONTROL Pay] / [!UICONTROL Installment] |

## Utilizzare più account PayPal

In Servizi di pagamento è possibile utilizzare più account PayPal all&#39;interno di **uno** conto commerciale a livello di sito web. Ad esempio, se gestisci i tuoi store in più paesi (che utilizzano diversi) [valute](https://docs.magento.com/user-guide/stores/currency.html)) o desideri utilizzare Adobe Commerce per alcune parti della tua attività ma non per *tutto*, puoi configurare il tuo account commerciale per l&#39;utilizzo di più account PayPal.

Vedi [Sito, archiviazione e visualizzazione ambito](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html) per ulteriori informazioni sulla gerarchia di siti web, store e viste store.

Il rappresentante commerciale può creare un nuovo [scope](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings) per il tuo conto commerciale e a bordo del sito aggiuntivo con PayPal in modo che uno qualsiasi dei pulsanti PayPal che configuri per apparire verrà mostrato sul tuo sito. Contatta il tuo rappresentante commerciale per assistenza sull&#39;utilizzo di più account PayPal per i tuoi siti web.
