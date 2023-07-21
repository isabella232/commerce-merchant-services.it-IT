---
title: Posizione archivio e configurazione del sistema di mappatura
description: Configurare un provider di servizi a distanza per supportare la mappatura della posizione del negozio nell'interfaccia utente della vetrina. Le soluzioni Store Fulfillment richiedono un fornitore a distanza per abilitare la ricerca nel punto vendita al dettaglio e altre funzionalità di mappatura e pianificazione per il flusso di lavoro di implementazione end-to-end.
role: Admin
level: Intermediate
feature: Shipping/Delivery, Integration, Tools and External Services, Configuration
exl-id: d09c4652-e2eb-49dc-8c42-2aa9b6be5d6b
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Impostazione della posizione del negozio e della mappatura

Abilitare la posizione del negozio e le funzionalità di mappatura per il Store Fulfillment configurando un [provider di distanze](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html) per cercare le posizioni dei negozi al dettaglio.

**Requisiti**

Durante il processo di configurazione, fornisci una chiave API Google per la piattaforma Google Maps. Se non ne hai uno, [generarne uno dalla piattaforma Google Maps](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html#configure-google-maps).

Per configurare il provider di distanze:

1. Dalla sezione **[!UICONTROL Stores > General]** in Admin, aggiungi l’integrazione Google Maps per il tipo di contenuto Map.

   - Vai a **[!UICONTROL Stores > Configuration  > General > Content Management]**.

   - Aggiungi la chiave API Google a **[!UICONTROL Google Maps API Key]** campo.

1. Dalla sezione **[!UICONTROL Stores > Inventory]** in Admin, selezionare il provider di distanza per Store Fulfillment.

   - Vai a **[!UICONTROL Stores > Configuration > Catalog > Inventory]**.

   - Espandi **[!UICONTROL Distance Provider for Distance Based SSA]** sezione.

   - Imposta il **Provider** a **Google Map**.

1. Configura le impostazioni per **[!UICONTROL Google Distance Provider]**.

   - Aggiungi il **Chiave API Google**.

   - Imposta **[!UICONTROL Computation Mode]** a `Driving` e **[!UICONTROL Value]** a `Distance`
