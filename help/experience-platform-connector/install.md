---
title: Installare e configurare il connettore Adobe Experience Platform da Adobe Commerce
description: Scopri come installare, configurare, aggiornare e disinstallare Adobe Experience Platform Connector da Adobe Commerce.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
source-git-commit: 334ee967ec2379a87acfc5fb427d7ada6fa25ee7
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# Installare e configurare il connettore Experience Platform

Prima di installare l&#39;estensione, [esaminare i prerequisiti](overview.md#prereqs).

## Installare l’estensione

1. Installa il metapackage del connettore di Experience Platform.

   ```bash
   composer require magento/experience-platform-connector
   ```

   Questo metapackage contiene i seguenti moduli ed estensioni:

   * `module-platform-connector-admin` - Aggiorna l’interfaccia utente di amministrazione in modo da poter selezionare l’ID di Datastream per una specifica istanza di Adobe Commerce
   * `module-platform-connector` - Imposta il `ImsOrgId` e `datastreamId` in Adobe Commerce Storefront Event SDK
   * `data-services` - Fornisce il contesto dell&#39;attributo per gli eventi di vetrina. Ad esempio, quando si verifica un evento di pagamento, vengono incluse informazioni sul numero di elementi presenti nel carrello e sui dati degli attributi del prodotto per tali elementi.
   * `services-id` - Collega l’istanza Adobe Commerce a [SaaS per Adobe Commerce](../landing/saas.md) utilizzo di sandbox e chiavi API di produzione e di Adobe Experience Platform per recuperare l’ID organizzazione IMS

1. (Facoltativo) Per includere [!DNL Live Search] i dati, che comprendono eventi di ricerca, installano [[!DNL Live Search]](../live-search/install.md) estensione.

## Aggiornare il connettore di Experience Platform {#update}

Per aggiornare il connettore di Experience Platform, esegui quanto segue dalla riga di comando:

```bash
composer update magento/experience-platform-connector --with-dependencies
```

Per eseguire l’aggiornamento a una versione principale, ad esempio da 1.0.0 a 2.0.0, modifica la directory principale del progetto [!DNL Composer] `.json` file come segue:

1. Apri la radice `composer.json` file e cerca `magento/platform-connector`.

1. In `require` aggiorna il numero di versione come segue:

   ```json
   "require": {
      ...
      "magento/experience-platform-connector": "^2.0",
      ...
    }
   ```

1. **Salva** `composer.json`. Esegui quindi quanto segue dalla riga di comando:

   ```bash
   composer update magento/experience-platform-connector –-with-dependencies
   ```

## Disinstallare il connettore Experience Platform {#uninstall}

Per disinstallare il connettore di Experience Platform, fai riferimento a [disinstallare i moduli](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-uninstall-mods.html).
