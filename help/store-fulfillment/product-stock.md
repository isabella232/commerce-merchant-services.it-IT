---
title: Gestione delle scorte di prodotti
description: Configura i messaggi e le funzionalità di stock commerciali disponibili per i clienti.
role: User, Admin
level: Intermediate
exl-id: 3ac217f7-e823-4578-8416-5ecceb76aa87
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---

# Gestione delle scorte di prodotti

Come commerciante, puoi utilizzare Adobe Commerce [Inventory management](https://docs.magento.com/user-guide/catalog/inventory-management.html) opzioni di stock e di origine. Inoltre, è possibile utilizzare la soluzione Store Fulfillment per controllare altre opzioni di disponibilità dell&#39;inventario relative alle operazioni del negozio commerciale.

- Opzione di consegna da negozi Merchant

- Consenti / Disponibile per il ritiro dal negozio

- UPC/SKU/altri identificatori di prodotto univoci

- Soglia esaurita

- Inventario decrescente da posizioni specifiche su ordine

Configura le opzioni di Stock di prodotto dall’amministratore: **[!UICONTROL Catalog > Products > Select Product]**

## **Opzioni stock prodotto**

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|--------------|
| **Disponibile per la distribuzione a domicilio** | Imposta la disponibilità della consegna a domicilio (Spedizione da negozio) per il prodotto. Se abilitata, tutte le posizioni assegnate del negozio di esercenti con inventario disponibile per il prodotto sono considerate idonee per l’opzione Consegna iniziale. Quando questa opzione è disabilitata, il prodotto non è mai idoneo per la distribuzione a domicilio.</br></br>Nella maggior parte dei casi, è sufficiente impostare questa opzione a livello di negozio di merchant. Tuttavia, potrebbero esistere casi unici per prodotti specifici, come quelli soggetti a restrizioni di spedizione federali, che non dovrebbero essere ammessi a Home Delivery. | Sito Web | No |
| **[!UICONTROL Available for Store Pickup]** | Imposta la disponibilità del ritiro dal negozio per il prodotto. Se abilitata, tutte le posizioni assegnate del negozio di esercenti con inventario disponibile per il prodotto sono considerate idonee per l’opzione Ritiro dal negozio . Se disabilitata, il prodotto non è mai idoneo per il ritiro dal negozio.</br></br>Questa opzione può essere utile per tenere traccia dell’inventario commerciale nel sistema che non desideri vendere dal tuo canale e-commerce. | Sito Web | No |
| **[!UICONTROL UPC / SKU / Custom Scannable Identifier]** | Questo attributo deve già esistere come attributo di prodotto e si riferisce al **[!UICONTROL Barcode Source / Barcode Type]** impostazione. Questo attributo viene utilizzato per tenere traccia di un codice a barre digitalizzabile per i prodotti. Questo valore può essere inviato quando un ordine viene inviato agli esercizi commerciali per il prelievo. I collaboratori dello store possono utilizzare il valore con l’elenco di prelievo per far corrispondere i prodotti sullo scaffale utilizzando uno scanner per codici a barre. | Visualizzazione store | No |

{style=&quot;table-layout:auto&quot;}

## Fonti per inventario a livello di prodotto

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Out of Stock Threshold]** | Imposta la soglia di magazzino per l&#39;articolo all&#39;interno di ogni origine. Quando le scorte scendono al di sotto della soglia, sono considerate esaurite alla fonte.</br></br>Per utilizzare l&#39;impostazione di configurazione dell&#39;archivio globale, controlla il **[!UICONTROL Use Default]** opzione . | Globale | No |
| **[!UICONTROL Allow Store Pickup]** | Imposta esplicitamente se l’articolo è disponibile per il ritiro dall’archivio, indipendentemente dalla configurazione di magazzino o dalla posizione dell’archivio commerciale disponibile.</br></br> Per utilizzare l’impostazione a livello di prodotto, deseleziona la [!UICONTROL Use Default] ed effettua la selezione. In caso contrario, questa impostazione viene scelta in base alla configurazione per **[!UICONTROL Allow In-Store Pickup]** che è impostato sulla fonte di magazzino. | Globale | No |

{style=&quot;table-layout:auto&quot;}

