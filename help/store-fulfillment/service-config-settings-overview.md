---
title: Panoramica della configurazione per l'evasione dello store
description: Scopri i tipi di impostazioni di configurazione dell’amministratore disponibili per personalizzare le funzionalità di esecuzione estese fornite dalla soluzione Store Fulfillment e collegati alle istruzioni per il completamento della configurazione.
role: User, Admin
level: Intermediate
exl-id: c432791a-94a0-457d-9ed9-8937846ce4f4
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 0%

---

# Panoramica sulla configurazione per l&#39;esecuzione dello store

In Adobe Commerce Admin, le impostazioni di configurazione per Store Fulfillment Services di Walmart Commerce Technologies sono suddivise per tipo.

**Memorizza impostazioni di configurazione evasione per tipo**

| **Tipo** | **Descrizione** | **Configurabile API** |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| [Configurazione generale](enable-general.md) | Integrazione generale impostata per la soluzione Store Fulfillment, le sue funzioni attive e le credenziali per la connessione ai servizi di evasione. | No |
| [Configurazione e-mail vendite](sales-emails.md) | Imposta modelli di posta elettronica aggiuntivi per le notifiche dei clienti inviate durante il processo di check-in. | No |
| [Configurazione dell’archivio merchant](merchant-store-configuration.md) | Imposta origini Inventory management avanzate come negozi commerciali. | Sì |
| [Gestione delle scorte di prodotti](product-stock.md) | Configura i messaggi e le funzionalità di stock commerciali disponibili per i clienti. | Sì |
| [Trasferimento origine Inventory management](inventory-stock-transfer.md) | Imposta un nuovo stock, trasferisci il magazzino fuori del magazzino predefinito. | Sì |
| [Configurazione di più siti web/ambiti](multi-site-and-scope-config.md) | Configura risorse e metodi di consegna per più siti web/ambiti store. | No |
| [Configurazione del sistema del processo in background](background-processes.md) | Configura le pianificazioni per i processi in background utilizzati nella sincronizzazione dei dati con i servizi di evasione. | No |
| [Impostazione della posizione e della mappatura del negozio](store-location-map-provider-setup.md) | Configura la possibilità di utilizzare un provider a distanza per cercare i negozi al dettaglio e visualizzare queste informazioni nella mappa SLS | Sì |
| [Configurazione dell’esperienza di check-in](check-in-experience-setup.md) | Configura il colore dell&#39;auto e rende le opzioni che saranno disponibili durante il processo di check-in | Sì |
| [Configurazione utente](user-setup.md) | Gestisci account utente, ruoli e autorizzazioni per i collaboratori dello store che utilizzano l&#39;app Store Assist. ambiti. | Sì |
| [Configurazione app](app-setup.md) | Esamina le configurazioni disponibili per l’app Store Assist necessarie per completare il processo di onboarding. Queste impostazioni non possono essere configurate dall&#39;amministratore di Adobe Commerce. | Sì |

## Utilizzare il riferimento di configurazione

Visualizza il riferimento di configurazione per ogni tipo di impostazione selezionando il nome del tipo nel _Memorizza impostazioni di configurazione evasione per tipo_ tabella.

Nel riferimento di configurazione per ciascun tipo, i dettagli di configurazione vengono visualizzati in una tabella con le seguenti intestazioni di colonna:

- **Campo** fa riferimento al nome del campo da configurare

- **Descrizione** fornisce dettagli importanti sullo scopo e il comportamento del campo

- **Ambito** indica l’ambito di configurazione di Adobe Commerce per l’impostazione (globale, sito web, store)

- **Obbligatorio** il valore indica se è necessario impostare un valore sul campo

Per riferimento tecnico, puoi anche trovare il percorso di configurazione interno per ciascun campo.
