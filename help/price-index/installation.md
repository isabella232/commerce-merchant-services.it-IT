---
title: Installazione dell'indicizzazione dei prezzi SaaS
description: Installazione dell’indicizzazione dei prezzi SaaS
seo-title: SaaS Price Indexing installation
seo-description: Installing SaaS Price indexing
source-git-commit: 077be6d893b800b9571a869237501e58accc01e8
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Installazione dell&#39;indicizzazione dei prezzi SaaS

L&#39;impostazione dell&#39;indicizzazione dei prezzi SaaS richiede l&#39;installazione di nuovi moduli e l&#39;esecuzione di comandi CLI. Per completare l’installazione, gli amministratori devono disporre dell’accesso alla riga di comando.

## Prerequisiti

* Adobe Commerce 2.4.4+
* Almeno uno dei seguenti servizi SaaS installati:

   * [Servizio catalogo](../catalog-service/overview.md)
   * [Live Search](../live-search/guide-overview.md)
   * [Recommendations di prodotto](../product-recommendations/guide-overview.md)

## Installare i moduli richiesti

A seconda della configurazione, il processo di installazione potrebbe essere leggermente diverso.
Ci sono estensioni che aggiungono nuovi feed e codice di supporto ed è presente un&#39;estensione che rimuove il feed dei prezzi predefiniti.

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

Dopo l’aggiornamento sono disponibili tre nuovi feed:

* `prices` - responsabile della consegna dei dati sui prezzi al servizio
* `scopesCustomerGroup` - responsabile della fornitura di gruppi di clienti al servizio
* `scopesWebsite` - responsabile della distribuzione di Siti Web, Store Groups e Store Views al servizio


1. Configura i nuovi feed da impostare in modalità &quot;Aggiorna secondo programma&quot;:

   ```bash
   bin/magento indexer:set-mode schedule catalog_data_exporter_product_prices scopes_customergroup_data_exporter scopes_website_data_exporter
   ```

1. Reindicizza i nuovi feed:

   ```bash
   bin/magento saas:resync --feed=scopesCustomerGroup
   bin/magento saas:resync --feed=scopesWebsite
   bin/magento saas:resync --feed=prices
   ```

Esegui manualmente gli indici di cui sopra, in base alle esigenze. In caso contrario, i dati vengono aggiornati nel processo di sincronizzazione standard. Ulteriori informazioni sulle [Sincronizzazione catalogo](../landing/catalog-sync.md) servizio.

Gli utenti Luma e Adobe Commerce Core GraphQL possono installare `catalog-adapter` modulo che fornisce compatibilità Luma e Core GraphQl e disabilita l’indicizzatore del prezzo di base PHP.
Per utilizzare `catalog-adapter` modulo, [!DNL Live Search] deve prima essere installato. Segui [Installa [!DNL Live Search]](../live-search/install.md) istruzioni prima di continuare.

```bash
composer require adobe-commerce/catalog-adapter
```

Se necessario, l&#39;indicizzatore del prezzo di base PHP può essere riabilitato con il seguente comando:

```bash
bin/magento module:disable Magento_PriceIndexerDisabler
```
