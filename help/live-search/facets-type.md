---
title: Tipi di facet
description: I facet Live Search sono dinamici e vengono visualizzati nell’elenco dei filtri se pertinente.
exl-id: 49fb7609-64b3-4ae8-928d-54c99032d919
source-git-commit: 19f0c987ab6b43b6fac1cad266b5fd47a7168e73
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---

# Tipi di facet

Tutto [!DNL Live Search] i facet sono dinamici e compaiono nel *Filtri* elenco solo se pertinente. L’elenco dei facet disponibili cambia in base ai prodotti restituiti. Le seguenti caratteristiche influiscono sulla loro presentazione e sul loro comportamento:

* Facet fissi : i facet più comunemente utilizzati possono essere fissati in cima all’elenco. I facet rimanenti sono elencati in *Tipo di ordinamento* ordinare dopo i facet bloccati.
* Facet intelligenti - Attributi del prodotto che [Adobe Sensei](https://www.adobe.com/sensei.html) trova più pertinente a un set di prodotti e a una query. Il calcolo tiene conto dei metadati degli attributi dell&#39;intero catalogo e determina in fase di query i facet più rilevanti per la query.
* Facet popolari - Attributi del prodotto più spesso presenti nei risultati di ricerca.
* Facet di prezzo - Ritorno prodotti per fascia di prezzo. È possibile specificare il numero di selezioni e l&#39;intervallo di prezzo nella [*Impostazioni*](settings.md) scheda .

Al momento della query, [!DNL Live Search] genera i risultati della ricerca in gruppi di facet intelligenti e popolari.

![Facet - Prezzo](assets/storefront-search-results-run-price.png)

## Opzioni front-end e headless

Facet di cui è stato eseguito il rendering per [!DNL Commerce] storefront viene elaborato dall&#39;adattatore di ricerca, che elabora le richieste ed esegue il rendering dei risultati nella vetrina. Tutto [!DNL Commerce] i facet della vetrina sono ordinati alfabeticamente con opzioni a selezione singola, indipendentemente dal tipo di input assegnato all’attributo corrispondente. I facet disponibili nella vetrina vengono resi in base al tema corrente e riflettono eventuali personalizzazioni apportate alla presentazione della navigazione a livelli.

Al contrario, [senza testa](https://devdocs.magento.com/guides/v2.4/architecture/archi_perspectives/webapi-vision.html) le implementazioni vengono elaborate dall’API e supportano opzioni aggiuntive. I facet headless possono essere ordinati alfabeticamente o per conteggio e possono avere opzioni a selezione singola o multipla.

### Seleziona tipo

Per le implementazioni headless, i facet possono essere definiti come `single select` o `multi-select` con operatori logici che determinano il set di prodotti restituito. Ad esempio: `green AND blue` o `green OR blue`.

![Facet - Seleziona tipo](assets/facets-select-type.png)

| Seleziona tipo | Descrizione |
|--- |--- |
| Selezione singola | Un facet a selezione singola offre più opzioni, ma consente all’acquirente di scegliere un solo valore. |
| Selezione multipla (o) | (Solo senza intestazione) Gli acquirenti possono scegliere più di un&#39;opzione e i prodotti restituiti possono corrispondere a qualsiasi valore selezionato. Esempio: `green OR blue` |
| Selezione multipla (e) | (Solo senza intestazione) Gli acquirenti possono scegliere più di un&#39;opzione e i prodotti restituiti devono corrispondere a tutti i valori selezionati. Esempio: `green AND blue` |

### Etichette dei facet

Per [!DNL Commerce] vetrine, l&#39;etichetta del facet è determinata dal [*Proprietà attributo*](https://docs.magento.com/user-guide/stores/attribute-product-create.html). Per gli archivi con più viste, è possibile definire etichette aggiuntive in *Gestire le etichette*. Per le implementazioni headless, le etichette vengono modificate dalla sezione [area di lavoro di targeting](faceting-workspace.md).

### Tipo di ordinamento

Tutti i facet sottoposti a rendering per la vetrina sono ordinati alfabeticamente. Per le implementazioni headless, i facet possono essere ordinati alfabeticamente o per conteggio.

| Tipo di ordinamento | Descrizione |
|--- |--- |
| Alfabetico | Nella vetrina *Filtri* elenco, i facet sono ordinati alfabeticamente. |
| Conteggio | (Solo headless) Per le implementazioni headless, i facet possono anche essere ordinati in base al numero di valori trovati per facet nel set corrente di prodotti restituiti. |
