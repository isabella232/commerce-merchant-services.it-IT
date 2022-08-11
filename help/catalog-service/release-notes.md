---
title: '''[!DNL Catalog Service] Note sulla versione'''
description: Informazioni aggiornate sulla versione di [!DNL Catalog Service] per Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: 72913e0c0b7364e38d37fe1a8279c40a4e849c02
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 2%

---

# [!DNL Catalog Service] Note sulla versione

{{catalog-service-beta}}

Queste note sulla versione descrivono le versioni più recenti di [!DNL Catalog Service] e comprendono:

* ![Nuovo](../assets/new.svg) - Nuove funzioni
* ![Correzione](../assets/fix.svg) - Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) - Problemi noti

## Versione beta

* ![Nuovo](../assets/new.svg) - `products` e `refineProduct` le query restituiscono i dati seguenti:
   * Attributi di prodotto predefiniti (del sistema).
   * Attributi del prodotto dinamici e filtrali in base al ruolo (pagina di visualizzazione del prodotto/pagina di elenco prodotti).
   * Opzioni del prodotto.
   * Immagini del prodotto e filtrarle in base al ruolo (PDP/PLP).
   * Un prezzo specifico per prodotti semplici e fasce di prezzo per prodotti configurabili.
   * Prezzi del gruppo di clienti e fasce di prezzo. Restituiscono un prezzo predefinito di fallback ai consumatori senza un gruppo di clienti.
   * Tipi di prodotti che utilizzano prezzi specifici per i clienti B2B.

## Limitazioni note

* I pacchetti e i prodotti raggruppati non sono supportati.
* La determinazione dei prezzi di livello non è supportata.
* In una matrice di immagini, solo la prima immagine contiene ruoli.
* Le immagini per le varianti non vengono recuperate.
* Gli aggiornamenti non vengono ricevuti quando i prodotti o le varianti vengono eliminati dal catalogo.
