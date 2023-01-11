---
title: "Facet"
description: "[!DNL Live Search] i facet utilizzano più dimensioni di valori di attributo come criteri di ricerca."
exl-id: 63c0b255-6be9-41ad-b4bf-13bb7ff098fd
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Facet

Faceting è un metodo di filtro ad alte prestazioni che utilizza più dimensioni di valori di attributo come criteri di ricerca. La ricerca sfaccettata è simile, ma notevolmente &quot;più intelligente&quot; rispetto allo standard [navigazione a strati](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/navigation/navigation-layered.html). L’elenco dei filtri disponibili è determinato dalla [attributi filtrabili](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/navigation/navigation-layered.html#filterable-attributes) dei prodotti restituiti nei risultati della ricerca.

![Risultati ricerca filtrati](assets/storefront-search-results-run.png)

## Requisiti di risposta

I requisiti degli attributi di categoria e prodotto per la facet sono simili agli attributi filtrabili utilizzati per la navigazione a livelli. Le proprietà storefront di ciascun attributo devono essere impostate su `filterable (with results)`.

Live Search supporta fino a:

* 100 attributi configurati come facet
* 50 attributi ordinabili
* 200 attributi filtrabili
* 200 attributi ricercabili

| Impostazione | Descrizione |
|--- |--- |
| [Impostazioni di visualizzazione delle categorie](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/create/categories-display-settings.html) | Ancoraggio - `Yes` |
| [Proprietà attributo](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/create/attribute-product-create.html) | [Tipo di ingresso catalogo](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/attributes-input-types.html) - `Yes/No`, `Dropdown`, `Multiple Select`, `Price` |
| Proprietà dell&#39;area di archiviazione attributi | Usa nella navigazione a livelli dei risultati di ricerca - `Yes` |

## Valori attributo predefiniti

I seguenti attributi di prodotto hanno [proprietà della vetrina](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) utilizzati da [!DNL Live Search] e abilitata per impostazione predefinita.

| Proprietà | Storefront, proprietà | Attributo |
|---|---|---|
| Ordinabile | Utilizzato per l’ordinamento nell’elenco dei prodotti | `price` |
| Ricerca | Usa nella ricerca | `price` <br />`sku`<br />`name` |
| FilterableInSearch | Utilizzo in Navigazione a livelli - Filtrabile (con risultati) | `price`<br />`visibility`<br />`category_name` |

## Proprietà attributo non di sistema predefinite

La tabella seguente mostra le proprietà di ricerca e filtro predefinite degli attributi non di sistema, inclusi quelli specifici per i dati di esempio Luma. Impostazione della *Usa nella ricerca* attributo property to `Yes` rende l’attributo ricercabile in entrambi [!DNL Live Search] e Adobe Commerce nativo.

| Codice attributo | Ricerca | Utilizzo nella navigazione a livelli |
|--- |--- |--- |
| attività | Sì | Filtrabile (con risultati) |
| attributes_brand | Sì | No |
| brand | Sì | No |
| clima | Sì | Filtrabile (con risultati) |
| collare | Sì | Filtrabile (con risultati) |
| color | Sì | Filtrabile (con risultati) |
| costo | Sì | No |
| eco_collection | Sì | Filtrabile (con risultati) |
| genere | Sì | Filtrabile (con risultati) |
| produttore | Sì | Filtrabile (con risultati) |
| materiale | Sì | Filtrabile (con risultati) |
| scopo | Sì | Filtrabile (con risultati) |
| strap_bag | Sì | Filtrabile (con risultati) |
| style_general | Sì | Filtrabile (con risultati) |

## Proprietà attributo di sistema predefinite

Nella tabella seguente sono illustrate le proprietà di ricerca e filtro predefinite degli attributi di sistema.

| Codice attributo | Ricerca | Utilizzo nella navigazione a livelli |
|--- |--- |--- |
| allow_open_amount | Sì | Filtrabile (con risultati) |
| descrizione | Sì | No |
| name | Sì | No |
| prezzo | Sì | Filtrabile (con risultati) |
| short_description | Sì | No |
| palude | Sì | No |
| status | Sì | No |
| tax_class_id | Sì | No |
| url_key | Sì | No |
| weight | Sì | No |
