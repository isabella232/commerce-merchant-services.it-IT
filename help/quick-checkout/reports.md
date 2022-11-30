---
title: '''[!DNL Quick Checkout] reportistica'
description: '''[!DNL Quick Checkout] offre informazioni complete sui rapporti."'
exl-id: 91c687f4-9953-4c2f-b240-73430603e6a1
source-git-commit: bdfac90aa221f39dfc53eee833c473c7dcb0a042
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Rapporti

[!DNL Quick Checkout] per Adobe Commerce e Magenti Open Source offre rapporti completi che consentono di ottenere informazioni dettagliate sulle statistiche dell’esperienza di checkout del negozio.

![Visualizzazione rapporti](assets/reports-view-big-checkout.png)

>[!WARNING]
>
> Per consentire ad Adobe Commerce di condividere le informazioni di pagamento con Bolt, la [**Tracciamento degli acquisti**](../quick-checkout/settings-quick-checkout.md)  deve essere abilitata nell&#39;amministratore. Per impostazione predefinita, questa opzione di configurazione è impostata su **Sì**. Se questa opzione è impostata su **No**, la generazione di rapporti ne risentirà. Bolt aggiorna le informazioni di reporting una volta al giorno alle 03:00 del mattino Eastern Standard Time (EST).

## Rapporti panoramica

I grafici nella sezione Panoramica mostrano informazioni dettagliate sulle prestazioni di pagamento del tuo negozio, tra cui il tempo medio di pagamento, i nuovi account creati durante l&#39;estrazione o l&#39;abbandono del pagamento.

![Panoramica dei rapporti](assets/overview-report-checkout.png)

| Grafico | Descrizione |
|---|---|
| [!UICONTROL Checkout abandonment] | La percentuale di visitatori che escono dal processo di pagamento senza completare un acquisto. |
| [!UICONTROL Checkout abandonment breakdown] | L’abbandono del pagamento è diviso per tipo di visitatore. La descrizione comando mostra una differenza percentuale tra Bolt e Guest. Opzioni: [!UICONTROL Bolt] / [!UICONTROL Merchant] / [!UICONTROL Guest] |
| [!UICONTROL Average checkout time] | Il tempo medio impiegato da un visitatore per completare il processo di pagamento. |
| [!UICONTROL Average checkout time breakdown] | Tempo medio di pagamento diviso per tipo di visitatore. La descrizione comando mostra una differenza percentuale tra Bolt e Guest. Opzioni: [!UICONTROL Bolt] / [!UICONTROL Merchant] / [!UICONTROL Guest] |
| [!UICONTROL Orders by account type] | Ordini inseriti divisi per tipo di visitatore. Opzioni: [!UICONTROL Bolt] / [!UICONTROL Merchant] / [!UICONTROL Guest] |

## Rapporti sulle tendenze

I grafici nella sezione Tendenze mostrano le tendenze dell’esperienza di pagamento filtrate in base al tipo di account o ai nuovi account creati durante il pagamento.

![Tendenze dei rapporti](assets/trends-report-checkout.png)

| Grafico | Descrizione |
|---|---|
| [!UICONTROL Checkout abandonment by account type] | La tendenza all’abbandono del pagamento divisa per tipo di visitatore. Opzioni: [!UICONTROL Bolt] / [!UICONTROL Merchant] / [!UICONTROL Guest] |
| [!UICONTROL Orders by account type] | Gli ordini inseriti presentano una tendenza divisa per tipo di visitatore. Opzioni: [!UICONTROL Bolt] / [!UICONTROL Merchant] / [!UICONTROL Guest] |
| [!UICONTROL New accounts on your store] | Nuovi account sulla tendenza del negozio. |

## Filtrare i dati

Puoi filtrare i risultati mostrati per data, o i predefiniti esistenti, come **Ultimi 30 giorni**.

![Vista a filtri](assets/filter-view.png)

| Campo | Descrizione |
|---|---|
| [!UICONTROL Preset] | Un elenco a discesa che visualizza i predefiniti che possono essere utilizzati per mostrare intervalli di dati specifici. Per impostazione predefinita: Ultimi 30 giorni |
| [!UICONTROL Date range] | Elenco a discesa che consente di selezionare un intervallo di dati specifico a seconda delle date selezionate. |
