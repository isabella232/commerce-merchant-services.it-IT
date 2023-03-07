---
title: '''[!DNL Catalog Service] Note sulla versione'
description: Informazioni aggiornate sulla versione di [!DNL Catalog Service] per Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: 2767de477e274c1855d21d6e678cc6139ff4faa4
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# [!DNL Catalog Service] Note sulla versione

Queste note sulla versione descrivono le versioni più recenti di [!DNL Catalog Service] e includono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Correzione](../assets/fix.svg) Correzioni e miglioramenti
![Bug](../assets/bug.svg) Problemi noti

## Versione principale corrente

### Versione V1.5

Data di rilascio: 2023-3-6 Compatibile con Adobe Commerce (EE): 2.4.4+ Compatibile con Adobe Commerce for Cloud (ECE): 2.4.4+ Stabilità: Disponibilità generale

![Nuovo](../assets/new.svg) Aggiunto [`categories`](https://developer.adobe.com/commerce/webapi/graphql/schema/catalog-service/queries/categories/) funzionalità GraphQL.
![Correzione](../assets/fix.svg) Prestazioni e scalabilità API migliorate.

### Versione V1.4

Data di rilascio: 2023-2-7 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): 2.4.x Stabilità: Disponibilità generale

![Nuovo](../assets/new.svg) È stato pubblicato il metapacchetto catalogo-servizio per semplificare i passaggi di installazione.
![Correzione](../assets/fix.svg) Miglioramenti a livello di scalabilità e prestazioni delle API.

#### Limitazioni note

Queste funzioni non sono ancora supportate:

* Pacchetto prodotti a prezzo fisso
* Non vengono ricevuti aggiornamenti quando le varianti vengono eliminate dal catalogo.
* La dimensione massima per il payload degli attributi dinamici è di 9 MB.
* Prezzo del prodotto di gruppo. Può essere calcolato con prezzi di prodotto semplici.
* In un array di immagini, solo la prima immagine contiene ruoli.
* Campioni colore
* Caricamento della pagina dettagli prodotto tramite l’URL del prodotto.

Le seguenti limitazioni possono essere risolte utilizzando l’API core di GraphQL:

* Prezzo minimo annunciato
* Prezzi a livelli
* Prodotti scaricabili e carte regalo
* Categorie (`categories` e `categoryList`)

### Versione V1.3

Data di rilascio: 2023-1-17 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): 2.4.x Stabilità: Disponibilità generale

![Nuovo](../assets/new.svg) L’esperienza di onboarding è stata semplificata e migliorata.
![Nuovo](../assets/new.svg) Sono disponibili nuovi endpoint sandbox per i clienti per i test di pre-produzione.
![Nuovo](../assets/new.svg) È stato aggiunto il supporto per i prodotti virtuali.
![Correzione](../assets/fix.svg) Miglioramenti a livello di scalabilità e prestazioni delle API.

### Versione V1.1

Data di rilascio: 2022-11-18 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): 2.4.x Stabilità: Disponibilità generale

![Nuovo](../assets/new.svg) Catalog Service ora supporta Adobe [Mesh API](https://developer.adobe.com/graphql-mesh-gateway/).
![Correzione](../assets/fix.svg) Abbiamo migliorato la scalabilità API e le prestazioni complessive.

### Versione V1.0

Data di rilascio: 2022-10-04 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): 2.4.x Stabilità: Disponibilità generale

![Nuovo](../assets/new.svg) Ora supporta prodotti in bundle e raggruppati.
![Nuovo](../assets/new.svg) Sono state aggiunte sostituzioni di visibilità B2B. È ora possibile cercare i prodotti e aggiungerli al carrello per gruppi di clienti specifici.
![Correzione](../assets/fix.svg) Il servizio è ora più stabile e offre prestazioni migliori.

## Versioni precedenti

Versioni +++beta

### Versione 0.3 - Beta+

Data di rilascio: 2022-09-12 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): 2.4.x Stabilità: Beta

![Nuovo](../assets/new.svg) Supporto immagini per varianti: le immagini del prodotto vengono restituite in base alle opzioni selezionate
![Nuovo](../assets/new.svg) Ruoli per supporto prezzi: consente solo ai membri di gruppi di clienti specifici di visualizzare il prezzo dei prodotti
![Correzione](../assets/fix.svg) Miglioramento della stabilità e delle prestazioni del servizio
![Nuovo](../assets/new.svg) Ricevi aggiornamenti quando i prodotti vengono eliminati dal catalogo

### Versione beta

Data di rilascio: 08/08/2022 Compatibile con Adobe Commerce (EE): 2.4.x Compatibile con Adobe Commerce for Cloud (ECE): 2.4.x Stabilità: Beta

![Nuovo](../assets/new.svg) Il `products` e `refineProduct` le query restituiscono i dati seguenti:

* Attributi di prodotto predefiniti (di sistema).
* Attributi di prodotto dinamici e filtrali per ruolo (pagina di visualizzazione prodotto/pagina di elenco prodotti).
* Opzioni prodotto.
* Immagini dei prodotti e filtrale per ruolo (PDP/PLP).
* Un prezzo specifico per prodotti semplici e fasce di prezzo per prodotti configurabili.
* Prezzi e fasce di prezzo del gruppo di clienti. Restituiscono un prezzo predefinito di fallback sugli acquirenti senza un gruppo di clienti.
* Tipi di prodotto che utilizzano prezzi specifici per il cliente B2B.

+++