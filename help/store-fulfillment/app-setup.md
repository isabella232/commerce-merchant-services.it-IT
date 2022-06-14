---
title: Configurazione app
description: '"Imposta il [!DNL Store Assist] app per gestire i flussi di lavoro e i processi di acquisto online, acquistare in store order". '
role: User, Admin
level: Intermediate
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# Configurazione app

Store Assist è un&#39;app di piattaforma FaaS (Compliance-as-a-service) basata su Walmart Commerce Technologies. L’app fornisce funzionalità di implementazione in-store da gestire [!DNL buy online], [!DNL pick up in store] (BOPIS) ordini.

L’app riceve tutte le informazioni sull’ordine e sui clienti, dai dettagli dell’ordine ai tempi di prelievo, e rende i dati disponibili per archiviare i collaboratori online, tramite dispositivi mobili. Con Store Assist, i collaboratori dello store possono vedere quali articoli sono stati ordinati dai clienti, scegliere più rapidamente gli articoli corretti e impostare gli ordini evasi per la consegna in negozio o in blocco ai clienti.

Gli associati al negozio utilizzano l&#39;assistenza al negozio [!UICONTROL Pick], [!UICONTROL Stage], [!UICONTROL Handoff]e [!UICONTROL Orders] per completare il seguente processo di gestione della consegna e del ritiro:

- Assegnare date e ore di consegna dell’ordine
- Ricevi notifiche dai clienti quando arrivano al negozio per il ritiro degli ordini
- Ordini di consegna ai clienti
- Tenere traccia dello stato dell&#39;ordine per tutti gli ordini nelle posizioni store assegnate

Vedi [Archiviare flussi di lavoro di evasione di Assistenza](store-assist-modules.md) per ulteriori informazioni sull’app Store Assist .


## Configurare l’app Store Assist

L&#39;app Store Assist richiede due tipi di configurazione:

- Impostazioni di configurazione dell’amministratore di Adobe Commerce in [Gestisci gli account utente, i ruoli utente e le autorizzazioni delle risorse dalle impostazioni del sistema Adobe Commerce Admin](user-setup.md).

- Impostazioni di configurazione front-end per personalizzare l’interfaccia dell’app Store Assist e altre impostazioni, tra cui:

   - **App Store Assist per marchi**- Personalizza l’interfaccia utente dell’app con il logo e i colori dell’azienda

   - **Aggiornare le istruzioni predefinite**- Personalizza le istruzioni visualizzate nelle interfacce Store Assist per i moduli Pick, Stage, Handoff e Order in modo che i tuoi associati sappiano esattamente cosa fare durante ogni fase del processo di evasione.

   - **Localizzazione**- Seleziona la lingua disponibile per l&#39;app, scegli il formato di data e ora, seleziona le unità di misura predefinite, seleziona la valuta predefinita

   - **Tempo di inattività**- Specifica il tempo di inattività dell&#39;app prima della disconnessione

   - **Cancellazione dal negozio**- Specifica se gli ordini possono essere annullati dall&#39;archivio e quali ruoli dispongono di autorizzazioni di annullamento

   - **Finestra di pulizia ordine**- Specifica per quanto tempo è trascorso il periodo di ritiro pianificato che un ordine raccolto rimane in fase di staging prima di essere ribloccato, ad esempio tre giorni.

   - Personalizza tutte le istruzioni dell’app (scelta, staging, consegna)

   - **Notifiche di prelievo**- Imposta se desideri che le notifiche push inizino a selezionare una volta inserito un ordine

   - **Verifica notifiche**-Imposta se desideri ricevere notifiche push dopo che un cliente ha effettuato l&#39;check-in / è in attesa di X minuti / o nessuna notifica

   - **Processo a mano**- Attiva la firma del cliente, attiva una richiesta per controllare l&#39;ID cliente prima di consegnare l&#39;ordine

   - **Abilita il rifiuto dell&#39;elemento al momento della consegna**

   Collabora con il team di Walmart Commerce Technologies Client Services per completare la configurazione Frontend per l&#39;app Store Assist.

## Download e installazione delle app

Una volta completata la configurazione dell&#39;app Store Assist, Store Associates può scaricare e installare l&#39;app Store Assist sui propri dispositivi mobili e accedere.

- Scarica l’app Store Assist da [Apple App Store](https://apps.apple.com/us/app/store-assist-by-walmart/id16092815390) o Google Play.

- Per effettuare l&#39;accesso, gli associati allo store richiedono le seguenti informazioni:

   - Nome società associato al tuo account Store Assist

   - Memorizza le credenziali dell&#39;account di Assistenza—nome utente e password per il loro account.
   Un amministratore Adobe Commerce può creare gli account utente dell’app di assistenza per lo store per le posizioni degli store che dispongono di [Ritocco nel negozio](merchant-store-configuration.md#pickup-location-configuration) nelle impostazioni di Admin Store.

