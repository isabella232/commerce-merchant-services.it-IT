---
title: "[!DNL Live Search] Indicizzazione"
description: "Scopri come [!DNL Live Search] indicizza le proprietà degli attributi del prodotto."
exl-id: 04441e58-ffac-4335-aa26-893988a89720
source-git-commit: f310f840e286859070002ab0e23eda3787c89f36
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 0%

---

# Indicizzazione

Le proprietà dell’attributo del prodotto (metadati) determinano:

* Utilizzo di un attributo nel catalogo
* Il suo aspetto e il suo comportamento nel negozio
* I dati inclusi nelle operazioni di trasferimento dei dati

L&#39;ambito dei metadati degli attributi è `website/store/store view`.

La [!DNL Live Search] L’API consente a un client di ordinare in base a qualsiasi attributo di prodotto con la [vetrina, proprietà](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) `Use in Search` impostato su `Yes` nell’amministratore di Adobe Commerce. Quando abilitato, `Search Weight` e `Visible in Advanced Search` può essere impostato per l&#39;attributo .

[!DNL Live Search] non indicizza i prodotti eliminati o quelli impostati su `Not Visible Individually`.

>[!NOTE]
>
> Clienti Commerce con [!DNL Live Search] può sfruttare più velocemente i cambiamenti di prezzo aggiornamenti e il tempo di sincronizzazione sui loro siti web con [Indicizzatore prezzo SaaS](../price-index/index.md).

## pipeline di indicizzazione

Il client chiama il servizio di ricerca dalla vetrina per recuperare i metadati dell&#39;indice (filtrabili, ordinabili). Solo gli attributi di prodotto ricercabili con *Utilizzo nella navigazione a livelli* proprietà impostata su `Filterable (with results)` e *Da utilizzare per l’ordinamento nell’elenco dei prodotti* impostato su `Yes` può essere chiamato dal servizio di ricerca.
Per creare una query dinamica, il servizio di ricerca deve sapere quali attributi possono essere ricercati e il loro peso. [!DNL Live Search] rispetta i pesi di ricerca di Adobe Commerce (1-10, dove 10 è la priorità più alta). L’elenco dei dati sincronizzati e condivisi con il servizio catalogo si trova nello schema, definito in:

`vendor/magento/module-catalog-data-exporter/etc/et_schema.xml`

![[!DNL Live Search] indicizzazione del diagramma di ricerca client](assets/indexing-pipeline.svg)

1. Controlla il commerciante per [!DNL Live Search] diritto.
1. Ottieni le viste Store con modifiche ai metadati dell&#39;attributo.
1. Memorizza gli attributi di indicizzazione.
1. Reindicizza l&#39;indice di ricerca.

### Indice completo

Quando [!DNL Live Search] è configurato e sincronizzato durante l&#39;onboarding, può richiedere fino a otto ore per generare l&#39;indice iniziale. Il processo inizia dopo `cron` invia il feed e termina l’esecuzione.

I seguenti eventi attivano una sincronizzazione completa e una build dell&#39;indice:

* Onboarding [sincronizzazione dati catalogo](install.md#synchronize-catalog-data)
* Modifiche ai metadati degli attributi

Ad esempio, la modifica del `Use in Search` proprietà `color` attributo da `No` a `Yes` modifica i metadati dell&#39;attributo in `searchable=true`e attiva una sincronizzazione e una reindicizzazione complete. I seguenti metadati dell&#39;attributo attivano una sincronizzazione completa e una reindicizzazione quando vengono modificati:

* `filterableInSearch`
* `searchable`
* `sortable`
* `visibleInSearch`

### Aggiornamenti dei prodotti in streaming

Dopo la creazione dell&#39;indice iniziale durante [onboarding](install.md#synchronize-catalog-data), i seguenti aggiornamenti incrementali dei prodotti vengono continuamente sincronizzati e reindicizzati:

* Nuovi prodotti aggiunti al catalogo
* Modifiche ai valori degli attributi del prodotto

Ad esempio, l’aggiunta di un nuovo valore campione al `color` viene gestito come aggiornamento del prodotto in streaming.
Flusso di lavoro di aggiornamento streaming:

1. I prodotti aggiornati vengono sincronizzati dall’istanza di Adobe Commerce al servizio catalogo.
1. Il servizio di indicizzazione cerca continuamente gli aggiornamenti dei prodotti dal servizio catalogo. I prodotti aggiornati vengono indicizzati quando arrivano nel servizio catalogo.
1. L’aggiornamento di un prodotto può richiedere fino a 15 minuti per essere disponibile in [!DNL Live Search].

## Ricerca client

La [!DNL Live Search] L’API consente a un cliente di ordinare in base a qualsiasi attributo di prodotto ordinabile impostando [vetrina, proprietà](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html), *Utilizzato per l&#39;ordinamento negli elenchi dei prodotti* a `Yes`. A seconda del tema, questa impostazione fa sì che l’attributo sia incluso come opzione nel [Ordina per](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/navigation/navigation.html) controllo dell’impaginazione nelle pagine di catalogo. È possibile indicizzare fino a 300 attributi di prodotto per [!DNL Live Search]con [proprietà della vetrina](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) ricercabili e filtrabili.
I metadati dell’indice vengono memorizzati nella pipeline di indicizzazione ed è accessibile dal servizio di ricerca.

![[!DNL Live Search] diagramma API dei metadati dell&#39;indice](assets/index-metadata-api.svg)

### Flusso di lavoro degli attributi ordinabili

1. Servizio di ricerca chiamate client.
1. Chiamate al servizio di ricerca Cerca nel servizio di amministrazione.
1. Il servizio di ricerca chiama la pipeline di indicizzazione.

## Indicizzato per tutti i prodotti

L’ordine dei campi in questo elenco corrisponde all’ordine tipico delle colonne nei dati di prodotto esportati.

* `environment_id`
* `website_code`
* `store_code`
* `store_view_code`
* `product_id`
* `sku`
* `name`
* `type`
* `displayable`
* `deleted`
* `url`
* `currency`
* `meta_description`
* `meta_keyword`
* `meta_title`
* `description`
* `short_description`
* `weight`
* `image`
* `small_image`
* `thumbnail_image`
* `prices`
* `in_stock`
* `low_stock`

Il seguente campo è indicizzato per tutti i prodotti configurabili:

* `childrenSkus`
