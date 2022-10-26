---
title: '[!DNL Catalog Service]'
description: '''[!DNL Catalog Service] per Adobe Commerce fornisce un modo per recuperare il contenuto delle pagine di visualizzazione dei prodotti e delle pagine di elenco dei prodotti molto più rapidamente rispetto alle query native di Adobe Commerce GraphQL."'
exl-id: 266faca4-6a65-4590-99a9-65b1705cac87
source-git-commit: 7ab545b8e3d9a795be7ff43246e102b366ad94bd
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 0%

---

# [!DNL Catalog Service] per Adobe Commerce

La [!DNL Catalog Service] per l&#39;estensione Adobe Commerce fornisce dati di catalogo basati su modelli di visualizzazione avanzati (sola lettura) per eseguire rapidamente e completamente il rendering di esperienze storefront correlate al prodotto, tra cui:

* Pagine dei dettagli del prodotto
* Pagine dell’elenco dei prodotti e delle categorie
* Pagine dei risultati di ricerca
* Caroselli di prodotti
* Pagine di confronto dei prodotti
* Qualsiasi altra pagina che esegue il rendering dei dati di prodotto, ad esempio le pagine del carrello, dell’ordine e dell’elenco dei desideri

La [!DNL Catalog Service] utilizza [GraphQL](https://graphql.org/) per richiedere e ricevere i dati di prodotto. GraphQL è un linguaggio di query utilizzato da un client front-end per comunicare con l’interfaccia API (Application Programming Interface) definita su un backend come Adobe Commerce. GraphQL è un metodo di comunicazione popolare perché è leggero e consente a un integratore di sistema di specificare il contenuto e l&#39;ordine di ogni risposta.

Adobe Commerce dispone di due sistemi GraphQL. Il sistema GraphQL di base fornisce un&#39;ampia gamma di query (operazioni di lettura) e mutazioni (operazioni di scrittura) che consentono a un acquirente di interagire con molti tipi di pagine, tra cui prodotto, account cliente, carrello, checkout e altro ancora. Tuttavia, le query che restituiscono informazioni di prodotto non sono ottimizzate per la velocità. Il sistema GraphQL dei servizi può eseguire query solo su prodotti e informazioni correlate. Queste query sono più performanti rispetto a query di base simili.

## Architettura

Il diagramma seguente mostra i due sistemi GraphQL:

![Diagramma dell’architettura del catalogo](assets/catalog-service-architecture.png)

Nel sistema GraphQL principale, PWA invia una richiesta all’applicazione Commerce, che riceve ogni richiesta, la elabora, eventualmente inviando una richiesta tramite più sottosistemi, quindi restituisce una risposta alla vetrina. Questo round trip può causare rallentamenti dei tempi di caricamento delle pagine, che possono causare tassi di conversione inferiori.

[!DNL Catalog Service] è un servizio gateway GraphQL federato. Il servizio accede a un database separato che contiene i dettagli del prodotto e le relative informazioni, ad esempio attributi di prodotto, varianti, prezzi e categorie. Il servizio mantiene il database sincronizzato con Adobe Commerce tramite indicizzazione.
Poiché il servizio evita la comunicazione diretta con l’applicazione, è in grado di ridurre la latenza del ciclo di richiesta e risposta.

>[!NOTE]
>
>Il gateway è per l’integrazione futura con Product Recommendations. In questa versione, puoi accedere al [!DNL Catalog Service Federated GraphQL] e [!DNL Live Search] query federate dallo stesso endpoint se si dispone di una chiave di licenza valida per entrambi i prodotti.

I sistemi GraphQL di base e di servizio non comunicano direttamente tra loro. Puoi accedere a ogni sistema da un URL diverso e le chiamate richiedono informazioni di intestazione diverse. I due sistemi GraphQL sono progettati per essere utilizzati insieme. La [!DNL Catalog Service] Il sistema GraphQL potenzia il sistema di base per rendere più veloci le esperienze sulla vetrina dei prodotti.

Facoltativamente, puoi implementare [Rete API per Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/) per integrare i due sistemi GraphQL di Adobe Commerce con API private e di terze parti e altre interfacce software tramite Adobe Developer. La mesh può essere configurata per garantire che le chiamate indirizzate a ciascun endpoint contengano le informazioni di autorizzazione corrette nelle intestazioni.

## Dettagli architettonici

Le sezioni seguenti descrivono alcune delle differenze tra i due sistemi GraphQL.

### Gestione dello schema

Poiché Catalog Service funziona come un servizio, gli integratori non devono preoccuparsi della versione sottostante di Commerce. La sintassi delle query è la stessa per tutte le versioni. Inoltre, lo schema è coerente per tutti i merchants. Questa coerenza semplifica la definizione delle best practice e aumenta notevolmente il riutilizzo dei widget di vetrina.

### Semplificazione dei tipi di prodotto

Lo schema riduce la diversità dei tipi di prodotto in due casi d’uso:

* I prodotti semplici sono quelli definiti con un unico prezzo e quantità. Il servizio catalogo mappa i tipi di prodotti semplici, virtuali, scaricabili e con carta regalo in `simpleProductViews`.

* I prodotti complessi sono costituiti da più prodotti semplici. I prodotti semplici componenti possono avere prezzi diversi. È inoltre possibile definire un prodotto complesso in modo che l’acquirente possa specificare la quantità di prodotti semplici componenti. Il servizio catalogo mappa i tipi di prodotto configurabili, raggruppati e raggruppati in `complexProductViews`.

Le opzioni di prodotto complesse sono unificate e distinte in base al loro comportamento, non in base al tipo. Ogni valore di opzione rappresenta un prodotto semplice. Questo valore di opzione ha accesso agli attributi di prodotto semplici, tra cui prezzo. Quando l&#39;acquirente seleziona tutte le opzioni per un prodotto complesso, la combinazione delle opzioni selezionate punta a un prodotto semplice specifico. Il prodotto semplice rimane ambiguo finché l&#39;acquirente non seleziona un valore per tutte le opzioni disponibili.

### Prezzi

I prodotti semplici rappresentano l&#39;unità di vendita di base che ha un prezzo. Servizio catalogo calcola il prezzo regolare prima degli sconti e il prezzo finale dopo gli sconti. I calcoli dei prezzi possono includere imposte sui prodotti fissi. Escludono le promozioni personalizzate.

Un prodotto complesso non ha un prezzo fisso. Al contrario, Servizio catalogo restituisce i prezzi delle semplificazioni collegate. Ad esempio, un commerciante può assegnare inizialmente gli stessi prezzi a tutte le varianti di un prodotto configurabile. Se determinate dimensioni o colori sono impopolari, il commerciante può ridurre i prezzi di tali varianti. Pertanto, il prezzo del prodotto complesso (configurabile) all&#39;inizio mostra una fascia di prezzo, riflettendo il prezzo sia delle varianti standard che impopolari. Dopo che l&#39;acquirente ha selezionato un valore per tutte le opzioni disponibili, la vetrina visualizza un prezzo unico.

## Implementazione

Il processo di installazione richiede la configurazione del [Connettore Commerce Services](../landing/saas.md). Una volta completata questa operazione, il passaggio successivo consiste nell&#39;aggiornare il codice della vetrina per incorporare il [!DNL Catalog Service] query. Tutto [!DNL Catalog Service] le query vengono instradate al gateway GraphQL. L’URL viene fornito durante il processo di onboarding.
