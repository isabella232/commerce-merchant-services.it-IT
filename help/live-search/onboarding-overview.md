---
title: Panoramica sull’onboarding
description: Flusso di onboarding di Live Search, requisiti di sistema, limiti e limitazioni
source-git-commit: 6220824c6032a33a760fe5c2bb5d2346e00a074b
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Panoramica sull’onboarding

Per iniziare a utilizzare Live Search per Adobe Commerce, devi completare alcuni passaggi di onboarding per installare l’estensione, configurare le chiavi API e sincronizzare il catalogo.

## Flusso di onboarding

![Diagramma di onboarding di Live Search](assets/onboarding-flow.svg)

## Requisiti {#requirements}

* [Adobe Commerce](https://magento.com/products/magento-commerce) 2.4.x
* PHP 7.3 / 7.4
* [!DNL Composer]

### Piattaforme supportate

* Adobe Commerce su prem (EE) : 2.4.x
* Adobe Commerce on Cloud (ECE) : 2.4.x

## Limiti e soglie

Al momento, l’API di ricerca/categoria Live Search ha i seguenti limiti supportati e limiti statici:

### Indicizzazione

* Indici fino a 300 attributi di prodotto per visualizzazione store
* Indici solo prodotti dal database Adobe Commerce
* Non indicizza le pagine CMS

### Limiti delle query

* Live Search non ha accesso all’intera tassonomia della struttura delle categorie, il che rende alcuni scenari di ricerca di navigazione a più livelli oltre la sua portata.
* Live Search utilizza un endpoint GraphQL univoco per le query per supportare funzioni quali il faceting intelligente e la ricerca come-tu-type. Anche se simile al [API GraphQL di Magento](https://devdocs.magento.com/guides/v2.4/graphql), esistono alcune differenze e alcuni campi potrebbero non essere completamente compatibili al momento.

### Versione beta di PWA

* La versione beta di PWA per Live Search non supporta [gestione degli eventi](https://devdocs.magento.com/shared-services/storefront-events-sdk.html).
* I seguenti attributi di prodotto non sono supportati da GraphQL quando utilizzati in relazione alla versione beta di [PWA](https://developer.adobe.com/commerce/pwa-studio/): `description`, `name`, `short_description`

### Non supportato al momento

* La [Ricerca avanzata](https://docs.magento.com/user-guide/catalog/search-advanced.html) Il modulo viene disattivato quando è installato Live Search e il collegamento Ricerca avanzata nel piè di pagina della vetrina viene rimosso.
* [Gruppi di clienti](https://docs.magento.com/user-guide/customers/customer-groups.html)
* [Gruppi di prezzi personalizzati](https://docs.magento.com/user-guide/catalog/product-price-group.html)
* Più posizioni di inventario utilizzate da [MCOM](https://docs.magento.com/user-guide/mcom.html) o altre estensioni OMS
* [Funzionalità B2B integrate](https://business.adobe.com/products/magento/b2b-ecommerce.html)
