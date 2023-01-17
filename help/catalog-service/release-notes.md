---
title: '[!DNL Catalog Service] Note sulla versione'
description: Informazioni aggiornate sulla versione di [!DNL Catalog Service] per Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: cfa0b505b0fb793bbc072f9f837551b7e67e9721
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Catalog Service] Note sulla versione

Queste note sulla versione descrivono le versioni più recenti di [!DNL Catalog Service] e comprendono:

* ![Nuovo](../assets/new.svg) Nuove funzioni
* ![Correzione](../assets/fix.svg) Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) Problemi noti

## Versione V1.3

Data di rilascio: 2023-1-17 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): Stabilità 2.4.x: Disponibilità generale

![Nuovo](../assets/new.svg) Esperienza di onboarding semplificata e migliorata.
![Nuovo](../assets/new.svg) Sono disponibili nuovi endpoint sandbox cliente per i test di preproduzione.
![Nuovo](../assets/new.svg) È stato aggiunto il supporto per i prodotti virtuali.
![Correzione](../assets/fix.svg) Miglioramenti a livello di scalabilità e prestazioni delle API.

### Limitazioni note

Queste funzionalità non sono ancora supportate:

* Bundle prodotti a prezzo fisso
* Non vengono ricevuti aggiornamenti quando le varianti vengono eliminate dal catalogo.
* La dimensione massima per il payload degli attributi dinamici è 9 MB.
* Prezzo del prodotto del gruppo. Può essere calcolato con prezzi del prodotto semplici.
* In un array di immagini, solo la prima immagine contiene ruoli.
* Campioni colore
* Caricamento della pagina dei dettagli del prodotto tramite l’URL del prodotto.

Le seguenti limitazioni possono essere risolte utilizzando l’API GraphQL:

* Prezzo minimo pubblicizzato
* Determinazione dei livelli
* Prodotti scaricabili e carte regalo
* Categorie (`categories` e `categoryList`)

## Versione V1.1

Data di rilascio: 2022-11-18 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): Stabilità 2.4.x: Disponibilità generale

![Nuovo](../assets/new.svg) Il servizio Catalogo ora supporta Adobe [Rete API](https://developer.adobe.com/graphql-mesh-gateway/).
![Correzione](../assets/fix.svg) Abbiamo migliorato la scalabilità delle API e le prestazioni complessive.

### Limitazioni note

Queste funzionalità non sono ancora supportate:

* Bundle prodotti a prezzo fisso
* Non vengono ricevuti aggiornamenti quando le varianti vengono eliminate dal catalogo.
* La dimensione massima per il payload degli attributi dinamici è 9 MB.
* Prezzo del prodotto del gruppo. Può essere calcolato con prezzi del prodotto semplici.
* In un array di immagini, solo la prima immagine contiene ruoli.
* Campioni colore
* Caricamento della pagina dei dettagli del prodotto tramite l’URL del prodotto.

Le seguenti limitazioni possono essere risolte utilizzando l’API GraphQL:

* Prezzo minimo pubblicizzato
* Determinazione dei livelli
* Prodotti scaricabili e carte regalo
* Categorie (`categories` e `categoryList`)

## Versione V1.0

Data di rilascio: 2022-10-04 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): Stabilità 2.4.x: Disponibilità generale

![Nuovo](../assets/new.svg) Ora supporta prodotti raggruppati e in bundle.
![Nuovo](../assets/new.svg) Sono state aggiunte le sostituzioni per la visibilità B2B. È ora possibile cercare i prodotti e aggiungerli al carrello per specifici gruppi di clienti.
![Correzione](../assets/fix.svg) Il servizio è ora più stabile e offre prestazioni migliori.

### Limitazioni note

Queste funzionalità non sono ancora supportate:

* Determinazione dei livelli
* Gli aggiornamenti non vengono ricevuti quando le varianti vengono eliminate dal catalogo
* La dimensione massima per il payload degli attributi dinamici è &lt;9MB
* Prezzo fisso per i prodotti bundle
* Prezzo totale per i prodotti raggruppati
* Supporto per tipi di prodotti virtuali, scaricabili e con carta regalo
* Prezzo pubblicizzato minimo (MAP)

## Versione 0.3 - Beta+

Data di rilascio: 2022-09-12 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): Stabilità 2.4.x: Beta

![Nuovo](../assets/new.svg) Le immagini per il supporto delle varianti: le immagini del prodotto vengono restituite in base alle opzioni selezionate
![Nuovo](../assets/new.svg) Ruoli per il supporto dei prezzi: consentire solo ai membri di gruppi di clienti specifici di vedere il prezzo dei prodotti
![Correzione](../assets/fix.svg) Miglioramento della stabilità e delle prestazioni del servizio
![Nuovo](../assets/new.svg) Gli aggiornamenti vengono ricevuti quando i prodotti vengono eliminati dal catalogo

### Limitazioni note

Queste funzionalità non sono ancora supportate:

* Determinazione dei livelli
* Bundle e prodotti raggruppati
* Non vengono ricevuti aggiornamenti quando le varianti vengono eliminate dal catalogo
* Ignorare la visibilità B2B: è possibile cercare i prodotti o aggiungerli al carrello per specifici gruppi di clienti

## Versione beta

Data di rilascio: 2022-08-09 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): Stabilità 2.4.x: Beta

![Nuovo](../assets/new.svg) La `products` e `refineProduct` le query restituiscono i dati seguenti:

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
