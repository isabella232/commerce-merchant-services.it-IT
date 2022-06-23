---
title: Requisiti del Negozio
description: Requisiti per il provisioning e l'onboarding [!DNL Store Fulfillment solution].
role: User, Admin
level: Intermediate
exl-id: f9e05049-5904-4f6c-b45d-9f81fbc76b69
source-git-commit: 421c90f4c8bd687216cd48c72f30301a32115522
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 2%

---

# Requisiti per la conformità allo store per Adobe Commerce

Devi soddisfare i seguenti requisiti tecnici e aziendali per installare e abilitare la soluzione Store Fulfillment per Adobe Commerce.

## Requisiti della piattaforma e della versione del software

La [!DNL Store Fulfillment] è disponibile per i clienti Adobe Commerce sulle seguenti piattaforme.

- Adobe Commerce su infrastruttura cloud (ECE)
- Adobe Commerce nei locali (EE)

La soluzione Store Fulfillment è compatibile con le seguenti versioni software.

**Compatibilità software**

| **Software** | **Versione minima** | **Versione massima** |
|----------------|---------------------|---------------------|
| Adobe Commerce | 2.4.0 | 2.4.4 |
| Compositore | 1.x | 2.x |
| MariaDB | 10,2 | 10,4 |
| MySQL | 5,7 | 8,0 |
| PHP | 7.4 | 8.1 |

Per requisiti dettagliati, consulta Adobe Commerce [Requisiti di sistema](https://devdocs.magento.com/guides/v2.4/install-gde/system-requirements.html) nella documentazione per sviluppatori.

## Requisiti dell’app di Assistenza store

Il processo end-to-end per gestire gli ordini di ritiro degli store viene gestito tramite l’app Store Assist installata su dispositivi mobili. Questi dispositivi, forniti dal rivenditore o dai dipendenti del negozio che utilizzano gli smartphone personali, devono soddisfare i seguenti requisiti:

**Requisiti minimi del sistema operativo**

- Android 6
- iOS 12

**Requisiti hardware minimi**

- RAM da 1 GB
- 600 MB di spazio libero su disco

## Requisiti aziendali

Per implementare la soluzione Store Fulfillment, la tua azienda deve soddisfare i seguenti criteri minimi.

- Solo aziende basate negli Stati Uniti

- Rivenditori B2C, produttori di CPG che vendono D2C o distributori che vendono D2C o a piccole imprese

- Almeno un negozio fisico o un magazzino

- Gestisci l’inventario dei prodotti con Inventory management per Adobe Commerce (alias MSI)

- Capacità di diffondere l&#39;inventario dei commercianti

- Archiviare la disponibilità Wi-Fi in tutte le località che supportano la soluzione Store Fulfillment: Velocità minima Internet a 3 Mbps

- I collaboratori del negozio e del magazzino possono accedere ai dispositivi mobili iOS o Android durante i loro spostamenti, personali o forniti dal commerciante

- I prodotti gestiti tramite la soluzione Store Fulfillment devono avere attributi di prodotto che includono un codice di prodotto SKU o UPC
