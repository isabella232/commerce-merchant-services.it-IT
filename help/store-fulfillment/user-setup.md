---
title: Configurazione utente
description: 'È stata migliorata la configurazione delle sorgenti Inventory management come negozi commerciali. '
role: User, Admin
level: Intermediate
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# Configurazione utente

Gli utenti delle app di Assistenza store vengono gestiti in Adobe Commerce. Tuttavia, questi utenti non interagiscono direttamente con Adobe Commerce. La gestione degli utenti è configurata in Adobe Commerce per abilitare connessioni sicure tra Adobe Commerce e l’app.

Il modello utente dell’app di evasione dell’archivio è separato da altri modelli utente di Adobe Commerce. L’app mantiene il proprio modello di autorizzazione tramite i ruoli utente e gli utenti che possono essere assegnati a tutte le posizioni o a posizioni specifiche. Sono supportate le seguenti autorizzazioni: Ordine di prelievo, ordine di erogazione e riduzione della quantità dell&#39;articolo (e annullamento).

>[!TIP]
>
>Per risultati migliori, [configurare la connessione](connect-set-up-service.md) prima di aggiungere utenti e autorizzazioni per Store Associates che utilizzano l&#39;app Store Assist.

## App Store Assist - Ruoli utente

Durante la configurazione iniziale dell&#39;utente per l&#39;app Store Assist, crea ruoli utente per personalizzare le autorizzazioni dell&#39;utente per l&#39;app Store Assist. Ad esempio, puoi creare ruoli diversi per i responsabili store e i collaboratori dello store e assegnare risorse di ruolo diverse per gestire le autorizzazioni per ogni tipo di utente.

Configura ruoli utente da **[!UICONTROL System > Store Fulfillment App Permissions > All Store Fulfillment App Users]**.

### Informazioni sul ruolo

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|----------------------------|-------------------------|-----------|--------------|
| **[!UICONTROL Role Name]** | Attiva o disattiva l&#39;utente. | Globale | Sì |

### Risorse del ruolo

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Resource Access]** | Elenca i gruppi di autorizzazioni disponibili che possono essere assegnati a un ruolo utente. Al momento, la soluzione di evasione archivio non dispone di diversi livelli di autorizzazione definiti per i ruoli di risorsa. Tutti i ruoli utente dispongono dello stesso accesso alle risorse. | Globale | Sì |

## Assistenza store - Informazioni utente

Gestisci i profili utente dell’app di Assistenza store dalle impostazioni di Admin System:  **[!UICONTROL System > Store Fulfillment App Permissions > All Store Fulfillment App Users]**.


| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL is Active]** | Attiva o disattiva l&#39;utente. | Globale | Sì |
| **[!UICONTROL User Name]** | Nome utente associato all’utente | Globale | Sì |
| **[!UICONTROL First Name]** | Nome associato all’utente | Globale | No |
| **[!UICONTROL Last Name]** | Cognome associato all’utente | Globale | No |
| **[!UICONTROL Role]** | Ruolo associato all’utente | Globale | No |
| **[!UICONTROL Access to all locations]** | Assegna agli utenti l&#39;accesso a tutti i negozi o seleziona singolarmente i negozi. | Globale | No |
| **Impostazioni internazionali interfaccia** | Se lo store dispone di più lingue, impostare le impostazioni internazionali di interfaccia sulla lingua da utilizzare per l’interfaccia di amministrazione. | Globale | No |
| **Attivo da** | Per impostare una data di inizio, seleziona l’icona Calendario . | Globale | No |
| **Attivo a** | Imposta la data di scadenza selezionando l&#39;icona del calendario. L’impostazione di una data di scadenza è utile per impostare le assegnazioni temporanee di utenti o ruoli. Dopo la data di scadenza, lo stato dell’account utente diventa `Inactive`, ma l’account può ancora essere aggiornato se necessario. | Globale | No |





