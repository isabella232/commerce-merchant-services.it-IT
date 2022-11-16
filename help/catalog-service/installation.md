---
title: Onboarding e installazione
description: Scopri come installare [!DNL Catalog Service]
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: c740e75c9fe12b062683fa957d0c6623d8180e4f
workflow-type: tm+mt
source-wordcount: '432'
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
   "require":{
   "magento/composer-root-update-plugin":"^2.0.2",
   "magento/magento-cloud-metapackage":">=2.4.5 <2.4.6",
   "magento/catalog-service": "^1.0.0"
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
   "magento/composer-root-update-plugin":"^2.0.2",
   "magento/catalog-service": "^1.0.0"
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
aio api-mesh:source:install "CommerceCatalogServiceGraph"
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
