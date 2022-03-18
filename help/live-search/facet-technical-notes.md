---
title: Note tecniche su facet
description: Note tecniche sull’utilizzo dei facet Live Search.
exl-id: 37982610-0ff7-48b7-b088-be7d2eff8a57
source-git-commit: 7402e97f53b71e488d860215487f4809572b7e6f
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 0%

---

# Note tecniche su facet

Faceting è un metodo di filtraggio ad alte prestazioni che utilizza più dimensioni di valori di attributi statici e dinamici ricercabili come criteri di ricerca.

[!DNL Live Search] utilizza `productSearch` query che restituisce facet e altri dati specifici per [!DNL Live Search]. Fai riferimento a [`productSearch` query](https://devdocs.magento.com/live-search/product-search.html) per esempi di codice.

## Aggregazione di facet

L&#39;aggregazione dei facet viene eseguita come segue se la vetrina ha tre facet (categorie, colore e prezzo) e i filtri dell&#39;acquirente su tutti e tre (colore = blu, prezzo = $ 10,00-50,00, categorie = `promotions`).

* `categories` aggregazione - Aggregati `categories`, si applica `color` e `price` filtri, ma non `categories` filtro.
* `color` aggregazione - Aggregati `color`, si applica `price` e `categories` filtri, ma non `color` filtro.
* `price` aggregazione - Aggregati `price`, si applica `color` e `categories` filtri, ma non `price` filtro.

## Valori attributo predefiniti

I seguenti attributi di prodotto hanno alcuni [proprietà della vetrina](https://docs.magento.com/user-guide/stores/attributes-product.html) che sono abilitati per impostazione predefinita.

| Proprietà | Storefront, proprietà | Attributo |
|---|---|---|
| Ordinabile | Utilizzato per l’ordinamento nell’elenco dei prodotti | `price` |
| Ricerca | Usa nella ricerca | `price` <br />`sku`<br />`name` |
| FilterableInSearch | Utilizzo in Navigazione a livelli - Filtrabile (con risultati) | `price`<br />`visibility`<br />`category_name` |
