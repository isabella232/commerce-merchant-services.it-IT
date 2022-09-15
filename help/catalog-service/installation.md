---
title: Onboarding e installazione
description: Scopri come installare [!DNL Catalog Service]
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: 595d7644374b066b7608748cf09df1c41bf0eaee
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Onboarding e installazione

I partner e i clienti sono invitati a iniziare a utilizzare [!DNL Catalog Service] per la versione beta di Adobe Commerce rilasciata il 9 agosto 2022. Per partecipare devi leggere e accettare il nostro [Termini del programma Adobe Commerce Beta](https://experiencecloudpanel.adobe.com/h/s/6eGskQlHvLSHztsNmKCWMy).

Una volta firmato l&#39;accordo, contatta il nostro team sul [#storefront-services](https://magentocommeng.slack.com/archives/C03HVPG8RS4) canale di Slack pubblico. Forniremo tutte le informazioni e i passaggi successivi necessari per lavorare con [!DNL Catalog Service] Versione beta.

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

La [!DNL Catalog Service] è installato con le chiavi del Compositore , collegate all&#39;ID Magento ([mageid](https://developer.adobe.com/commerce/marketplace/guides/sellers/profile-personal/#field-descriptions) fornito nel processo di registrazione. Il Compositore utilizza queste chiavi durante l&#39;installazione iniziale di [!DNL Adobe Commerce]o in situazioni in cui le chiavi del Compositore non sono state precedentemente salvate nel `auth.json` file.

Vedi [Ottieni le chiavi di autenticazione](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) per ulteriori informazioni su come ottenere le chiavi Composer.

### Adobe Commerce su infrastruttura cloud

Utilizzare questo metodo per installare [!DNL Catalog Service] estensione per un&#39;istanza Commerce Cloud.

1. Apri `<Commerce_root>/composer.json` in un editor di testo e aggiorna il `require` come segue:

   ```json
   "require": {
    "magento/composer-root-update-plugin": "^2.0.2",
    "magento/magento-cloud-metapackage": ">=2.4.5 <2.4.6",
    "magento/saas-export": "^101.4.0",
    "magento/commerce-data-export": "^101.3.1",
    "magento/commerce-data-export-ee": "^101.3.1",
    "magento/services-id": "^3.0.1",
    "magento/services-connector": "1.2.1"
    }
   ```

   <!-- What if the customer already has other services installed, and some of these lines are already present? Do they need to delete the duplications? What if the version numbers are different? -->

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
     "magento/magento-cloud-metapackage": ">=2.4.3 <2.4.4",
     "magento/composer-root-update-plugin": "~1.1",
     "magento/saas-export": "^101.3.1",
     "magento/commerce-data-export": "^101.2.4",    
     "magento/commerce-data-export-ee": "^101.2.4",
     "magento/services-id": "^3.0.0",
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

## Configurare l’esportazione del catalogo

Dopo l&#39;installazione [!DNL Catalog Service], devi configurare le [Connettore Commerce Services](../landing/saas.md) specificando le chiavi API e selezionando uno spazio dati SaaS.

Per verificare che l’esportazione del catalogo sia eseguita correttamente:

- Conferma che [lavori cron](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs.html) stanno correndo.
- Verifica la [indicizzatori](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/manage-indexers.html) stanno correndo.
- Assicurati che `Catalog Attributes Feed`, `Product Feed`, `Product Overrides Feed`e `Product Variant Feed` gli indici sono impostati su `Update by Schedule`.
