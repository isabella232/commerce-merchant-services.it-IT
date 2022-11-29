---
title: Onboarding e installazione
description: Scopri come installare [!DNL Catalog Service]
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: 4604aacc19d7740c63b39134bd9f4c146479ac8f
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---

# Onboarding e installazione

## Prerequisiti

Il processo di onboarding per [!DNL Catalog Service] richiede l&#39;accesso alla riga di comando del server. Se non hai familiarità con l’utilizzo della riga di comando, chiedi aiuto a uno sviluppatore o a un integratore di sistema.

### Requisiti software

- Adobe Commerce 2.4.x
- PHP 8.1, 7.4, 7.3
- Compositore: 2.x, 1.x

### Piattaforme supportate

- Adobe Commerce sull’infrastruttura cloud: 2.4.x
- Adobe Commerce nei locali: 2.4.x

## Installare l’estensione

È possibile installare [!DNL Catalog Service] estensione sia per Adobe Commerce sull’infrastruttura cloud che per le istanze locali.

La [!DNL Catalog Service] è installato con le chiavi del Compositore, collegate all’account Commerce [mageid](https://developer.adobe.com/commerce/marketplace/guides/sellers/profile-personal/#field-descriptions) fornito nel processo di registrazione. Il Compositore utilizza queste chiavi durante l&#39;installazione iniziale di [!DNL Adobe Commerce]o in situazioni in cui le chiavi del Compositore non sono state precedentemente salvate nel `auth.json` file.

Vedi [Ottieni le chiavi di autenticazione](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) per ulteriori informazioni su come ottenere le chiavi Composer.

### Adobe Commerce su infrastruttura cloud

Utilizzare questo metodo per installare [!DNL Catalog Service] estensione per un&#39;istanza Commerce Cloud.

1. Apri `<Commerce_root>/composer.json` in un editor di testo e aggiorna il `require` come segue:

   ```json
   "require": {
      "magento/module-saas-catalog": "^101.4.0",
      "magento/module-saas-product-override": "^101.4.0",
      "magento/module-saas-product-variant": "^101.4.0",
      "magento/module-bundle-product-data-exporter": "^101.3.1",
      "magento/module-catalog-data-exporter": "^101.3.1",
      "magento/module-catalog-inventory-data-exporter": "^101.3.1",
      "magento/module-catalog-url-rewrite-data-exporter": "^101.3.1",
      "magento/module-configurable-product-data-exporter": "^101.3.1",
      "magento/module-data-exporter": "^101.3.1",
      "magento/module-parent-product-data-exporter": "^101.3.1",
      "magento/module-product-override-data-exporter": "^101.3.1",
      "magento/data-services": "^7.0.11",
      "magento/services-id": "^3.0.1",
      "magento/services-connector": "1.2.1"
    }
   ```

1. Verifica la nuova configurazione localmente e aggiorna le dipendenze:

   ```bash
   composer update
   ```

   Il comando aggiorna tutte le dipendenze.

1. Conferma e invia le modifiche per `composer.json` e `composer.lock`.

### Presso i locali

Utilizzare questo metodo per installare [!DNL Catalog Service] estensione per un&#39;istanza locale.

1. Apri `<Commerce_root>/composer.json` in un editor di testo e aggiorna il `require` come segue:

   ```json
   "require": {
    "magento/module-saas-catalog": "^101.4.0",
    "magento/module-saas-product-override": "^101.4.0",
    "magento/module-saas-product-variant": "^101.4.0",
    "magento/module-bundle-product-data-exporter": "^101.3.1",
    "magento/module-catalog-data-exporter": "^101.3.1",
    "magento/module-catalog-inventory-data-exporter": "^101.3.1",
    "magento/module-catalog-url-rewrite-data-exporter": "^101.3.1",
    "magento/module-configurable-product-data-exporter": "^101.3.1",
    "magento/module-data-exporter": "^101.3.1",
    "magento/module-parent-product-data-exporter": "^101.3.1",
    "magento/module-product-override-data-exporter": "^101.3.1",
    "magento/data-services": "^7.0.11",
    "magento/services-id": "^3.0.1",
    "magento/services-connector": "1.2.1"
   }
   ```

1. Aggiorna le dipendenze e installa l&#39;estensione:

   ```bash
   composer update
   ```

   Il comando aggiorna tutte le dipendenze.

1. Aggiorna Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cancella la cache:

   ```bash
   bin/magento cache:clean
   ```

## Rete di servizi del catalogo e API

La [Rete API](https://developer.adobe.com/graphql-mesh-gateway/gateway/overview/) consente agli sviluppatori di integrare API private o di terze parti e altre interfacce con i prodotti Adobe tramite Adobe IO.

Il primo passaggio per utilizzare la mesh API con il servizio catalogo è quello di collegare la mesh API alla tua istanza. Vedi istruzioni dettagliate in [Creare una mesh](https://developer.adobe.com/graphql-mesh-gateway/gateway/create-mesh/).

Per completare la configurazione, è necessario [Pacchetto Adobe IO CLI](https://developer.adobe.com/runtime/docs/guides/tools/cli_install/) installato.

Una volta configurata Mesh su Adobe IO, esegui il seguente comando per collegare la nuova mesh.

```bash
aio api-mesh:source:install "CommerceCatalogServiceGraph" -f variables.json
```

dove `variables.json` è un file separato che memorizza i valori comunemente utilizzati per Adobe IO.
Ad esempio, la chiave API può essere salvata all’interno del file :

```json
{
    "CATALOG_SERVICE_API_KEY":"your_api_key"
}
```

Dopo aver eseguito questo comando, il servizio catalogo deve essere in esecuzione attraverso la mesh API.

## Configurare l’esportazione del catalogo

Dopo l&#39;installazione [!DNL Catalog Service], devi configurare le [Connettore Commerce Services](../landing/saas.md) specificando le chiavi API e selezionando uno spazio dati SaaS.

Per verificare che l’esportazione del catalogo sia eseguita correttamente:

- Conferma che [lavori cron](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs.html) stanno correndo.
- Verifica la [indicizzatori](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/manage-indexers.html) stanno correndo.
- Assicurati che `Catalog Attributes Feed`, `Product Feed`, `Product Overrides Feed`e `Product Variant Feed` gli indici sono impostati su `Update by Schedule`.

## [!DNL Catalog Service] demo

Guarda questo video per saperne di più [!DNL Catalog Service] installazione e prova:

>[!VIDEO](https://video.tv.adobe.com/v/3409390?quality=12&learn=on)
