---
title: "Note tecniche facet"
description: "Note tecniche sull’utilizzo di [!DNL Live Search] facet."
exl-id: 37982610-0ff7-48b7-b088-be7d2eff8a57
source-git-commit: 995f528abc0011c6ae7c4c524982c301072ec2eb
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Note tecniche facet

Il faceting è un metodo di filtraggio ad alte prestazioni che utilizza come criteri di ricerca più dimensioni di valori di attributi statici e dinamici ricercabili.

[!DNL Live Search] utilizza `productSearch` query che restituisce faceting e altri dati specifici di [!DNL Live Search]. Fai riferimento a [`productSearch` query](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/) per esempi di codice.

## Aggregazione facet

L’aggregazione delle sfaccettature viene eseguita come segue: se la vetrina ha tre sfaccettature (categorie, colore e prezzo) e i filtri cliente su tutte e tre (colore = blu, prezzo = $ 10.00-50,00, categorie = `promotions`).

* `categories` aggregazione - Aggregati `categories`, quindi applica il `color` e `price` filtri, ma non `categories` filtro.
* `color` aggregazione - Aggregati `color`, quindi applica il`price` e `categories` filtri, ma non `color` filtro.
* `price` aggregazione - Aggregati `price`, quindi applica il `color` e `categories` filtri, ma non `price` filtro.
