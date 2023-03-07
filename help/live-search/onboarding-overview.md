---
title: "Panoramica sull’onboarding"
description: "[!DNL Live Search] Flusso di onboarding, requisiti di sistema, limiti e limitazioni"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: 484319fc1df6c29c972b57c13bd0ed711e374e99
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# Panoramica sull’onboarding

Per iniziare a utilizzare [!DNL Live Search] per Adobe Commerce, completa il processo di onboarding per installare l’estensione, configurare le chiavi API e sincronizzare il catalogo.

## Flusso di onboarding

![[!DNL Live Search] diagramma di onboarding](assets/onboarding-flow.svg)

## Requisiti {#requirements}

* [Adobe Commerce](https://magento.com/products/magento-commerce) 2.4.4+
* PHP 8.1, 8.2
* [!DNL Composer]

### Piattaforme supportate

* Adobe Commerce on prem (EE) : 2.4.4+
* Adobe Commerce on Cloud (ECE) : 2.4.4+

## Limiti e soglie

In questo momento, il [!DNL Live Search] l’API di ricerca/categoria ha i seguenti limiti supportati e limiti statici:

### Indicizzazione

* Indice fino a 300 attributi di prodotto per visualizzazione store.
* Indica solo i prodotti dal database di Adobe Commerce.
* Le pagine CMS non sono indicizzate.

### Query

* [!DNL Live Search] non ha accesso alla tassonomia completa dell’albero delle categorie, il che rende alcuni scenari di ricerca di navigazione a più livelli al di fuori della sua portata.
* [!DNL Live Search] utilizza un endpoint GraphQL univoco per le query per supportare funzioni quali il faceting intelligente e la ricerca come si digita. Anche se simile al [API GRAPHQL MAGENTO](https://developer.adobe.com/commerce/webapi/graphql/)Tuttavia, esistono alcune differenze e alcuni campi al momento potrebbero non essere completamente compatibili.

### Regole

* Il numero massimo di regole per visualizzazione archivio è 50.
* Il numero massimo di condizioni per regola è 10.
* Il numero massimo di eventi per regola è 25.

### Sinonimi

* [!DNL Live Search] può gestire fino a 200 sinonimi per ogni visualizzazione store.

### Versione beta di PWA

* L’attuale implementazione beta PWA di Live Search richiede più tempo di elaborazione per restituire i risultati della ricerca rispetto a Live Search con la vetrina nativa di Commerce.
* Versione beta di PWA per [!DNL Live Search] non supporta [gestione degli eventi](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).
* I seguenti attributi di prodotto non sono supportati da GraphQL quando vengono utilizzati in relazione alla versione beta di [PWA](https://developer.adobe.com/commerce/pwa-studio/): `description`, `name`, `short_description`

### Al momento non supportato

* Il [Ricerca avanzata](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) il modulo è disattivato quando [!DNL Live Search] e il collegamento Ricerca avanzata nel piè di pagina della vetrina viene rimosso.
* [Gruppi di prezzi personalizzati](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-group.html)
* Più ubicazioni di magazzino utilizzate da [MCOM](https://experienceleague.adobe.com/docs/commerce-admin/systems/integrations/mcom.html) o altre estensioni OMS
* I prezzi dei prodotti non includono [imposta sul valore aggiunto](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/taxes/vat.html) (IVA)
