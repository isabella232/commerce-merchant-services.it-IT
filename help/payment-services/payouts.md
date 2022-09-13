---
title: Rapporto Pagamenti
description: Utilizzare il rapporto Pagamenti per garantire la piena trasparenza dell'importo del pagamento, del volume elaborato e del reporting dettagliato a livello di transazione per la riconciliazione finanziaria.
role: User
level: Intermediate
exl-id: f3f99474-cd28-4c8f-b0ea-dca8e014b108
source-git-commit: 27d280fb9f49715a455ff55279416f7df4ada56d
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 0%

---

# Rapporto Pagamenti

[!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] offre un reporting completo per ottenere una visione chiara degli ordini e dei pagamenti del tuo negozio.

![Visualizzazione rapporti finanziari](assets/reports-view-new.png)

Sono disponibili due visualizzazioni di generazione rapporti Pagamenti per consentirti di visualizzare informazioni approfondite su tutte le tue vincite:

* **[Visualizzazione dati pagamenti](#payouts-data-visualization-view)**- Grafico disponibile nella home di Payment Services che è una rappresentazione visiva degli importi aggregati al giorno dalla visualizzazione del rapporto Pagamenti
* **[Visualizzazione del rapporto Pagamenti](#payouts-report-view)**- Report disponibile in Pagamenti che mostra informazioni dettagliate sui pagamenti per tutte le transazioni

Le visualizzazioni Pagamenti mostrano immediatamente informazioni complete sui pagamenti, consentendo la piena trasparenza dell&#39;importo del pagamento, del volume elaborato e dei rapporti dettagliati a livello di transazione per la riconciliazione finanziaria.

>[!NOTE]
>
>I rapporti sui pagamenti mostrano solo gli ordini acquisiti (l&#39;azione di pagamento è impostata su [`Authorize and Capture`](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/production.html#set-payment-services-as-payment-method))—o [contrassegnato come `Invoiced`](https://docs.magento.com/user-guide/sales/invoice-create.html).

## Visualizzazione dati pagamenti

La visualizzazione dei dati relativi ai pagamenti è disponibile nella home di Payment Services. È una rappresentazione visiva degli importi aggregati al giorno dalla tabella dettagliata [Visualizzazione del rapporto Pagamenti](#payouts-report-view).

Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** per visualizzare il grafico di visualizzazione dei dati su crediti e debiti e le medie mobili nel tempo.

![Visualizzazione dati di payout nell’amministratore](assets/payouts-data.png)

Fai clic su **[!UICONTROL View Report]** per passare alla tabella dettagliata [Visualizzazione del rapporto Pagamenti](#payouts-report-view).

### Personalizza arco temporale delle transazioni

Per impostazione predefinita, vengono visualizzati 30 giorni di transazioni.

Nella visualizzazione Visualizzazione dati Pagamenti è possibile personalizzare l&#39;intervallo di tempo per le transazioni di pagamento che si desidera visualizzare selezionando un intervallo di date:

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**. La visualizzazione dei dati relativi ai pagamenti è visibile nella sezione Pagamenti.
1. Fai clic sul pulsante **[!UICONTROL Range]** filtro selettore.
1. Scegli l’intervallo di date applicabile: 30 giorni, 15 giorni o 7 giorni.
1. Visualizza le informazioni sulle transazioni per le date specificate.

### Informazioni sulle transazioni

Gli importi delle transazioni per un intervallo di date selezionato vengono visualizzati a sinistra della visualizzazione dati Pagamenti. Le date dell’intervallo date selezionato vengono visualizzate nella parte inferiore della visualizzazione. Se non ci sono stati pagamenti in una data particolare, quella data non verrà visualizzata.

La visualizzazione dati Pagamenti include le informazioni seguenti.

| Dati | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL Transaction amount] | Intervallo di importo per le transazioni nell&#39;arco temporale specificato; dati sull’asse Y (a sinistra) |
| Intervallo date | Intervallo di date per l&#39;intervallo di tempo specificato; dati sull&#39;asse X (in basso) |
| Crediti | Pagamenti per il periodo di tempo specificato |
| Debito | Debiti (rimborsi) per il periodo di tempo specificato |
| Media mobile | Rappresentazione del pagamento medio per ogni data nell&#39;arco temporale specificato |
| Rete per gamma | Importo netto dell&#39;utile per l&#39;intervallo di tempo specificato (intervallo) |

## Visualizzazione del rapporto Pagamenti

La visualizzazione del rapporto Pagamenti è disponibile nella visualizzazione Pagamenti di Servizi di pagamento. Include tutte le informazioni disponibili sui pagamenti per i tuoi store. La [Visualizzazione dati pagamenti](#payouts-data-visualization-view) in Payment Services Home è una rappresentazione visiva degli importi aggregati al giorno in questa visualizzazione più dettagliata del rapporto.

Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]** per visualizzare la visualizzazione dettagliata del rapporto Pagamenti tabulari .

![Transazioni di pagamento nell&#39;amministratore](assets/payouts-report-new.png)

Puoi configurare questa visualizzazione, in base alle sezioni di questo argomento, per presentare al meglio i dati che desideri visualizzare.

Vedi ID di ordine e transazione commerciali collegati, importi delle transazioni, metodo di pagamento per transazione e altro ancora, tutto all&#39;interno del rapporto Pagamenti in Amministratore.

È possibile scaricare le transazioni di pagamento in un formato file .csv da utilizzare nel software di contabilità o gestione degli ordini esistente.

>[!NOTE]
>
>I dati visualizzati in questa tabella vengono ordinati in ordine decrescente (`DESC`) per impostazione predefinita utilizzando `TRANS DATE`. La `TRANS DATE` è la data e l&#39;ora in cui è stata avviata la transazione.

### Seleziona origine dati

Nella visualizzazione del rapporto Pagamenti, è possibile selezionare l&#39;origine dati—_[!UICONTROL Live]_o_[!UICONTROL Sandbox]_- per i quali visualizzare i risultati del rapporto.

![Selezione di origini dati](assets/datasource.png)

Se _[!UICONTROL Live]_è l’origine dati selezionata, puoi visualizzare le informazioni sui rapporti per gli archivi live. Se [!UICONTROL Sandbox]_ è l’origine dati selezionata, puoi visualizzare le informazioni sul rapporto per l’ambiente Sandbox.

Le selezioni dell’origine dati funzionano come segue:

* Se non disponi di archivi in modalità Live, la selezione dell’origine dati viene impostata automaticamente su _[!UICONTROL Sandbox]_.
* Se hai degli archivi (uno o più) in modalità Live, la selezione dell&#39;origine dati viene impostata automaticamente su _[!UICONTROL Live]_.
* Le esportazioni dei rapporti rispettano sempre la selezione dell’origine dati.

Per selezionare l&#39;origine dati per il report Stato pagamento ordine:

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Fai clic su **[!UICONTROL Data source]** e seleziona _[!UICONTROL Live]_o_[!UICONTROL Sandbox]_.

   I risultati del report vengono rigenerati in base all&#39;origine dati selezionata.

### Visualizza transazioni

Per impostazione predefinita, vengono visualizzati 30 giorni di transazioni.

Il numero di righe restituite in una ricerca, o visualizzate nei 30 giorni predefiniti di transazioni, viene visualizzato sopra la griglia di visualizzazione Pagamenti accanto al filtro di selezione del calendario delle date delle transazioni.

Scorri verso sinistra e verso destra per visualizzare [informazioni per ogni operazione di pagamento](#column-descriptions) nel rapporto giornaliero, compresi la data della transazione, l&#39;ID di riferimento, il numero della fattura e i dettagli del metodo di pagamento.

#### Personalizza arco temporale delle transazioni

Nella visualizzazione del rapporto Pagamenti è possibile personalizzare l&#39;intervallo temporale per le transazioni di pagamento che si desidera visualizzare inserendo date specifiche o selezionando un intervallo di date dal selettore data:

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Fare clic sul filtro del selettore del calendario delle date delle transazioni.
1. Scegli l’intervallo di date applicabile.
1. Visualizza gli stati dei pagamenti nella griglia per le date specificate.

### Mostra e nascondi colonne

La visualizzazione del rapporto Pagamenti mostra per impostazione predefinita la maggior parte delle colonne di informazioni disponibili. È tuttavia possibile personalizzare le colonne visualizzate nel rapporto.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Payouts]**.
1. Fai clic sul pulsante _Impostazioni colonna_ icona (![icona delle impostazioni colonna](assets/column-settings.png)).
1. Per personalizzare le colonne visualizzate nel rapporto, selezionare o deselezionare le colonne nell’elenco.

   La visualizzazione del rapporto Pagamenti mostrerà immediatamente tutte le modifiche apportate nel menu Impostazioni colonna. Le preferenze della colonna vengono salvate e rimangono attive se ci si allontana dalla visualizzazione del rapporto.

### Scarica transazioni

È possibile scaricare un file .csv contenente tutte le transazioni visibili nella griglia di visualizzazione Pagamenti.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. [Personalizzare l’intervallo di tempo per le transazioni](#customize-transactions-timeframe).
1. Fai clic sul pulsante _Scarica_ (![](assets/icon-download.png)).

Le transazioni di pagamento vengono scaricate in formato .csv.

### Descrizioni delle colonne

I rapporti di pagamento includono le seguenti informazioni.

| Colonna | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL Provider] | Fornitore di pagamenti |
| [!UICONTROL Provider trans] | ID transazione |
| [!UICONTROL Trans date] | Data e ora di avvio della transazione |
| [!UICONTROL Type] | Tipo di transazione *[!UICONTROL PAYMENT]*, *[!UICONTROL BONUS]*, *[!UICONTROL CHARGEBACK]*, *[!UICONTROL CORRECTION]*, *[!UICONTROL CURRENCY_CONVERSATION]*, *[!UICONTROL DEPOSIT]*, *[!UICONTROL DISBURSEMENT]*, *[!UICONTROL DISPUTE]*, *[!UICONTROL FEES]*, *[!UICONTROL HOLD]*, *[!UICONTROL HOLD_RELEASE]*, *[!UICONTROL INCENTIVES]*, *[!UICONTROL OTHERS]*, *[!UICONTROL RECOUP]*, *[!UICONTROL REFUND]*, *[!UICONTROL REVERSAL]*, *[!UICONTROL WITHDRAWAL]* <br> <br>Vedi [Tipi di transazione](#transaction-types) per ulteriori informazioni. |
| [!UICONTROL Status] | Stato attuale della transazione—*[!UICONTROL SUCCESS]*, *[!UICONTROL DENIED]*, *[!UICONTROL PENDING]* |
| [!UICONTROL Code] | Codice transazione che indica il credito (*CR*) o Debiti (*DR*) |
| [!UICONTROL Reference ID] | ID transazione originale per il quale è correlato l’evento |
| [!UICONTROL Invoice] | ID fattura (uno per ordine) della transazione |
| [!UICONTROL Commerce order] | ID ordine commerciale <br> <br>Per visualizzare i dati correlati [info ordine](https://docs.magento.com/user-guide/sales/orders.html), fai clic sull&#39;ID. |
| [!UICONTROL Commerce trans] | ID transazione commerciale |
| [!UICONTROL Pay method] | Tipo di carta di credito *[!UICONTROL BANK]*, *[!UICONTROL PAYPAL]*, *[!UICONTROL CREDIT_CARD]*- e il provider di carte associato (ad esempio *Visto* o *MasterCard*) |
| [!UICONTROL Trans amt] | Importo della transazione |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo della transazione |
| [!UICONTROL Pending] | Importo da versare |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo in sospeso |
| [!UICONTROL Seller amt] | Importo dei fondi trasferiti da o verso un cliente <br> <br>I fondi che escono dal conto del venditore presentano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo del venditore |
| [!UICONTROL Partner fee] | Commissioni per i partner associate alla transazione <br> <br>I fondi che escono dal conto delle tariffe partner presentano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per la tariffa del partner |
| [!UICONTROL Prov fees] | Tariffe associate alla transazione <br> <br>I fondi che escono dal conto commissioni del fornitore mostrano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per la commissione del fornitore |
| [!UICONTROL Fee %] | Percentuale dell&#39;importo della transazione addebitato come commissione |
| [!UICONTROL Fixed fee] | Importo canone fisso fornitore |
| [!UICONTROL Chbk fee] | Commissioni di addebito associate alla transazione <br> <br>Un prefisso trattino (-) indica che la tassa di chargeback è stata annullata. |
| [!UICONTROL Cur] | Unità di valuta per la tassa di ricarica |
| [!UICONTROL Hold amt] | Importo messo in attesa o rilasciato dal blocco <br> <br>Un prefisso trattino (-) indica che i fondi in attesa vengono rilasciati. |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo del blocco |
| [!UICONTROL Recoup amt] | Importo recuperato dal conto di recupero <br> <br>I fondi che escono dall&#39;account di recupero presentano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo del recupero |

### Tipi di transazione

Questi tipi di operazioni possono essere annotati nelle operazioni di pagamento.

| Rapporto | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL PAYMENT] | Il denaro è stato trasferito tra un acquirente e un venditore per un ordine |
| [!UICONTROL AUTH] | Autorizzazione e autorizzazione di transazioni nulle |
| [!UICONTROL BONUS] | — |
| [!UICONTROL CHARGEBACK] | Transazioni di storno di commissioni e di commissioni di addebito |
| [!UICONTROL CORRECTION] | — |
| [!UICONTROL CURRENCY_CONVERSION] | — |
| [!UICONTROL DEPOSIT] | — |
| [!UICONTROL DISBURSEMENT] | — |
| [!UICONTROL DISPUTE] | — |
| [!UICONTROL FEES] | Commissioni partner, commissioni di pagamento e transazioni di storno di commissioni |
| [!UICONTROL HOLD] | — |
| [!UICONTROL HOLD_RELEASE] | — |
| [!UICONTROL INCENTIVES] | — |
| [!UICONTROL OTHERS] | — |
| [!UICONTROL RECOUP] | Ricavi da conti bancari o perdite |
| [!UICONTROL REFUND] | — |
| [!UICONTROL REVERSAL] | — |
| [!UICONTROL WITHDRAWAL] | — |
