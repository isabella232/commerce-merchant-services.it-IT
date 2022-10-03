---
title: Report stato del pagamento dell'ordine
description: Utilizza il rapporto sullo stato del pagamento dell'ordine per avere visibilità sullo stato del pagamento degli ordini e identificare eventuali problemi potenziali.
role: User
level: Intermediate
exl-id: 192e47b9-d52b-4dcf-a720-38459156fda4
source-git-commit: 39c0140961fa9de5075087bbc3fbec0e14560860
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 0%

---

# Report stato del pagamento dell&#39;ordine

[!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] offre un reporting completo per ottenere una visione chiara degli ordini e dei pagamenti del tuo negozio.

![Visualizzazione rapporti finanziari](assets/report-view.png)

Il rapporto sullo stato del pagamento dell&#39;ordine ti aiuta a capire facilmente dove si trova un ordine specifico all&#39;interno del flusso di processo dell&#39;ordine al contante. Questo rapporto ti consente di visualizzare rapidamente lo stato dei pagamenti degli ordini e di identificare eventuali problemi potenziali.

Non è necessario aprire più visualizzazioni per incrociare manualmente ordini e pagamenti con riferimenti incrociati. [!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] consente di ottenere una panoramica degli ordini e dei pagamenti, il tutto all&#39;interno del rapporto sullo stato del pagamento dell&#39;ordine.

Vedere gli stati di pagamento, gli stati di fatturazione e spedizione, gli stati di rimborso, gli stati di controversia e altro ancora all&#39;interno di questo rapporto nell&#39;Amministratore.

È possibile scaricare le transazioni dello stato dell&#39;ordine in un formato file .csv da utilizzare nel software di contabilità o gestione degli ordini esistente.

