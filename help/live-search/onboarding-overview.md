---
title: "Panoramica sull’onboarding"
description: "[!DNL Live Search] flusso di onboarding, requisiti di sistema, limiti e limitazioni"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: 41d6bed30769d3864d93d6b3d077987a810890cc
workflow-type: tm+mt
source-wordcount: '494'
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

Attualmente, il [!DNL Live Search] l’API di ricerca/categoria ha i seguenti limiti supportati e limiti statici:

### Indicizzazione

* Indice fino a 300 attributi di prodotto per visualizzazione store.
* Indica solo i prodotti dal database di Adobe Commerce.
* I prodotti devono trovarsi nel catalogo condiviso predefinito.
* Le pagine CMS non sono indicizzate.

### Query

* [!DNL Live Search] non ha accesso alla tassonomia completa dell’albero delle categorie, il che rende alcuni scenari di ricerca di navigazione a più livelli al di fuori della sua portata.
* [!DNL Live Search] utilizza un endpoint GraphQL univoco per le query per supportare funzioni quali il faceting dinamico e la ricerca in base al tipo di utente. Anche se simile al [API GRAPHQL](https://developer.adobe.com/commerce/webapi/graphql/), esistono alcune differenze e alcuni campi potrebbero non essere completamente compatibili.

Per limitare i gruppi di clienti utilizzando le autorizzazioni del catalogo:

* I prodotti devono essere assegnati alla categoria principale.
* Al gruppo di clienti &quot;Non connesso&quot; devono essere assegnate autorizzazioni di navigazione &quot;Consenti&quot;.
* Per limitare i prodotti al gruppo di clienti Non connesso, passare a ogni categoria e impostare le autorizzazioni per ogni gruppo di clienti.

### Regole

* Il numero massimo di regole per visualizzazione archivio è 50.
* Il numero massimo di condizioni per regola è 10.
* Il numero massimo di eventi per regola è 25.

### Sinonimi

* [!DNL Live Search] può gestire fino a 200 sinonimi per ogni visualizzazione store.

### Supporto PWA

Il supporto di Live Search è considerato in versione beta perché non tutti i PWA sono stati testati con [!DNL Live Search]. Le funzionalità di base, come la ricerca e la pagina di elenco dei prodotti, funzionano in Venia, ma alcune permutazioni di Graphql potrebbero non funzionare correttamente.

* L’attuale implementazione beta PWA di [!DNL Live Search] richiede più tempo di elaborazione per restituire i risultati di ricerca di [!DNL Live Search] con la vetrina nativa di Commerce.
* [!DNL Live Search] in PWA non supporta [gestione degli eventi](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).
* Filtrare direttamente su `description`, `name`, `short_description` non è supportato da GraphQL se utilizzato con [PWA](https://developer.adobe.com/commerce/pwa-studio/), ma vengono restituiti con un filtro più generale.

### Non attualmente supportato

* Il [Ricerca avanzata](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) il modulo è disattivato quando [!DNL Live Search] e il collegamento Ricerca avanzata nel piè di pagina della vetrina viene rimosso.
* Più ubicazioni di magazzino utilizzate da [MCOM](https://experienceleague.adobe.com/docs/commerce-admin/systems/integrations/mcom.html) o altre estensioni OMS
* I prezzi dei prodotti non includono [imposta sul valore aggiunto](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/taxes/vat.html) (IVA)
* [Prezzo livello](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-tier.html) non è supportato nel widget per pagina popover Live Search e elenco prodotti.

## Cookie

[!DNL Live Search] raccoglie i dati di interazione dell’utente come parte della sua funzionalità di base e i cookie vengono utilizzati per memorizzare tali dati. Quando raccoglie informazioni sull’utente, quest’ultimo deve accettare di memorizzare i cookie. [!DNL Live Search] e [!DNL Product Recommendations] condividere il flusso di dati e quindi lo stesso meccanismo di cookie. Ulteriori informazioni sono disponibili in [Gestire le restrizioni dei cookie](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/setting-cookie.html).
