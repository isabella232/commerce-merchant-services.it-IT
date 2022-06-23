---
title: Configurazione app
description: Imposta la [!DNL Store Assist] app per gestire i flussi di lavoro e i processi di acquisto online e di evasione dei negozi end-to-end, scegliere gli ordini nei negozi.
role: User, Admin
level: Intermediate
exl-id: bcb5b02b-0141-407a-ad55-6e10e8e1aa90
source-git-commit: 556cbf803a0f8569e8561d2b33b7a976065ae814
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 0%

---

# Configurazione app

Store Assist è un&#39;app di piattaforma FaaS (Compliance-as-a-service) basata su Walmart Commerce Technologies. L’app fornisce funzionalità di implementazione in-store da gestire [!DNL buy online], [!DNL pick up in store] (BOPIS) ordini.  Con Store Assist, i collaboratori dello store possono vedere quali articoli sono stati ordinati dai clienti, scegliere più rapidamente gli articoli corretti e impostare gli ordini evasi per la consegna in negozio o in blocco ai clienti.

L’app Store Assist riceve tutte le informazioni sull’ordine e sui clienti, dai dettagli dell’ordine ai tempi di prelievo, e rende i dati disponibili per archiviare i collaboratori online, tramite dispositivi mobili. L&#39;app include [!UICONTROL Pick], [!UICONTROL Stage], [!UICONTROL Handoff]e [!UICONTROL Orders] moduli per aiutare Store Associates ad attività di evasione come il seguente:

- Assegna date e ore di consegna dell’ordine.
- Ricevi notifiche dai clienti quando arrivano per il ritiro degli ordini.
- Esegui ordini di consegna ai clienti.
- Monitora lo stato dell&#39;ordine per tutti gli ordini nelle posizioni di archiviazione assegnate.

>[!NOTE]
>
>Vedi [Archiviare flussi di lavoro di evasione di Assistenza](store-assist-modules.md) per ulteriori informazioni sull’app Store Assist .

## Configurare l’app Store Assist

L&#39;app Store Assist richiede due tipi di configurazione:

- Impostazioni di configurazione dell’amministratore di Adobe Commerce in [gestire gli account utente, i ruoli utente e le autorizzazioni delle risorse dalle impostazioni del sistema di amministrazione di Adobe Commerce](user-setup.md).

- Impostazioni di configurazione front-end per personalizzare l’interfaccia dell’app Store Assist e altre impostazioni, tra cui:

   - **App Store Assist per marchi**- Personalizza l’interfaccia utente dell’app con il logo e i colori dell’azienda.

   - **Aggiornare le istruzioni predefinite**- Personalizzare le istruzioni contenute nelle interfacce Store Assist per i moduli Pick, Stage, Handoff e Order per rispettare le politiche e le procedure aziendali e guidare Store Associates in ogni fase del flusso di lavoro di evasione.

   - **Localizzazione**- Seleziona la lingua disponibile per l&#39;app. Scegli il formato di data e ora e seleziona le unità di misura predefinite e la valuta predefinita.

   - **Tempo di inattività**- Specifica il tempo di inattività dell&#39;app prima della disconnessione.

   - **Cancellazione dal negozio**- Specifica se gli ordini possono essere annullati dall&#39;archivio e quali ruoli dispongono di autorizzazioni di annullamento

   - **Finestra di pulizia ordine**- Specifica per quanto tempo è trascorso il periodo di ritiro pianificato che un ordine raccolto rimane in fase di staging prima di essere ribloccato, ad esempio tre giorni.

   - Personalizza tutte le istruzioni dell’app (scelta, staging, consegna).

   - **Notifiche di prelievo**- Specifica se inviare una notifica push per avviare il processo di prelievo dopo che un cliente ha effettuato un ordine.

   - **Verifica notifiche**- Specifica se inviare una notifica push durante il processo di check-in per i prelievi degli ordini - dopo il check-in, dopo che il tempo di attesa del cliente supera un periodo di tempo specificato. In alternativa, disattiva la notifica.

   - **Processo a mano**- Abilita i processi facoltativi quando Store Associate consegna l&#39;ordine al cliente, ad esempio richiede una firma del cliente o richiede all&#39;associato di controllare l&#39;ID cliente.

   - **Abilita il rifiuto dell&#39;elemento al momento della consegna**- Consente ai clienti di restituire o annullare gli articoli dell&#39;ordine durante la consegna dell&#39;ordine.
   Collabora con il team di Walmart Commerce Technologies Client Services per completare la configurazione front-end per l&#39;app Store Assist.

## Download e installazione delle app

Una volta completata la configurazione dell&#39;app Store Assist, Store Associates può scaricare, installare e accedere all&#39;app Store Assist dai propri dispositivi mobili.

- Verifica che il dispositivo mobile soddisfi il [requisiti hardware e software](solution-requirements.md#store-assist-app-requirements) per la soluzione Store Fulfillment.

- Scarica l’app Store Assist da [Apple App Store](https://apps.apple.com/us/app/store-assist-by-walmart/id16092815390){target=&quot;_blank&quot;} o [Google Play Store](https://play.google.com/store/apps/details?id=com.walmart.faas.storeassist){target=&quot;_blank&quot;}.

- Per effettuare l&#39;accesso, gli associati allo store richiedono le seguenti informazioni:

   - **[!UICONTROL Company name]** associato all’account Store Assist

   - **Memorizzare le credenziali dell&#39;account Assistenza**- credenziali nome utente e password per il loro account.
   Un amministratore di Adobe Commerce può creare un account utente e impostare le autorizzazioni per gli account utente di Assistenza agli archivi per le posizioni degli archivi che dispongono di [Ritocco nel negozio](merchant-store-configuration.md#pickup-location-configuration) nelle impostazioni di Admin Store.
