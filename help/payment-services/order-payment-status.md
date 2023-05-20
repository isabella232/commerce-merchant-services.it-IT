---
title: Rapporto Stato pagamento ordine
description: Utilizzare il rapporto Stato pagamento ordine per ottenere visibilità sullo stato di pagamento degli ordini e identificare eventuali problemi.
role: User
level: Intermediate
exl-id: 192e47b9-d52b-4dcf-a720-38459156fda4
source-git-commit: 817a01e98876bddf5f41a253501984539b3351cd
workflow-type: tm+mt
source-wordcount: '1416'
ht-degree: 0%

---

# Rapporto Stato pagamento ordine

[!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] offre una funzione di reporting completa che ti permette di avere una visione chiara degli ordini e dei pagamenti del tuo negozio.

![Visualizzazione dei report finanziari](assets/reports-justpayouts.png)

Il rapporto Stato pagamento ordine consente di comprendere facilmente la posizione di un ordine specifico all&#39;interno del flusso di elaborazione del contante dell&#39;ordine. Questo report consente di visualizzare rapidamente lo stato dei pagamenti degli ordini e di identificare eventuali problemi.

Non è necessario aprire più viste per eseguire manualmente il riferimento incrociato di ordini e pagamenti. [!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] consente di ottenere una visione d&#39;insieme degli ordini e dei pagamenti, il tutto all&#39;interno del rapporto sullo stato del pagamento dell&#39;ordine.

Vedi stati dei pagamenti, stati fatturati e spediti, stati dei rimborsi, stati delle controversie e altro ancora, il tutto all&#39;interno di questo rapporto in Amministrazione.

È possibile scaricare le transazioni relative allo stato del pagamento dell&#39;ordine in un formato di file .csv da utilizzare nel software di contabilità o di gestione degli ordini esistente.

