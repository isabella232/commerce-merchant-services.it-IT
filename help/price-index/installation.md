---
title: Installazione dell'indicizzazione dei prezzi SaaS
description: Installazione dell'indicizzazione dei prezzi SaaS
seo-title: SaaS Price Indexing installation
seo-description: Installing SaaS Price indexing
exl-id: a607e852-aa04-4be3-9576-a6bf45f8751f
source-git-commit: 3820736a25942b147d6e2c7b8820c360d6a0a535
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---

# Installazione dell&#39;indicizzazione dei prezzi SaaS

L&#39;impostazione dell&#39;indicizzazione dei prezzi SaaS richiede l&#39;installazione di nuovi moduli e l&#39;esecuzione di comandi CLI. Per completare l&#39;installazione, gli amministratori devono poter accedere alla riga di comando.

## Prerequisiti

* Adobe Commerce 2.4.4+
* Almeno uno dei seguenti servizi SaaS installati:

   * [Servizio catalogo](../catalog-service/overview.md)
   * [Live Search](../live-search/guide-overview.md)
   * [Recommendations del prodotto](../product-recommendations/guide-overview.md)

## Installare i moduli richiesti

A seconda della configurazione, il processo di installazione potrebbe essere leggermente diverso.
Esistono estensioni che aggiungono nuovi feed e il codice di supporto, ed è presente un’estensione che rimuove il feed dei prezzi predefinito.

1. Aggiungi i seguenti moduli al tuo `composer.json` file:

   ```json
   "magento/module-saas-price": "102.2.0",
   "magento/module-saas-scopes": "102.2.0",
   "magento/module-product-override-price-remover": "102.2.0",
   "magento/module-bundle-product-override-data-exporter": "102.2.0",
   ```

1. Esegui il comando di aggiornamento:

   ```bash
   bin/magento setup:upgrade
   ```

Dopo l&#39;upgrade, sono disponibili tre nuovi feed:

* `prices` - responsabile della fornitura dei dati sui prezzi al servizio
* `scopesCustomerGroup` - responsabile della fornitura dei gruppi di clienti al servizio
* `scopesWebsite` - responsabile della fornitura di siti Web, gruppi di store e visualizzazioni di store al servizio


1. Configura i nuovi feed da impostare sulla modalità &quot;Aggiorna in base a pianificazione&quot;:

   ```bash
   bin/magento indexer:set-mode schedule catalog_data_exporter_product_prices scopes_customergroup_data_exporter scopes_website_data_exporter
   ```

1. Reindicizzare i nuovi feed:

   ```bash
   bin/magento saas:resync --feed=scopesCustomerGroup
   bin/magento saas:resync --feed=scopesWebsite
   bin/magento saas:resync --feed=prices
   ```

Esegui manualmente gli indicizzatori di cui sopra, in base alle esigenze. In caso contrario, i dati vengono aggiornati nel processo di sincronizzazione standard. Ulteriori informazioni su [Sincronizzazione catalogo](../landing/catalog-sync.md) servizio.

Gli utenti di Luma e Adobe Commerce Core GraphQL possono installare `catalog-adapter` che fornisce compatibilità con Luma e Core GraphQl e disabilita l’indicizzatore del prezzo principale PHP.
Per utilizzare `catalog-adapter` modulo, [!DNL Live Search] e [!DNL Catalog Service] deve prima essere installato e configurato. Segui le [Installa [!DNL Live Search]](../live-search/install.md) e [Installazione di Catalog Service](../catalog-service/installation.md) prima di continuare.

Per configurare Live Search e l&#39;adattatore del catalogo, procedere come segue [Connettore Commerce Services](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html?lang=en) istruzioni.

```bash
composer require adobe-commerce/catalog-adapter
```

Se necessario, l&#39;indicizzatore prezzi PHP di base può essere riattivato con il seguente comando:

```bash
bin/magento module:disable Magento_PriceIndexerDisabler
```
