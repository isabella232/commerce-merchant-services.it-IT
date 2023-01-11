---
title: "Panoramica sull'onboarding"
description: "[!DNL Live Search] flusso di onboarding, requisiti di sistema, limiti e limitazioni"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Panoramica sull’onboarding

Per iniziare a utilizzare [!DNL Live Search] per Adobe Commerce, completa il processo di onboarding per installare l’estensione, configurare le chiavi API e sincronizzare il catalogo.

## Flusso di onboarding

![[!DNL Live Search] diagramma di onboarding](assets/onboarding-flow.svg)

## Requisiti {#requirements}

* [Adobe Commerce](https://magento.com/products/magento-commerce) 2.4.x
* PHP 7.3 / 7.4 / 8.1
* [!DNL Composer]

### Piattaforme supportate

* Adobe Commerce su prem (EE) : 2.4.x
* Adobe Commerce on Cloud (ECE) : 2.4.x

## Limiti e soglie

Al momento, il [!DNL Live Search] l’API di ricerca/categoria ha i seguenti limiti supportati e statici:

### Indicizzazione

* Indici fino a 300 attributi di prodotto per visualizzazione store.
* Indici solo i prodotti dal database Adobe Commerce.
* Le pagine CMS non sono indicizzate.

### Query

* [!DNL Live Search] non ha accesso alla tassonomia completa della struttura delle categorie, il che rende alcuni scenari di ricerca di navigazione a più livelli al di fuori della sua portata.
* [!DNL Live Search] utilizza un endpoint GraphQL univoco per le query per supportare funzioni quali faceting intelligente e search-as-you-type. Anche se simile al [API Magento GraphQL](https://developer.adobe.com/commerce/webapi/graphql/), esistono alcune differenze e alcuni campi potrebbero non essere completamente compatibili al momento.

### Regole

* Il numero massimo di regole per visualizzazione archivio è 50.
* Il numero massimo di condizioni per regola è 10.
* Il numero massimo di eventi per regola è 25.

### Sinonimi

* [!DNL Live Search] può gestire fino a 200 sinonimi per visualizzazione store.

### Versione beta di PWA

* L’attuale implementazione beta PWA di Live Search richiede più tempo di elaborazione per restituire i risultati della ricerca rispetto a Live Search con la vetrina Commerce nativa.
* Versione beta di PWA per [!DNL Live Search] non supporta [gestione degli eventi](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).
* I seguenti attributi di prodotto non sono supportati da GraphQL quando utilizzati in relazione alla versione beta di [PWA](https://developer.adobe.com/commerce/pwa-studio/): `description`, `name`, `short_description`

### Non supportato al momento

* La [Ricerca avanzata](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) il modulo è disabilitato quando [!DNL Live Search] e il collegamento Ricerca avanzata nel piè di pagina della vetrina viene rimosso.
* [Gruppi di prezzi personalizzati](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-group.html)
* Più posizioni di inventario utilizzate da [MCOM](https://experienceleague.adobe.com/docs/commerce-admin/systems/integrations/mcom.html) o altre estensioni OMS
* I prezzi dei prodotti non includono [imposta sul valore aggiunto](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/taxes/vat.html) (IVA).
