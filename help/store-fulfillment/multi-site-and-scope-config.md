---
title: Configurazione di più siti web e ambito
description: Configura risorse e metodi di consegna per più siti web e ambiti di archiviazione.
role: User, Admin
level: Intermediate
exl-id: 8939046e-1c26-4380-83be-ff8e074e591d
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Configurazione di più siti web e ambito

È possibile impostare [Ambito](https://docs.magento.com/user-guide/configuration/scope.html) per alcuni elementi per ospitare più siti web, negozi e viste store:

- [Gestire le azioni](https://docs.magento.com/user-guide/catalog/inventory-stock.html) per ambito

- Gestisci [!DNL Delivery Methods] per ambito

È possibile assegnare le azioni a un sito Web o all&#39;ambito dello store. Quindi, aggiorna le origini store per impostare i metodi di consegna disponibili (consegna principale, ritiro dal negozio).

Dopo aver aggiornato la configurazione con successo, le opzioni di ritiro del negozio nella pagina dei dettagli del prodotto (PDP) nella vetrina Adobe Commerce possono essere selezionate solo per i prodotti disponibili da una sorgente di magazzino che consente il ritiro del negozio.

## Gestire le impostazioni di prelievo nello store

Attiva o disattiva la [!UICONTROL In-Store Pickup] opzioni per ogni sito web o ambito dello store [Configurazioni dei metodi di consegna](enable-general.md#delivery-methods) nell&#39;amministratore.

1. Passa a **[!UICONTROL Stores > Configuration]**.

1. Seleziona l’ambito (sito web da archiviare) da configurare.

1. Con l’ambito selezionato, passa a **[!UICONTROL Sales > Delivery Methods]**.

1. Disattiva o abilita **[!UICONTROL In-Store Pickup]** Metodo di consegna.

Puoi anche gestire se il ritiro dei dati curbside o in-store è disponibile a livello globale in questa sezione.

Gestire [!UICONTROL In-Store Pickup] e [!UICONTROL Delivery Method] impostazioni per fonte di stock. Esistono molte altre configurazioni per garantire la massima flessibilità nell’implementazione.
