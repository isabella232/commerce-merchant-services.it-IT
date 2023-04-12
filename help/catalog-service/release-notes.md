---
title: '''[!DNL Catalog Service] Note sulla versione"'
description: Informazioni aggiornate sulla versione di [!DNL Catalog Service] per Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: 47163a83d3c79abe7718121492970e34ffbf3643
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# [!DNL Catalog Service] Note sulla versione

Queste note sulla versione descrivono le versioni più recenti di [!DNL Catalog Service] e comprendono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Correzione](../assets/fix.svg) Correzioni e miglioramenti
![Bug](../assets/bug.svg) Problemi noti

## Versione principale corrente

### Versione V1.7

_12 aprile 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Servizio catalogo ora pulisce le varianti di prodotto eliminate.
![Correzione](../assets/fix.svg) Miglioramenti a livello di scalabilità e prestazioni dell&#39;infrastruttura.

#### Limitazioni note

Queste funzionalità non sono ancora supportate:

* Bundle prodotti a prezzo fisso
* La dimensione massima per il payload degli attributi dinamici è 9 MB.
* Prezzo del prodotto del gruppo. Può essere calcolato con prezzi del prodotto semplici.
* In un array di immagini, solo la prima immagine contiene ruoli.

Le seguenti limitazioni possono essere risolte utilizzando la mesh API e l&#39;API GraphQL core:

* Prezzo minimo pubblicizzato
* [Determinazione dei livelli](mesh.md)
* Prodotti scaricabili e carte regalo

### Versione V1.6

_28 marzo 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Sono stati aggiunti dei campioni al [`products`](https://developer.adobe.com/commerce/webapi/graphql/schema/catalog-service/queries/products/) query.
![Nuovo](../assets/new.svg) Aggiunta la possibilità di ottenere `entityId` utilizzo [Rete API](mesh.md).

### Versione V1.5

_6 marzo 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Aggiunto [`categories`](https://developer.adobe.com/commerce/webapi/graphql/schema/catalog-service/queries/categories/) Funzionalità GraphQL.
![Correzione](../assets/fix.svg) Prestazioni e scalabilità API migliorate.

### Versione V1.4

_7 febbraio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stato pubblicato il metapackage del servizio catalogo per semplificare i passaggi di installazione.
![Correzione](../assets/fix.svg) Miglioramenti a livello di scalabilità e prestazioni delle API.

### Versione V1.3

_17 gennaio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Esperienza di onboarding semplificata e migliorata.
![Nuovo](../assets/new.svg) Sono disponibili nuovi endpoint sandbox cliente per i test di preproduzione.
![Nuovo](../assets/new.svg) È stato aggiunto il supporto per i prodotti virtuali.
![Correzione](../assets/fix.svg) Miglioramenti a livello di scalabilità e prestazioni delle API.

### Versione V1.1

_18 novembre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Il servizio Catalogo ora supporta Adobe [Rete API](https://developer.adobe.com/graphql-mesh-gateway/).
![Correzione](../assets/fix.svg) Miglioramento della scalabilità delle API e delle prestazioni complessive.

### Versione V1.0

_4 ottobre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Ora supporta prodotti raggruppati e in bundle.
![Nuovo](../assets/new.svg) Sono state aggiunte le sostituzioni per la visibilità B2B. È ora possibile cercare i prodotti e aggiungerli al carrello per specifici gruppi di clienti.
![Correzione](../assets/fix.svg) Il servizio è ora più stabile e offre prestazioni migliori.

## Versioni precedenti

+++Versioni beta

### Versione 0.3 - Beta+

_12 settembre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Le immagini per il supporto delle varianti: le immagini del prodotto vengono restituite in base alle opzioni selezionate
![Nuovo](../assets/new.svg) Ruoli per il supporto dei prezzi: consentire solo ai membri di gruppi di clienti specifici di vedere il prezzo dei prodotti
![Correzione](../assets/fix.svg) Miglioramento della stabilità e delle prestazioni del servizio
![Nuovo](../assets/new.svg) Gli aggiornamenti vengono ricevuti quando i prodotti vengono eliminati dal catalogo

### Versione beta

_9 agosto 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) La `products` e `refineProduct` le query restituiscono i dati seguenti:

* Attributi di prodotto predefiniti (del sistema).
* Attributi del prodotto dinamici e filtrali in base al ruolo (pagina di visualizzazione del prodotto/pagina di elenco prodotti).
* Opzioni del prodotto.
* Immagini del prodotto e filtrarle in base al ruolo (PDP/PLP).
* Un prezzo specifico per prodotti semplici e fasce di prezzo per prodotti configurabili.
* Prezzi del gruppo di clienti e fasce di prezzo. Restituiscono un prezzo predefinito di fallback ai consumatori senza un gruppo di clienti.
* Tipi di prodotti che utilizzano prezzi specifici per i clienti B2B.

+++
