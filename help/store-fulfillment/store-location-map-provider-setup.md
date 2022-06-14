---
title: Memorizzazione della posizione e configurazione del sistema di mappatura
description: Configura un provider di distanza per supportare la mappatura della posizione dell'archivio nell'interfaccia utente di vetrina.
role: User, Admin
level: Intermediate
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Impostazione di posizione e mappatura store

Abilita la posizione dell&#39;archivio e le funzionalità di mappatura per l&#39;evasione dell&#39;archivio configurando un [fornitore a distanza](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html) per cercare i punti vendita al dettaglio.

**Requisiti**

Durante il processo di configurazione, fornisci una chiave API Google per la piattaforma Google Maps. Se non ne hai uno, [generarne una dalla piattaforma Google Maps](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html#configure-google-maps).

Per configurare il provider di distanze:

1. Da [!UICONTROL Stores > General] in Admin, aggiungi l’integrazione Google Maps per il tipo di contenuto Mappa .

   - Vai a **[!UICONTROL Stores > Configuration  > General > Content Management]**.

   - Aggiungi la chiave API Google a **[!UICONTROL Google Maps API Key]** campo .

1. Da [!UICONTROL Stores > Inventory] in Admin, seleziona il provider di distanza per Store Fulfillment.

   - Vai a **[!UICONTROL Stores > Configuration > Catalog > Inventory]**.

   - Espandi la **[!UICONTROL Distance Provider for Distance Based SSA]** sezione .

   - Imposta la **Provider** a **Mappa Google**.

1. Configura le impostazioni per **[!UICONTROL Google Distance Provider]**.

   - Aggiungi il tuo **Chiave API Google**.

   - Imposta **[!UICONTROL Computation Mode]** a `Driving` e **[!UICONTROL Value]** a `Distance`

