---
title: Rapporto Pagamenti
description: Utilizzare il rapporto Pagamenti per una trasparenza completa dell'importo del pagamento, del volume elaborato e del reporting dettagliato a livello di transazione per la quadratura finanziaria.
role: User
level: Intermediate
exl-id: f3f99474-cd28-4c8f-b0ea-dca8e014b108
source-git-commit: 817a01e98876bddf5f41a253501984539b3351cd
workflow-type: tm+mt
source-wordcount: '1335'
ht-degree: 0%

---

# Rapporto Pagamenti

[!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] offre una funzione di reporting completa che ti permette di avere una visione chiara degli ordini e dei pagamenti del tuo negozio.

![Visualizzazione dei report finanziari](assets/reports-justpayouts.png)

Sono disponibili due visualizzazioni di reporting Pagamenti per consentirti di visualizzare informazioni approfondite su tutti i tuoi pagamenti:

* **[Visualizzazione dati pagamenti](#payouts-data-visualization-view)**- Grafico disponibile nella home di Payment Services che è una rappresentazione visiva degli importi aggregati al giorno dalla visualizzazione del rapporto Pagamenti
* **[Visualizzazione report Pagamenti](#payouts-report-view)**- Report disponibile in Pagamenti che mostra informazioni dettagliate sui pagamenti per tutte le transazioni

Le visualizzazioni Pagamenti mostrano immediatamente informazioni complete sui pagamenti, consentendo la completa trasparenza dell&#39;importo del pagamento, del volume elaborato e dei rapporti dettagliati a livello di transazione per la quadratura finanziaria.

>[!NOTE]
>
>I rapporti Pagamenti mostrano solo gli ordini acquisiti (l&#39;azione di pagamento è impostata su [`Authorize and Capture`](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/production.html#set-payment-services-as-payment-method))—oppure [contrassegnato come `Invoiced`](https://docs.magento.com/user-guide/sales/invoice-create.html).

## Visualizzazione dati pagamenti

La visualizzazione dati Pagamenti è disponibile nella Home page di Payment Services. Rappresenta visivamente gli importi aggregati al giorno dalla tabella dettagliata [Visualizzazione report Pagamenti](#payouts-report-view).

Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** per visualizzare il grafico con la visualizzazione dei dati relativo ai crediti rispetto ai debiti e alle medie mobili nel tempo.

![Visualizzazione dei dati di pagamento nell’Amministratore](assets/payouts-report.png)

Clic **[!UICONTROL View Report]** per passare alla tabella dettagliata [Visualizzazione report Pagamenti](#payouts-report-view).

### Personalizzare l’arco temporale delle transazioni

Per impostazione predefinita, vengono visualizzati 30 giorni di transazioni.

Nella visualizzazione dati Pagamenti è possibile personalizzare l&#39;intervallo di tempo per le transazioni di pagamento che si desidera visualizzare selezionando un intervallo di date:

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**. La visualizzazione dei dati Pagamenti è visibile nella sezione Pagamenti.
1. Fai clic su **[!UICONTROL Range]** filtro di selezione.
1. Scegliere l&#39;intervallo di date applicabile: 30 giorni, 15 giorni o 7 giorni.
1. Visualizza le informazioni sulle transazioni per le date specificate.

### Informazioni sulle transazioni

Gli importi delle transazioni per un intervallo di date selezionato vengono visualizzati a sinistra della visualizzazione Dati pagamenti. Le date per l’intervallo di date selezionato sono visualizzate nella parte inferiore della visualizzazione. Se non ci sono stati pagamenti in una data particolare, quella data non sarà visualizzata.

La visualizzazione dati Pagamenti include le seguenti informazioni.

| Dati | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL Transaction amount] | Intervallo di importi per le transazioni nell&#39;intervallo di tempo specificato; dati sull&#39;asse Y (a sinistra) |
| Intervallo di date | Intervallo di date per l’intervallo di tempo specificato; dati sull’asse X (in basso) |
| Credito | Pagamenti per l&#39;intervallo di tempo specificato |
| Dare | Debiti (rimborsi) per l&#39;intervallo di tempo specificato |
| Media mobile | Rappresentazione del pagamento medio per ogni data nell&#39;intervallo di tempo specificato |
| Netto per intervallo | Importo del pagamento netto per l’intervallo di tempo specificato |

## Visualizzazione report Pagamenti

La visualizzazione del rapporto Pagamenti è disponibile nella visualizzazione Pagamenti di Servizi di pagamento. Include tutte le informazioni disponibili sui pagamenti per il/i tuo/i negozio/i. Il [Visualizzazione dati pagamenti](#payouts-data-visualization-view) in Payment Services Home è una rappresentazione visiva degli importi aggregati al giorno in questa visualizzazione di report più dettagliata.

Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]** per visualizzare la tabella dettagliata della visualizzazione del rapporto Pagamenti.

![Transazioni di pagamento nell&#39;amministratore](assets/payouts-report-new.png)

È possibile configurare questa visualizzazione in base alle sezioni di questo argomento per presentare al meglio i dati che si desidera visualizzare.

Vedi gli ID di transazioni e ordini Commerce collegati, gli importi delle transazioni, il metodo di pagamento per transazione e altro ancora, tutto all’interno del rapporto Pagamenti in Admin.

È possibile scaricare le transazioni di pagamento in un formato di file .csv da utilizzare nel software di contabilità o di gestione degli ordini esistente.

>[!NOTE]
>
>I dati mostrati in questa tabella sono ordinati in ordine decrescente (`DESC`) per impostazione predefinita utilizzando `TRANS DATE`. Il `TRANS DATE` è la data e l’ora in cui è stata avviata la transazione.

### Seleziona origine dati

Nella visualizzazione del rapporto Pagamenti, è possibile selezionare l&#39;origine dati:_[!UICONTROL Live]_o_[!UICONTROL Sandbox]_- per il quale si desidera visualizzare i risultati del rapporto.

![Selezione di origini dati](assets/datasource.png)

Se _[!UICONTROL Live]_è l’origine dati selezionata, puoi visualizzare le informazioni del rapporto per i tuoi store live. Se [!UICONTROL Sandbox]_ è l’origine dati selezionata, puoi visualizzare le informazioni del rapporto per il tuo ambiente Sandbox.

Le selezioni delle origini dati funzionano come segue:

* Se non disponi di archivi in modalità Live, la selezione dell’origine dati viene impostata per impostazione predefinita su _[!UICONTROL Sandbox]_.
* Se disponi di uno o più archivi in modalità Live, per impostazione predefinita la selezione dell’origine dati viene impostata su _[!UICONTROL Live]_.
* Le esportazioni dei rapporti rispettano sempre la selezione dell’origine dati.

Per selezionare l&#39;origine dati per il rapporto Stato pagamento ordine:

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Clic **[!UICONTROL Data source]** e seleziona _[!UICONTROL Live]_o_[!UICONTROL Sandbox]_.

   I risultati del report vengono rigenerati in base all&#39;origine dati selezionata.

### Visualizza transazioni

Per impostazione predefinita, vengono visualizzati 30 giorni di transazioni.

Il numero di righe restituite in una ricerca o visualizzate nei 30 giorni predefiniti di transazioni viene visualizzato sopra la griglia di visualizzazione Pagamenti insieme al filtro del selettore calendario Date transazione.

Scorri verso sinistra e destra per visualizzare [informazioni per ogni operazione di pagamento](#column-descriptions) nel report giornaliero, inclusi i dettagli relativi alla data della transazione, all&#39;ID di riferimento, al numero della fattura e al metodo di pagamento.

#### Personalizzare l’arco temporale delle transazioni

Nella visualizzazione del rapporto Pagamenti è possibile personalizzare l&#39;intervallo di tempo per le transazioni di pagamento che si desidera visualizzare inserendo date specifiche o selezionando un intervallo di date dal selettore delle date:

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Fai clic sul filtro del selettore calendario Date transazione.
1. Scegli l’intervallo di date applicabile.
1. Visualizza gli stati dei pagamenti nella griglia per le date specificate.

### Mostra e nascondi colonne

La visualizzazione del rapporto Pagamenti mostra la maggior parte delle colonne di informazioni disponibili per impostazione predefinita. È tuttavia possibile personalizzare le colonne visualizzate nel rapporto.

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Payouts]**.
1. Fai clic su _Impostazioni colonna_ icona (![icona delle impostazioni delle colonne](assets/column-settings.png)).
1. Per personalizzare le colonne visualizzate nel report, selezionare o deselezionare le colonne nell&#39;elenco.

   La visualizzazione del rapporto Pagamenti mostra immediatamente le modifiche apportate nel menu delle impostazioni delle colonne. Le preferenze delle colonne verranno salvate e rimarranno attive anche quando ci si allontana dalla vista del rapporto.

### Scarica transazioni

Puoi scaricare un file .csv contenente tutte le transazioni visibili nella griglia di visualizzazione Pagamenti.

1. Il giorno _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. [Personalizzare l’intervallo di date temporale per le transazioni](#customize-transactions-timeframe).
1. Fai clic su _Scarica_ (![](assets/icon-download.png)).

Le transazioni di pagamento vengono scaricate in formato .csv.

### Descrizioni delle colonne

I rapporti di pagamento includono le seguenti informazioni.

| Colonna | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL Provider] | Fornitore di pagamenti |
| [!UICONTROL Provider trans] | ID transazione |
| [!UICONTROL Trans date] | Data e ora di avvio della transazione |
| [!UICONTROL Type] | Tipo di transazione:*[!UICONTROL PAYMENT]*, *[!UICONTROL BONUS]*, *[!UICONTROL CHARGEBACK]*, *[!UICONTROL CORRECTION]*, *[!UICONTROL CURRENCY_CONVERSATION]*, *[!UICONTROL DEPOSIT]*, *[!UICONTROL DISBURSEMENT]*, *[!UICONTROL DISPUTE]*, *[!UICONTROL FEES]*, *[!UICONTROL HOLD]*, *[!UICONTROL HOLD_RELEASE]*, *[!UICONTROL INCENTIVES]*, *[!UICONTROL OTHERS]*, *[!UICONTROL RECOUP]*, *[!UICONTROL REFUND]*, *[!UICONTROL REVERSAL]*, *[!UICONTROL WITHDRAWAL]* <br> <br>Consulta [Tipi di transazione](#transaction-types) per ulteriori informazioni. |
| [!UICONTROL Status] | Stato corrente della transazione:*[!UICONTROL SUCCESS]*, *[!UICONTROL DENIED]*, *[!UICONTROL PENDING]* |
| [!UICONTROL Code] | Codice transazione che indica il credito (*CR*) o Dare (*DR*) |
| [!UICONTROL Reference ID] | ID transazione originale per cui è correlato questo evento |
| [!UICONTROL Invoice] | ID fattura (uno per ordine) della transazione |
| [!UICONTROL Commerce order] | ID ordine commerce <br> <br>Per visualizzare i [informazioni ordine](https://docs.magento.com/user-guide/sales/orders.html){target="_blank"}, fai clic sull&#39;ID. |
| [!UICONTROL Commerce trans] | ID transazione commerciale <br> <br>Per visualizzare i [informazioni transazione](https://docs.magento.com/user-guide/sales/transactions.html){target="_blank"}, fai clic sull&#39;ID. |
| [!UICONTROL Pay method] | Tipo di carta di credito—*[!UICONTROL BANK]*, *[!UICONTROL PAYPAL]*, *[!UICONTROL APPLE_PAY]*, *[!UICONTROL CREDIT_CARD]*- e il relativo provider di carte (ad esempio *Visto* o *MasterCard*) |
| [!UICONTROL Trans amt] | Importo della transazione |
| [!UICONTROL Cur] | Unità di valuta per l’importo della transazione |
| [!UICONTROL Pending] | Importo ancora da erogare |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo in sospeso |
| [!UICONTROL Seller amt] | Importo dei fondi trasferiti da o verso un cliente <br> <br>I fondi che escono dall&#39;account del venditore presentano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo del venditore |
| [!UICONTROL Partner fee] | Tariffe partner associate alla transazione <br> <br>I fondi trasferiti dal conto di addebito partner mostrano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per la commissione partner |
| [!UICONTROL Prov fees] | Tariffe associate alla transazione <br> <br>I fondi che si spostano dal conto di addebito del fornitore mostrano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per la tariffa del provider |
| [!UICONTROL Fee %] | Percentuale dell&#39;importo della transazione addebitato come commissione |
| [!UICONTROL Fixed fee] | Importo tariffa provider fisso |
| [!UICONTROL Chbk fee] | Commissione di rettifica associata alla transazione <br> <br>Un trattino (-) prefisso indica che la commissione di rettifica è stata stornata. |
| [!UICONTROL Cur] | Unità di valuta per la commissione di rettifica |
| [!UICONTROL Hold amt] | Quantità messa in attesa o rilasciata dalla sospensione <br> <br>Un trattino (-) prefisso indica che i fondi in attesa vengono rilasciati. |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo del blocco |
| [!UICONTROL Recoup amt] | Importo recuperato dal conto di recupero <br> <br>I fondi che escono dal conto di recupero presentano un prefisso trattino (-). |
| [!UICONTROL Cur] | Unità di valuta per l&#39;importo da recuperare |

### Tipi di transazione

Questi tipi di operazioni possono essere annotati nelle transazioni di pagamento.

| Report | Descrizione |
| ------------ | -------------------- |
| [!UICONTROL PAYMENT] | Soldi trasferiti tra un acquirente e un venditore per un ordine |
| [!UICONTROL AUTH] | Autorizzazione e autorizzazione di operazioni annullate |
| [!UICONTROL BONUS] | -- |
| [!UICONTROL CHARGEBACK] | Transazioni di storno con commissione di rettifica e commissione di rettifica |
| [!UICONTROL CORRECTION] | -- |
| [!UICONTROL CURRENCY_CONVERSION] | -- |
| [!UICONTROL DEPOSIT] | -- |
| [!UICONTROL DISBURSEMENT] | -- |
| [!UICONTROL DISPUTE] | -- |
| [!UICONTROL FEES] | Tariffe partner, commissioni di pagamento e transazioni di storno delle tariffe |
| [!UICONTROL HOLD] | -- |
| [!UICONTROL HOLD_RELEASE] | -- |
| [!UICONTROL INCENTIVES] | -- |
| [!UICONTROL OTHERS] | -- |
| [!UICONTROL RECOUP] | Recuperi da conti bancari o perdite |
| [!UICONTROL REFUND] | -- |
| [!UICONTROL REVERSAL] | -- |
| [!UICONTROL WITHDRAWAL] | -- |
