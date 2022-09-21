---
title: '[!DNL Catalog Service] Note sulla versione'
description: Informazioni aggiornate sulla versione di [!DNL Catalog Service] per Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: 372dc1cb567121ab86f606d2ace9f19d8e01170b
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# [!DNL Catalog Service] Note sulla versione

{{catalog-service-beta}}

Queste note sulla versione descrivono le versioni più recenti di [!DNL Catalog Service] e comprendono:

* ![Nuovo](../assets/new.svg) - Nuove funzioni
* ![Correzione](../assets/fix.svg) - Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) - Problemi noti

## Versione 0.3 - Beta+

Data di rilascio: 2022-09-12 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): Stabilità 2.4.x: Beta

![Nuovo](../assets/new.svg) - Supporto delle immagini per varianti: le immagini del prodotto vengono restituite in base alle opzioni selezionate
![Nuovo](../assets/new.svg) - Ruoli per il supporto dei prezzi: consentire solo ai membri di gruppi di clienti specifici di vedere il prezzo dei prodotti
![Correzione](../assets/fix.svg) - Maggiore stabilità e prestazioni del servizio
![Nuovo](../assets/new.svg) - Gli aggiornamenti vengono ricevuti quando i prodotti vengono eliminati dal catalogo

### Limitazioni note

Queste funzionalità non sono ancora supportate:

* Determinazione dei livelli
* Bundle e prodotti raggruppati
* Non vengono ricevuti aggiornamenti quando le varianti vengono eliminate dal catalogo
* Ignorare la visibilità B2B: è possibile cercare i prodotti o aggiungerli al carrello per specifici gruppi di clienti

## Versione beta

Data di rilascio: 2022-08-09 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): Stabilità 2.4.x: Beta

* ![Nuovo](../assets/new.svg) - `products` e `refineProduct` le query restituiscono i dati seguenti:
* Attributi di prodotto predefiniti (del sistema).
* Attributi del prodotto dinamici e filtrali in base al ruolo (pagina di visualizzazione del prodotto/pagina di elenco prodotti).
* Opzioni del prodotto.
* Immagini del prodotto e filtrarle in base al ruolo (PDP/PLP).
* Un prezzo specifico per prodotti semplici e fasce di prezzo per prodotti configurabili.
* Prezzi del gruppo di clienti e fasce di prezzo. Restituiscono un prezzo predefinito di fallback ai consumatori senza un gruppo di clienti.
* Tipi di prodotti che utilizzano prezzi specifici per i clienti B2B.

### Limitazioni note

* I pacchetti e i prodotti raggruppati non sono supportati.
* La determinazione dei prezzi di livello non è supportata.
* In una matrice di immagini, solo la prima immagine contiene ruoli.
* Le immagini per le varianti non vengono recuperate.
* Gli aggiornamenti non vengono ricevuti quando i prodotti o le varianti vengono eliminati dal catalogo.
