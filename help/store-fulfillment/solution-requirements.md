---
title: Requisiti di evasione del negozio
description: Requisiti per il provisioning e l’onboarding di [!DNL Store Fulfillment solution].
role: Leader, Admin, Developer
level: Intermediate
feature: Shipping/Delivery, Install
exl-id: f9e05049-5904-4f6c-b45d-9f81fbc76b69
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 2%

---

# Memorizza requisiti di evasione per Adobe Commerce

Le sezioni seguenti descrivono i requisiti tecnici e aziendali per l’installazione e l’abilitazione della soluzione Store Fulfillment per Adobe Commerce.

## Requisiti di versione della piattaforma e del software

Il [!DNL Store Fulfillment] La soluzione è disponibile per i clienti Adobe Commerce sulle seguenti piattaforme.

- Adobe Commerce sull’infrastruttura cloud (ECE)
- Adobe Commerce on-premise (EE)

La soluzione Store Fulfillment è compatibile con le versioni software elencate nella *Compatibilità software* tabella.

**Compatibilità software**

| **Software** | **Versione minima** | **Versione massima** |
|----------------|---------------------|---------------------|
| Adobe Commerce | 2.4.0 | 2.4.5 |
| Compositore | 1.x | 2.x |
| MariaDB | 10.2 | 10.4 |
| MySQL | 5.7 | 8.0 |
| PHP | 7.4 | 8.1 |

Per i requisiti dettagliati, consulta la sezione Adobe Commerce [Requisiti di sistema](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/system-requirements.html) nel *Guida all’installazione di Adobe Commerce*.

## Requisiti dell’app Store Assist

Il processo end-to-end per gestire gli ordini di ritiro dallo store viene gestito tramite l’app Store Assist installata sui dispositivi mobili. Questi dispositivi, forniti dal rivenditore o dai dipendenti del negozio che utilizzano i propri smartphone personali, devono soddisfare i seguenti requisiti:

**Requisiti minimi del sistema operativo**

- Android 6
- iOS 12

**Requisiti hardware minimi**

- 1 GB di RAM
- 600 MB di spazio libero su disco

## Requisiti aziendali

La tua azienda deve soddisfare i seguenti criteri minimi per implementare la soluzione di Store Fulfillment:

- Solo aziende con sede negli Stati Uniti

- Commercianti da impresa a consumatore (B2C), commercianti di beni di consumo confezionati (CPG) Produttori che vendono direttamente ai consumatori (D2C) o distributori che vendono direttamente ai consumatori o alle piccole imprese

- Almeno un negozio fisico o magazzino

- Gestire l’inventario dei prodotti con Inventory management for Adobe Commerce (o MSI)

- Possibilità di sindacare l’inventario dei commercianti

- Memorizza la disponibilità Wi-Fi in tutte le sedi che supportano la soluzione Store Fulfillment: velocità minima di Internet di 3 Mbps

- Gli associati al negozio e al magazzino hanno accesso a dispositivi mobili iOS o Android durante i loro turni, personali o forniti dal commerciante

- I prodotti gestiti tramite la soluzione Store Fulfillment devono avere attributi di prodotto che includano un codice prodotto SKU o UPC
