---
title: Indicizzazione dei prezzi SaaS
description: Utilizzo dell’indicizzazione dei prezzi SaaS per migliorare le prestazioni
seo-title: Adobe SaaS Price Indexing
seo-description: Price indexing give performance improvements using SaaS infrastructure
exl-id: 747c0f3e-dfde-4365-812a-5ab7768342ab
source-git-commit: 45999b6499f248ea4138f7de4e910c274e747a04
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 0%

---

# Indicizzazione dei prezzi SaaS

L&#39;indicizzazione dei prezzi SaaS accelera il tempo necessario affinché le modifiche dei prezzi si riflettano sul sito web di un cliente dopo che sono state inviate. Questo modulo opzionale consente ai commercianti con cataloghi grandi e complessi o con più siti web o gruppi di clienti di elaborare le modifiche dei prezzi in modo più rapido e continuo.

Il più grande collo di bottiglia del gasdotto: processi pesanti di elaborazione, come l&#39;indicizzazione e il calcolo dei prezzi, sono stati spostati dal nucleo PHP all&#39;infrastruttura Cloud di Adobe. Questo consente ai commercianti di aumentare rapidamente le risorse per aumentare i tempi di indicizzazione dei prezzi e riflettere le modifiche ai siti web a velocità molto più elevate.

Tutti i commercianti che soddisfano i requisiti possono trarre vantaggio da questi miglioramenti, ma quelli che vedranno i maggiori vantaggi sono i clienti con:

* Variazioni costanti del prezzo: I commercianti che richiedono modifiche ripetute dei loro prezzi per soddisfare obiettivi strategici come promozioni frequenti, sconti stagionali o markdown di inventario.
* Siti web multipli e/o gruppi di clienti: Commercianti con cataloghi di prodotti condivisi su più siti web (domini/marchi) e/o gruppi di clienti.
* Un gran numero di prezzi unici tra siti web o gruppi di clienti: Commercianti con ampi cataloghi di prodotti condivisi che contengono prezzi unici su siti web o gruppi di clienti, come i commercianti B2B con prezzi pre-negoziati, marchi con diverse strategie di prezzo.

Se hai applicazioni di terze parti che si basano sull&#39;indicizzatore di prezzo di base PHP, leggi la documentazione e consulta il provider dell&#39;estensione prima di apportare eventuali modifiche.

L’indicizzazione dei prezzi SaaS è disponibile gratuitamente per i clienti che utilizzano i servizi Adobe Commerce.

Questa mini-guida descrive come funziona l’indicizzazione dei prezzi SaaS e come abilitarla.

## Requisiti di sistema

Per utilizzare l&#39;indicizzazione dei prezzi SaaS, è necessario:

* Adobe Commerce 2.4.4+
* Almeno uno dei seguenti servizi SaaS installati:

   * [Servizio catalogo](../catalog-service/overview.md)
   * [Live Search](../live-search/guide-overview.md)
   * [Recommendations di prodotto](../product-recommendations/guide-overview.md)

## Moduli

L’indicizzazione dei prezzi SaaS utilizza un set di moduli per fornire funzionalità. L&#39;elenco dei moduli richiesti potrebbe essere leggermente diverso, a seconda della configurazione dello store.

Questi moduli aggiungono i nuovi feed all’amministratore. Questi feed trasferiscono i dati necessari per il calcolo dei prezzi all’indicizzatore SaaS e ignorano l’indicizzatore dei prezzi di base PHP.

```
magento/module-product-override-price-remover
magento/module-bundle-product-override-data-exporter
magento/module-product-override-price-remover
magento/module-bundle-product-override-data-exporter
```

I clienti che utilizzano Luma e Adobe Commerce Core GraphQL possono installare un modulo che fornisce compatibilità Luma e disabilita l’indicizzatore del prezzo di base PHP:

```
adobe-commerce/catalog-adapter
```

La `catalog-adapter` è compatibile solo con la versione 2.4.5. Il supporto per le versioni 2.4.4 e 2.4.6 verrà rilasciato prossimamente.
L&#39;indicizzatore del prezzo di base PHP può essere riabilitato se necessario da un&#39;estensione di terze parti o per qualsiasi altro motivo.

## Avvertenze

A seconda di fattori come i tipi di prodotto, la complessità dei prezzi e la dimensione del catalogo, l&#39;indicizzazione dei prezzi SaaS può essere la soluzione giusta per il vostro negozio. Leggi le seguenti limitazioni e stabilisci se si tratta di una buona soluzione per il tuo sito.

Attualmente, l&#39;indicizzazione dei prezzi SaaS supporta i tipi di prodotto Semplici, Raggruppati, Virtuali, Configurabili e Bundle Dynamic.
Il supporto per i tipi di prodotti Scaricabili, Carte regalo e Bundle Fisso sarà presto disponibile.

L&#39;indicizzazione dei prezzi SaaS supporta i prezzi base:

* Prezzo normale min/max
* Prezzo finale min/max
* Prezzi speciali
* Prezzi del gruppo di clienti
* Prezzi delle regole del catalogo

Una volta scelto di utilizzare il nuovo feed di prezzo, è possibile contattare [Supporto](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html) per annullare l&#39;operazione.

I nuovi feed devono essere sincronizzati manualmente con il `resync` [Comando CLI](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/data-services/catalog-sync.html#resynccmdline). In caso contrario, i dati vengono aggiornati nel processo di sincronizzazione standard. Ulteriori informazioni sulle [Sincronizzazione catalogo](../landing/catalog-sync.md) processo.

## Scenari di utilizzo

### Luma senza dipendenze di estensione

* Un commerciante GraphQL di base Luma o Abode Commerce che ha installato un servizio richiesto (Live Search, Recommendations prodotto, Servizio catalogo)
* Nessuna estensione di terze parti che si basa sull&#39;indicizzatore del prezzo di base PHP
* Vendita di prodotti dinamici semplici, configurabili, raggruppati, virtuali e raggruppati

1. Abilita nuovi feed.
1. Installare l&#39;adattatore catalogo.

### Grafico principale di Luma e Adobe Commerce con dipendenze dell’indicizzatore dei prezzi di base PHP

* Un commerciante GraphQL di base Luma o Abode Commerce che ha installato un servizio supportato (Live Search, Product Recommendations, Catalog Service)
* Con un&#39;estensione di terze parti che si basa sul PHP core price indexer
* Vendita di prodotti dinamici semplici, configurabili, raggruppati, virtuali e raggruppati

1. Abilitare i nuovi feed
1. Installare l&#39;adattatore catalogo.
1. Riattiva l&#39;indicizzatore del prezzo di base PHP.
1. Utilizza nuovi feed e il codice di compatibilità Luma nel `catalog-adapter` modulo .

### Commerciante senza testa

* Un commerciante headless con un servizio supportato installato (Live Search, Product Recommendations, Catalog Service)
* Nessun affidamento su PHP core price indexer
* Vendita di prodotti dinamici semplici, configurabili, raggruppati, virtuali e raggruppati

1. Abilitare nuovi feed
1. Installa l&#39;adattatore di catalogo, che disabilita l&#39;indicizzatore del prezzo di base PHP.

### Luma/Core GraphQL/Headless con tipi di prodotto non supportati

* Commerciante Luma/Headless
* Vendita di buoni regalo, prodotti scaricabili o prodotti fissi in bundle

Con i tipi di prodotto attualmente non supportati, attendi il supporto completo per i tipi di prodotto.