>[!NOTE]
>
>Non è possibile visualizzare i rapporti finanziari se non [Modalità Live onboarded e attivata](production.md#enable-live-payments) per [!DNL Payment Services].

## Dati utilizzati nel rapporto

Il [!DNL Payment Services] Il modulo utilizza i dati degli ordini e li combina con i dati di pagamento aggregati provenienti da altre fonti (incluso PayPal) per fornire rapporti significativi e molto utili.

I dati dell’ordine vengono esportati e memorizzati nel servizio di pagamento. Quando [modificare o aggiungere stati degli ordini](https://docs.magento.com/user-guide/sales/order-status-custom.html){target="_blank"} or [edit a store view](https://docs.magento.com/user-guide/stores/stores-all-view-edit.html){target="_blank"}, [store](https://docs.magento.com/user-guide/stores/store-information.html){target="_blank"}, o nome del sito Web, tali dati vengono combinati con i dati di pagamento e il rapporto sullo stato del pagamento dell&#39;ordine viene compilato con le informazioni combinate.

Questo processo prevede due fasi:

1. L’indice viene modificato in base ai dati `ON SAVE` (ogni volta che le informazioni dell&#39;ordine o del negozio vengono modificate) o `BY SCHEDULE` (secondo una pianificazione cron preconfigurata), a seconda di come è configurato in [Gestione indice](https://docs.magento.com/user-guide/system/index-management.html){target="_blank"} in Admin.

   Per impostazione predefinita, si verifica l’indicizzazione dei dati `ON SAVE`, il che significa che ogni volta che qualcosa cambia nell’ordine, nello stato dell’ordine, nella visualizzazione del negozio, nel negozio o nel sito web, il processo di reindicizzazione avviene immediatamente.

1. I dati indicizzati vengono inviati al servizio di pagamento, che quindi compila il rapporto Stato pagamento ordine.

Gli unici dati esportati e confrontati a scopo di reporting sono i dati utilizzati dal rapporto Stato pagamento ordine.

>[!NOTE]
>
>I dati mostrati in questa tabella sono ordinati in ordine decrescente (`DESC`) per impostazione predefinita utilizzando `ORDER DATE`. Il `ORDER DATE` è la data e l’ora in cui è stato creato l’ordine.

### Configurare l’esportazione dei dati

Anche se, per impostazione predefinita, la reindicizzazione si verifica in `ON SAVE` modalità, si consiglia di indicizzare in `BY SCHEDULE` modalità. Il `BY SCHEDULE` L&#39;indice viene eseguito con una pianificazione cron di un minuto e tutti i dati modificati vengono visualizzati nel rapporto sullo stato dell&#39;ordine entro due minuti dalla modifica dei dati. Questa reindicizzazione programmata consente di ridurre qualsiasi tensione sul negozio, soprattutto se si dispone di un grande volume di ordini in entrata, perché avviene secondo un programma (non come ogni ordine viene effettuato).

È possibile modificare la modalità indice:`ON SAVE` o `BY SCHEDULE`—[in Admin](https://docs.magento.com/user-guide/system/index-management.html#change-the-index-mode){target="_blank"}.

Per informazioni su come configurare l’esportazione dei dati, consulta [Configurazione della riga di comando](configure-cli.md#configure-data-export).

## Disponibilità

Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Order payment status]** per visualizzare gli stati di pagamento degli ordini.

![Stati di pagamento degli ordini nell’amministratore](assets/order-payment-status-report.png)

## Seleziona origine dati

Nella vista del rapporto Stato pagamento ordine è possibile selezionare l&#39;origine dati:_[!UICONTROL Live]_o_[!UICONTROL Sandbox]_- per il quale si desidera visualizzare i risultati del rapporto.

![Selezione di origini dati](assets/datasource.png)

Se _[!UICONTROL Live]_è l&#39;origine dati selezionata, è possibile visualizzare le informazioni del report per gli archivi che utilizzano [!DNL Payment Services] in_[!UICONTROL Live]_ modalità. Se [!UICONTROL Sandbox]_ è l’origine dati selezionata, puoi visualizzare le informazioni del rapporto per il tuo ambiente Sandbox.

Le selezioni delle origini dati funzionano come segue:

* Se non si dispone di negozi che utilizzano [!DNL Payment Services] in modalità Live, la selezione dell’origine dati viene impostata per impostazione predefinita su _[!UICONTROL Sandbox]_.
* Se sono presenti negozi (uno o più) che utilizzano [!DNL Payment Services] in modalità Live, la selezione dell’origine dati viene impostata per impostazione predefinita su _[!UICONTROL Live]_.
* Le esportazioni dei rapporti rispettano sempre la selezione dell’origine dati.

Per selezionare l&#39;origine dati per [!UICONTROL Order Payment Status] rapporto:

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Clic **[!UICONTROL Data source]** e seleziona _[!UICONTROL Live]_o_[!UICONTROL Sandbox]_.

   I risultati del report vengono rigenerati in base all&#39;origine dati selezionata.

## Personalizzare l’intervallo temporale delle date

Nella visualizzazione del rapporto Stato pagamento ordine è possibile personalizzare l&#39;intervallo temporale degli stati che si desidera visualizzare selezionando date specifiche. Per impostazione predefinita, nella griglia sono visualizzati 30 giorni di stato di pagamento dell&#39;ordine.

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Fai clic su **[!UICONTROL Order dates]** filtro selettore calendario.
1. Scegli l’intervallo di date applicabile.
1. Visualizza gli stati di pagamento dell&#39;ordine per le date specificate nella griglia.

## Mostra e nascondi colonne

Il rapporto Stato pagamento ordine mostra tutte le colonne di informazioni disponibili per impostazione predefinita. È tuttavia possibile personalizzare le colonne visualizzate nel rapporto.

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Fai clic su _Impostazioni colonna_ icona (![icona delle impostazioni delle colonne](assets/column-settings.png)).
1. Per personalizzare le colonne visualizzate nel report, selezionare o deselezionare le colonne nell&#39;elenco.

   Il rapporto Stato pagamento ordine visualizza immediatamente le modifiche apportate nel menu Impostazioni colonna. Le preferenze delle colonne verranno salvate e rimarranno attive anche quando ci si allontana dalla vista del rapporto.

## Stati di visualizzazione

La visualizzazione del rapporto Stato pagamento ordine mostra lo stato completo delle transazioni e le informazioni sullo stato del pagamento per ogni ordine di Payment Services.

### Stato della transazione

Per impostazione predefinita, nella griglia sono visualizzati 30 giorni di stato di pagamento dell&#39;ordine.

Scorri verso sinistra e destra per visualizzare [informazioni stato pagamento ordine](#column-descriptions), inclusa la data dell&#39;ordine, la data autorizzata, fatturata, spedita, lo stato di pagamento e altro ancora.

Il numero di righe restituite in una ricerca o visualizzate negli stati di pagamento dell&#39;ordine predefiniti per 30 giorni viene visualizzato sopra la griglia di visualizzazione dello stato del pagamento dell&#39;ordine insieme al filtro del selettore calendario Date ordine.

### Stato della retribuzione

La colonna Stato pagamento mostra lo stato corrente di qualsiasi pagamento. A `Capture failed` il pagamento mostra uno stato di avviso rosso e un `Voided` il pagamento mostra uno stato di avviso grigio.

### Stato rimborso

La colonna Stato rimborso mostra lo stato corrente di qualsiasi rimborso. A `Capture failed` il pagamento mostra uno stato di avviso rosso e un `Voided` il pagamento mostra uno stato di avviso grigio.

## Aggiornare i dati del rapporto

La vista del rapporto Stato pagamento ordine mostra un _[!UICONTROL Last updated]_timestamp che mostra l’ultimo aggiornamento delle informazioni del rapporto. Per impostazione predefinita, i dati del rapporto Stato pagamento ordine vengono aggiornati automaticamente ogni tre ore.

È inoltre possibile forzare manualmente l&#39;aggiornamento dei dati del rapporto Stato pagamento ordine per visualizzare le informazioni più aggiornate.

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Fai clic su _Aggiorna_ icona (![icona di aggiornamento](assets/refresh-button-med.png)).

   I dati del rapporto sullo stato del pagamento dell&#39;ordine vengono aggiornati, *[!UICONTROL Update complete]* viene visualizzata la conferma e nella griglia sono presenti le informazioni più recenti.

## Visualizza controversie

Puoi visualizzare eventuali controversie sugli ordini del tuo Negozio e passare al Centro di risoluzione PayPal per intervenire su di essi, dall&#39;interno del rapporto Stato pagamento ordine.

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Accedi a **[!UICONTROL Disputes column]**.
1. Visualizzare eventuali controversie per un ordine specifico e vedere [lo stato della controversia](#order-payment-status-information).
1. Fare clic sul collegamento ID controversia (che inizia con _PP-D-_) per passare al [Centro soluzioni PayPal](https://www.paypal.com/us/smarthelp/article/what-is-the-resolution-center-faq3327).
1. Adottare le misure appropriate per la controversia, se necessario.

   Per ordinare le controversie in base allo stato, fai clic sull’intestazione della colonna Controversie.

## Scarica stati di pagamento ordine

È possibile scaricare un file .csv con tutti gli stati visibili nella griglia di visualizzazione dello stato del pagamento dell&#39;ordine, sia che si visualizzino gli stati predefiniti di 30 giorni o un intervallo temporale personalizzato.

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Se desideri visualizzare gli stati per un intervallo di tempo diverso dagli ultimi 30 giorni, [personalizza l’intervallo di date temporale per i tuoi stati](#customize-dates-timeframe).
1. Fai clic su _Scarica_ (![icona di download](assets/icon-download.png)).

Gli stati di pagamento dell&#39;ordine vengono scaricati in formato .csv.

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

## Informazioni stato pagamento ordine

La vista Stato pagamento ordine mostra informazioni dettagliate per ogni stato visualizzato nella griglia.

### Descrizioni delle colonne

I rapporti sullo stato dei pagamenti degli ordini includono le seguenti informazioni.

| Colonna | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL Order ID] | ID ordine commerce<br> <br>Per visualizzare i [informazioni ordine](https://docs.magento.com/user-guide/sales/orders.html){target="_blank"}, fai clic sull&#39;ID. |
| [!UICONTROL Order Date] | Timestamp data ordine |
| [!UICONTROL Authorized Date] | Data e ora dell’autorizzazione di pagamento |
| [!UICONTROL Order Status] | Commerce corrente [stato ordine](https://docs.magento.com/user-guide/sales/order-status.html){target="_blank"} |
| [!UICONTROL Invoiced] | Stato fattura dell&#39;ordine—*[!UICONTROL No]*, *[!UICONTROL Partial]*, o *[!UICONTROL Yes]* |
| [!UICONTROL Shipped] | Stato spedizione dell&#39;ordine—*[!UICONTROL No]*, *[!UICONTROL Partial]*, o *[!UICONTROL Yes]* |
| [!UICONTROL Order Amt] | Importo totale totale dell’ordine |
| [!UICONTROL Cur] | Tipo di valuta dell’ordine |
| [!UICONTROL Pay Status] | Stato del pagamento per un ordine specifico |
| [!UICONTROL Paid Amt] | Importo pagato su un ordine |
| [!UICONTROL Cur] | Tipo di valuta dell’importo pagato su un ordine |
| [!UICONTROL Refund Status] | Stato di un rimborso su un ordine (ad esempio informazioni da restituzioni, RMA e note di accredito)—   *[!UICONTROL Requires refund]*, *[!UICONTROL Refund requested]*, *[!UICONTROL Refunded]*, *[!UICONTROL Refund failed]*, o *[!UICONTROL Voided]* |
| [!UICONTROL Refund Amount] | Totale dell&#39;importo rimborsato per un ordine |
| [!UICONTROL Cur] | Tipo di valuta dell&#39;importo rimborsato per un ordine |
| [!UICONTROL Disputes] | Stato di qualsiasi controversia relativa a un ordine (informazioni derivanti da controversie e rettifiche)—*[!UICONTROL Open]*, *[!UICONTROL Waiting for buyer response]*, *[!UICONTROL Waiting for seller response]*, *[!UICONTROL Under review]*, *[!UICONTROL Resolved]*, o *[!UICONTROL Other]* |
| [!UICONTROL Payment Method] | Metodo di pagamento utilizzato nella transazione Commerce per un ordine |
| [!UICONTROL Website] | Sito web da cui è stato effettuato l’ordine |
| [!UICONTROL Store] | Archivio da cui è stato effettuato l’ordine |
| [!UICONTROL Store View] | Visualizzazione del Negozio da cui è stato effettuato l&#39;ordine |
