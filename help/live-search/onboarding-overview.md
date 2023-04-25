---
title: "Panoramica sull'onboarding"
description: "[!DNL Live Search] flusso di onboarding, requisiti di sistema, limiti e limitazioni"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: 86e6fdb653278f3e70640155d697897a2ea1b674
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# Panoramica sull’onboarding

Per iniziare a utilizzare [!DNL Live Search] per Adobe Commerce, completa il processo di onboarding per installare l’estensione, configurare le chiavi API e sincronizzare il catalogo.

## Flusso di onboarding

![[!DNL Live Search] diagramma di onboarding](assets/onboarding-flow.svg)

## Requisiti {#requirements}

* [Adobe Commerce](https://business.adobe.com/products/magento/magento-commerce.html) 2.4.4+
* PHP 8.1 / 8.2
* [!DNL Composer]

### Piattaforme supportate

* Adobe Commerce on-prem (EE) : 2.4.4+
* Adobe Commerce on Cloud (ECE) : 2.4.4+

## Limiti e soglie

Attualmente, il [!DNL Live Search] l’API di ricerca/categoria ha i seguenti limiti supportati e statici:

### Indicizzazione

* Indici fino a 300 attributi di prodotto per visualizzazione store.
* Indici solo i prodotti dal database Adobe Commerce.
* I prodotti devono trovarsi nel Catalogo condiviso predefinito.
* Le pagine CMS non sono indicizzate.

### Query

* [!DNL Live Search] non ha accesso alla tassonomia completa della struttura delle categorie, il che rende alcuni scenari di ricerca di navigazione a più livelli al di fuori della sua portata.
* [!DNL Live Search] utilizza un endpoint GraphQL univoco per le query per supportare funzioni quali il faceting dinamico e la ricerca come utente. Anche se simile al [API GraphQL](https://developer.adobe.com/commerce/webapi/graphql/), esistono alcune differenze e alcuni campi potrebbero non essere completamente compatibili.

Per limitare i gruppi di clienti che utilizzano le autorizzazioni Catalogo:

* I prodotti devono essere assegnati alla categoria Root.
* Al gruppo di clienti &quot;Non connesso&quot; devono essere assegnate le autorizzazioni di navigazione &quot;Consenti&quot;.
* Per limitare i prodotti al gruppo di clienti Not Logged In, vai a ogni categoria e imposta le autorizzazioni per ogni gruppo di clienti.

### Regole

* Il numero massimo di regole per visualizzazione archivio è 50.
* Il numero massimo di condizioni per regola è 10.
* Il numero massimo di eventi per regola è 25.

### Sinonimi

* [!DNL Live Search] può gestire fino a 200 sinonimi per visualizzazione store.

## Indicizzatore dei prezzi

I clienti di Live Search possono utilizzare il nuovo [Indicizzatore prezzo SaaS](../price-index/index.md), che offre aggiornamenti più rapidi dei prezzi e dei tempi di sincronizzazione.

### Supporto PWA

Il supporto per Live Search è considerato in versione beta perché non è stato testato tutto PWA con [!DNL Live Search]. Le funzionalità di base, come la pagina di ricerca e l’elenco dei prodotti, funzionano a Venia ma alcune permutazioni di Graphql potrebbero non funzionare correttamente.

* Implementazione beta PWA corrente di [!DNL Live Search] richiede più tempo di elaborazione per restituire i risultati della ricerca rispetto a [!DNL Live Search] con la vetrina Commerce nativa.
* [!DNL Live Search] in PWA non supporta [gestione degli eventi](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).
* Filtrare direttamente `description`, `name`, `short_description` non è supportato da GraphQL quando viene utilizzato con [PWA](https://developer.adobe.com/commerce/pwa-studio/), ma vengono restituiti con un filtro più generale.

### Non supportato al momento

* La [Ricerca avanzata](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) il modulo è disabilitato quando [!DNL Live Search] e il collegamento Ricerca avanzata nel piè di pagina della vetrina viene rimosso.
* Più posizioni di inventario utilizzate da [MCOM](https://experienceleague.adobe.com/docs/commerce-admin/systems/integrations/mcom.html) o altre estensioni OMS
* I prezzi dei prodotti non includono [imposta sul valore aggiunto](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/taxes/vat.html) (IVA).
* [Prezzo di listino](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-tier.html) non è supportato nel widget Pagina di ricerca dal vivo e Elenco prodotti .

## Cookie

[!DNL Live Search] raccoglie i dati di interazione dell’utente come parte delle sue funzionalità di base e i cookie vengono utilizzati per memorizzare questi dati. Quando raccogli informazioni utente, l&#39;utente deve accettare di memorizzare i cookie. [!DNL Live Search] e [!DNL Product Recommendations] condividere il flusso di dati e quindi lo stesso meccanismo di cookie. Ulteriori informazioni in [Gestire le limitazioni dei cookie](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/setting-cookie.html).
