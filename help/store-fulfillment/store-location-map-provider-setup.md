---
title: Memorizzazione della posizione e configurazione del sistema di mappatura
description: Configura un provider di distanza per supportare la mappatura della posizione dell'archivio nell'interfaccia utente di vetrina. Le soluzioni Store Fulfillment richiedono un provider a distanza per abilitare la ricerca nel negozio al dettaglio e altre funzionalità di mappatura e pianificazione per il flusso di lavoro di implementazione end-to-end.
role: User, Admin
level: Intermediate
exl-id: d09c4652-e2eb-49dc-8c42-2aa9b6be5d6b
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Impostazione della posizione e della mappatura del negozio

Abilita la posizione dell&#39;archivio e le funzionalità di mappatura per l&#39;evasione dell&#39;archivio configurando un [fornitore a distanza](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html) per cercare i punti vendita al dettaglio.

**Requisiti**

Durante il processo di configurazione, fornisci una chiave API Google per la piattaforma Google Maps. Se non ne hai uno, [generarne una dalla piattaforma Google Maps](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html#configure-google-maps).

Per configurare il provider di distanze:

1. Da **[!UICONTROL Stores > General]** in Admin, aggiungi l’integrazione Google Maps per il tipo di contenuto Mappa .

   - Vai a **[!UICONTROL Stores > Configuration  > General > Content Management]**.

   - Aggiungi la chiave API Google a **[!UICONTROL Google Maps API Key]** campo .

1. Da **[!UICONTROL Stores > Inventory]** in Admin, seleziona il provider di distanza per Store Fulfillment.

   - Vai a **[!UICONTROL Stores > Configuration > Catalog > Inventory]**.

   - Espandi la **[!UICONTROL Distance Provider for Distance Based SSA]** sezione .

   - Imposta la **Provider** a **Mappa Google**.

1. Configura le impostazioni per **[!UICONTROL Google Distance Provider]**.

   - Aggiungi il tuo **Chiave API Google**.

   - Imposta **[!UICONTROL Computation Mode]** a `Driving` e **[!UICONTROL Value]** a `Distance`
