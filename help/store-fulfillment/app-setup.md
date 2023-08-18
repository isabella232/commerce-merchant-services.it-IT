---
title: Configurazione app
description: Configurare [!DNL Store Assist] app per gestire flussi di lavoro e processi di evasione del punto vendita end-to-end per l’acquisto online, ritiro degli ordini nel punto vendita.
level: Intermediate
role: Admin
feature: Shipping/Delivery, Configuration, Tools and External Services
exl-id: bcb5b02b-0141-407a-ad55-6e10e8e1aa90
source-git-commit: 78b09113e72382053b01d6016276bae3aa545fa3
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Configurazione dell’app

Store Assist è un’app per piattaforma di tipo Fulfilment-as-a-Service (FaaS) fornita da Walmart Commerce Technologies. L’app fornisce funzionalità di esecuzione in-store per gestire [!DNL buy online, pick up in store] (BOPIS). Con Store Assist, i dipendenti del negozio possono vedere quali articoli sono stati ordinati dai clienti, scegliere gli articoli corretti più rapidamente e impostare ordini evasi per la consegna in-store o con prelievo a blocchi ai clienti.

L&#39;app Store Assist riceve tutte le informazioni relative agli ordini e ai clienti, dai dettagli degli ordini per prelevare i tempi di consegna, e rende i dati disponibili online per gli associati dello store, attraverso i dispositivi mobili. L&#39;app include [!UICONTROL Pick], [!UICONTROL Stage], [!UICONTROL Handoff], e [!UICONTROL Orders] moduli per aiutare gli associati del negozio ad attività di evasione come le seguenti:

- Assegnare date e ore di consegna dell&#39;ordine.
- Ricevi notifiche dai clienti quando arrivano per il ritiro dell’ordine.
- Fase degli ordini per la consegna ai clienti.
- Tenere traccia dello stato dell&#39;ordine per tutti gli ordini nelle ubicazioni di magazzino assegnate.

>[!NOTE]
>
>Ulteriori informazioni sull&#39;app Store Assist sono disponibili nella sezione [Archivia flussi di lavoro di evasione assistenza](store-assist-modules.md) argomento.

## Configurare l’app Store Assist

L&#39;app Store Assist richiede due tipi di configurazione:

- Impostazioni di Adobe Commerce Admin System su [gestire account utente, ruoli utente, autorizzazioni delle risorse](user-setup.md), e [le selezioni di marca e modello dell&#39;auto disponibili ai clienti durante il processo di check-in](check-in-experience-setup.md).

- Impostazioni di configurazione front-end per personalizzare l’interfaccia dell’app Store Assist e altre impostazioni, tra cui:

   - **Personalizzare l’app Store Assist**: personalizza l’interfaccia utente dell’app con il logo e i colori della tua azienda.

   - **Aggiornare le istruzioni predefinite**: personalizza le istruzioni nei moduli Prelievo assistenza store, Staging, Handoff e Ordine per guidare gli associati al negozio attraverso ogni passaggio del flusso di lavoro di evasione per la tua azienda.

   - **Localizzazione**- Seleziona la lingua disponibile per l&#39;app. Scegliere il formato di data e ora e selezionare le unità di misura predefinite e la valuta predefinita.

   - **Tempo di inattività**- Specifica per quanto tempo l&#39;app deve essere inattiva prima di disconnettersi.

   - **Annullamento dallo store**- Specificare se gli ordini possono essere annullati dallo store e quali ruoli dispongono delle autorizzazioni di annullamento

   - **Finestra di pulizia ordine**- Specifica quanto tempo è passato il [Lead time di prelievo stimato](enable-general.md#delivery-method-title-configuration) che un ordine prelevato rimanga nella gestione temporanea prima di essere rifornito, ad esempio tre giorni. Il valore predefinito è sette giorni. Se questa configurazione è attivata, l&#39;ordine viene automaticamente annullato alla scadenza di questo periodo di tempo. Gli articoli vengono riassortimenti e il commerciante riceve un’e-mail di cancellazione.

   - Personalizza tutto nelle istruzioni dell’app (prelievo, staging, consegna).

   - **Notifiche di prelievo**- Specifica se inviare una notifica push per avviare il processo di prelievo dopo che un cliente ha effettuato un ordine.

   - **Archivia notifiche**— Specificare se inviare una notifica push durante il processo di check-in per i prelievi degli ordini- dopo il check-in, dopo che il tempo di attesa del cliente supera un periodo di tempo specificato. Oppure, disattiva la notifica.

   - **Processo a mano**- Abilitare i processi facoltativi quando l&#39;Associato negozio consegna l&#39;ordine al cliente, ad esempio richiedere una firma del cliente o richiedere all&#39;Associato di controllare l&#39;ID cliente.

   - **Abilita rifiuto articolo al momento del passaggio di consegne**- Consente ai clienti di restituire o annullare gli articoli dell&#39;ordine durante il trasferimento.

  Collabora con il team di Walmart Commerce Technologies Client Services per completare la configurazione front-end per l’app Store Assist.

## Download e installazione dell’app

Dopo che l&#39;app Store Assist è stata configurata, gli associati possono scaricare, installare e accedere all&#39;app Store Assist dai loro dispositivi mobili.

- Verifica che il dispositivo mobile soddisfi [requisiti hardware e software](solution-requirements.md#store-assist-app-requirements) per la soluzione Store Fulfillment.

- Scarica l’app Store Assist da [Apple App Store](https://apps.apple.com/us/app/store-assist-by-walmart/id1609281539){target="_blank"} or the [Google Play store](https://play.google.com/store/apps/details?id=com.walmart.faas.storeassist){target="_blank"}.

- Per l&#39;accesso, gli Associati archivio richiedono le seguenti informazioni:

   - **[!UICONTROL Company name]** associato all’account Store Assist

   - **Memorizza credenziali account di assistenza**: credenziali di nome utente e password per il proprio account.

  Un amministratore Adobe Commerce può creare e gestire [!DNL Store Assist app] account utente per tutte le posizioni del punto vendita che hanno [Prelievo in-store](merchant-store-configuration.md#pickup-location-configuration) nelle impostazioni di Admin Stores.