>[!NOTE]
>
>Non è possibile visualizzare i rapporti finanziari se non si [Modalità attiva integrata](production.md#enable-live-payments) per [!DNL Payment Services].

## Dati utilizzati nel rapporto

La [!DNL Payment Services] Il modulo utilizza i dati degli ordini e li combina con i dati di pagamento aggregati provenienti da altre fonti (incluso PayPal), per fornire report significativi e molto utili.

I dati dell&#39;ordine vengono esportati e mantenuti nel servizio di pagamento. Quando [modificare o aggiungere gli stati dell’ordine](https://docs.magento.com/user-guide/sales/order-status-custom.html){target=&quot;_blank&quot;} o [modificare una visualizzazione store](https://docs.magento.com/user-guide/stores/stores-all-view-edit.html){target=&quot;_blank&quot;}, [archiviare](https://docs.magento.com/user-guide/stores/store-information.html){target=&quot;_blank&quot;}, o nome del sito web, questi dati vengono combinati con i dati di pagamento e il rapporto sullo stato del pagamento dell&#39;ordine viene compilato con le informazioni combinate.

Questo processo prevede due passaggi:

1. L&#39;indice viene modificato o `ON SAVE` (ogni volta che le informazioni sull&#39;ordine o sul negozio vengono modificate) o `BY SCHEDULE` (su una pianificazione cron preconfigurata), a seconda di come è configurato in [Gestione dell&#39;indice](https://docs.magento.com/user-guide/system/index-management.html){target=&quot;_blank&quot;} nell&#39;amministratore.

   Per impostazione predefinita, l’indicizzazione dei dati si verifica `ON SAVE`, il che significa che ogni volta che qualcosa cambia nell&#39;ordine, lo stato dell&#39;ordine, la vista del negozio, il negozio o il sito web, il processo di reindicizzazione avviene immediatamente.

1. I dati indicizzati vengono inviati al servizio di pagamento, che viene quindi compilato nel rapporto sullo stato del pagamento dell&#39;ordine.

Gli unici dati esportati e raccolti a scopo di reporting sono i dati utilizzati dal rapporto sullo stato del pagamento dell&#39;ordine.

>[!NOTE]
>
>I dati visualizzati in questa tabella vengono ordinati in ordine decrescente (`DESC`) per impostazione predefinita utilizzando `ORDER DATE`. La `ORDER DATE` è la marca temporale della data di creazione dell’ordine.

### Configurare l’esportazione di dati

Anche se, per impostazione predefinita, la reindicizzazione avviene in `ON SAVE` è consigliabile indicizzare in `BY SCHEDULE` modalità. La `BY SCHEDULE` l&#39;indice viene eseguito su una pianificazione cron di un minuto e tutti i dati modificati vengono visualizzati nel rapporto sullo stato dell&#39;ordine entro due minuti da qualsiasi modifica dei dati. Questa reindicizzazione programmata ti aiuta a ridurre qualsiasi sforzo sul tuo negozio, specialmente se hai un grande volume di ordini in arrivo, perché si verifica su una pianificazione (non come ogni ordine è posizionato).

È possibile modificare la modalità indice—`ON SAVE` o `BY SCHEDULE`—[nell’amministratore](https://docs.magento.com/user-guide/system/index-management.html#change-the-index-mode){target=&quot;_blank&quot;}.

Per scoprire come configurare l’esportazione dei dati, consulta [Configurazione della riga di comando](configure-cli.md#configure-data-export).

## Disponibilità

Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Order payment status]** per visualizzare gli stati di pagamento degli ordini.

![Stato del pagamento dell’ordine nell’amministratore](assets/order-payment-status-report.png)

## Seleziona origine dati

Nella visualizzazione del rapporto sullo stato del pagamento dell&#39;ordine, è possibile selezionare l&#39;origine dati—_[!UICONTROL Live]_o_[!UICONTROL Sandbox]_- per i quali visualizzare i risultati del rapporto.

![Selezione di origini dati](assets/datasource.png)

Se _[!UICONTROL Live]_è l’origine dati selezionata, è possibile visualizzare le informazioni sui rapporti per gli archivi che utilizzano [!DNL Payment Services] in_[!UICONTROL Live]_ modalità. Se [!UICONTROL Sandbox]_ è l’origine dati selezionata, puoi visualizzare le informazioni sul rapporto per l’ambiente Sandbox.

Le selezioni dell’origine dati funzionano come segue:

* Se non hai negozi che utilizzano [!DNL Payment Services] in modalità Live, la selezione dell’origine dati viene impostata automaticamente su _[!UICONTROL Sandbox]_.
* Se sono presenti negozi (uno o più) che utilizzano [!DNL Payment Services] in modalità Live, la selezione dell’origine dati viene impostata automaticamente su _[!UICONTROL Live]_.
* Le esportazioni dei rapporti rispettano sempre la selezione dell’origine dati.

Selezione dell&#39;origine dati per [!UICONTROL Order Payment Status] rapporto:

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Fai clic su **[!UICONTROL Data source]** e seleziona _[!UICONTROL Live]_o_[!UICONTROL Sandbox]_.

   I risultati del report vengono rigenerati in base all&#39;origine dati selezionata.

## Personalizza arco temporale date

Dalla visualizzazione del rapporto sullo stato del pagamento dell&#39;ordine, è possibile personalizzare l&#39;intervallo temporale degli stati che si desidera visualizzare selezionando date specifiche. Per impostazione predefinita, nella griglia sono visualizzati 30 giorni degli stati di pagamento degli ordini.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Fai clic sul pulsante **[!UICONTROL Order dates]** filtro selettore calendario.
1. Scegli l’intervallo di date applicabile.
1. Visualizza gli stati di pagamento dell&#39;ordine per le date specificate nella griglia.

## Mostra e nascondi colonne

Il rapporto Stato pagamento ordine mostra tutte le colonne di informazioni disponibili per impostazione predefinita. È tuttavia possibile personalizzare le colonne visualizzate nel rapporto.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Fai clic sul pulsante _Impostazioni colonna_ icona (![icona delle impostazioni colonna](assets/column-settings.png)).
1. Per personalizzare le colonne visualizzate nel rapporto, selezionare o deselezionare le colonne nell’elenco.

   Il rapporto sullo stato del pagamento dell&#39;ordine mostrerà immediatamente tutte le modifiche apportate nel menu Impostazioni colonna. Le preferenze della colonna vengono salvate e rimangono attive se ci si allontana dalla visualizzazione del rapporto.

## Visualizzare gli stati

La visualizzazione del rapporto sullo stato del pagamento dell&#39;ordine mostra informazioni complete sullo stato della transazione e sullo stato del pagamento per ogni ordine di Servizi di pagamento.

### Stato della transazione

Per impostazione predefinita, nella griglia sono visualizzati 30 giorni degli stati di pagamento degli ordini.

Scorri verso sinistra e verso destra per visualizzare [informazioni sullo stato del pagamento dell&#39;ordine](#column-descriptions), inclusa la data dell’ordine, la data autorizzata, fatturata, spedita, lo stato del pagamento e altro ancora.

Il numero di righe restituite in una ricerca, o visualizzate negli stati di pagamento degli ordini di 30 giorni predefiniti, viene visualizzato sopra la griglia di visualizzazione dello stato del pagamento dell&#39;ordine accanto al filtro del selettore del calendario delle date dell&#39;ordine.

### Stato della retribuzione

La colonna Stato Pagamento mostra lo stato corrente per qualsiasi pagamento. A `Capture failed` il pagamento mostra lo stato di un avviso rosso e un `Voided` il pagamento presenta uno stato di avviso grigio.

### Stato della restituzione

La colonna Stato Rimborso mostra lo stato corrente per qualsiasi rimborso. A `Capture failed` il pagamento mostra lo stato di un avviso rosso e un `Voided` il pagamento presenta uno stato di avviso grigio.

## Update report data

La visualizzazione del rapporto sullo stato del pagamento dell&#39;ordine mostra un _[!UICONTROL Last updated]_marca temporale che mostra l’ultima volta che le informazioni del rapporto sono state aggiornate. Per impostazione predefinita, i dati del rapporto sullo stato del pagamento dell&#39;ordine vengono aggiornati automaticamente ogni tre ore.

È inoltre possibile forzare manualmente un aggiornamento dei dati del report sullo stato del pagamento dell&#39;ordine per visualizzare le informazioni più aggiornate sul report.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Fai clic sul pulsante _Aggiorna_ icona (![icona di aggiornamento](assets/refresh-button-med.png)).

   I dati del rapporto sullo stato del pagamento dell&#39;ordine vengono aggiornati, e *[!UICONTROL Update complete]* viene visualizzata una conferma e le informazioni più recenti sono presenti nella griglia.

## Visualizza controversie

È possibile visualizzare eventuali controversie sugli ordini del negozio e accedere al Centro di risoluzione PayPal per intervenire su di essi, dall&#39;interno del rapporto sullo stato del pagamento dell&#39;ordine.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Passa a **[!UICONTROL Disputes column]**.
1. Visualizza eventuali controversie per un ordine specifico e visualizza [lo stato della controversia](#order-payment-status-information).
1. Fai clic sul collegamento ID controversia (a partire da _PP-D_) per passare al [Centro di risoluzione PayPal](https://www.paypal.com/us/smarthelp/article/what-is-the-resolution-center-faq3327).
1. Adottare, se necessario, le misure adeguate per la controversia.

   Per ordinare le controversie in base allo stato, fare clic sull&#39;intestazione della colonna Dispute.

## Download degli stati di pagamento dell&#39;ordine

È possibile scaricare un file .csv con tutti gli stati visibili nella griglia di visualizzazione dello stato del pagamento dell&#39;ordine, sia che si visualizzino i 30 giorni di stato predefiniti o un arco temporale personalizzato.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Se desideri visualizzare gli stati per un periodo di tempo diverso dagli ultimi 30 giorni, [personalizzare l’intervallo di tempo per gli stati](#customize-dates-timeframe).
1. Fai clic sul pulsante _Scarica_ (![icona di download](assets/icon-download.png)).

Gli stati di pagamento dell&#39;ordine vengono scaricati in formato .csv .

<!-- ## Default order payment status timeframes

These order payment status timeframes are currently available in [!DNL Payment Services].

| Report       | Description          |
| ------------ | -------------------- |
| Yesterday | Available from the Order payment status dates selector, this shows information for the prior date. |
| | Today | Available from the Order payment status dates selector, this shows information for the current day. |
| Last 7 days | Available from the Order payment status dates selector, this shows information for the last seven days. |
| Last 30 days | Available from the Order payment status dates selector and by default in the Order payment statuses view, this shows information for the last 30 days. |
| Last 90 days | Available from the Order payment status dates selector, this shows information for the last 90 days. |
| Year to date | Available from the Order payment status dates selector, this shows information for the the entire year to date. |
| Custom range | Available from the Order payment status dates selector, this can be filtered to show a custom date range. |
-->

## Informazioni sullo stato del pagamento dell&#39;ordine

La visualizzazione Stato pagamento ordine mostra informazioni complete su ogni stato visualizzato nella griglia.

### Descrizioni delle colonne

I rapporti sullo stato del pagamento degli ordini includono le seguenti informazioni.

| Colonna | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL Order ID] | ID ordine commerciale<br> <br>Per visualizzare i dati correlati [info ordine](https://docs.magento.com/user-guide/sales/orders.html){target=&quot;_blank&quot;}, fai clic sull&#39;ID. |
| [!UICONTROL Order Date] | Timestamp data ordine |
| [!UICONTROL Authorized Date] | Data e ora dell&#39;autorizzazione di pagamento |
| [!UICONTROL Order Status] | Commerce corrente [stato dell&#39;ordine](https://docs.magento.com/user-guide/sales/order-status.html){target=&quot;_blank&quot;} |
| [!UICONTROL Invoiced] | Stato della fattura dell&#39;ordine:*[!UICONTROL No]*, *[!UICONTROL Partial]* oppure *[!UICONTROL Yes]* |
| [!UICONTROL Shipped] | Stato di spedizione dell&#39;ordine—*[!UICONTROL No]*, *[!UICONTROL Partial]* oppure *[!UICONTROL Yes]* |
| [!UICONTROL Order Amt] | Importo totale complessivo dell&#39;ordine |
| [!UICONTROL Cur] | Tipo di valuta dell&#39;ordine |
| [!UICONTROL Pay Status] | Stato del pagamento per un ordine specifico |
| [!UICONTROL Paid Amt] | Importo pagato su un ordine |
| [!UICONTROL Cur] | Tipo di valuta dell&#39;importo pagato su un ordine |
| [!UICONTROL Refund Status] | Stato del rimborso su un ordine (ad esempio informazioni provenienti da restituzioni, RMA e note di credito)—   *[!UICONTROL Requires refund]*, *[!UICONTROL Refund requested]*, *[!UICONTROL Refunded]*, *[!UICONTROL Refund failed]* oppure *[!UICONTROL Voided]* |
| [!UICONTROL Refund Amount] | Importo totale rimborsato per un ordine |
| [!UICONTROL Cur] | Tipo di valuta dell&#39;importo rimborsato per un ordine |
| [!UICONTROL Disputes] | Status di qualsiasi controversia su un ordine (informazioni da controversie e commissioni)—*[!UICONTROL Open]*, *[!UICONTROL Waiting for buyer response]*, *[!UICONTROL Waiting for seller response]*, *[!UICONTROL Under review]*, *[!UICONTROL Resolved]* oppure *[!UICONTROL Other]* |
| [!UICONTROL Payment Method] | Metodo di pagamento utilizzato nella transazione Commerce per un ordine |
| [!UICONTROL Website] | Sito Web da cui è stato effettuato l&#39;ordine |
| [!UICONTROL Store] | Archivio da cui è stato effettuato l&#39;ordine |
| [!UICONTROL Store View] | Vista store da cui è stato effettuato l’ordine |
