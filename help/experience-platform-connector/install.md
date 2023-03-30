---
title: Installare e configurare il connettore Adobe Experience Platform da Adobe Commerce
description: Scopri come installare, configurare, aggiornare e disinstallare Adobe Experience Platform Connector da Adobe Commerce.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
source-git-commit: 76bc0650f32e99f568c061e67290de6c380f46a4
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# Installare e configurare il connettore Experience Platform

Prima di installare l&#39;estensione, [esaminare i prerequisiti](overview.md#prereqs).

## Installare l’estensione

L’estensione del connettore di Experience Platform viene installata dalla riga di comando del server e si connette all’installazione di Adobe Commerce come [servizio](../landing/saas.md). Al termine del processo, **Connettore Experience Platform** appare sul **Sistema** menu sotto **Servizi** nel Commercio _Amministratore_.

Il connettore di Experience Platform viene installato come estensione da [Adobe Marketplace](https://marketplace.magento.com/magento-experience-platform-connector.html).

![B2B per Adobe Commerce](../assets/b2b.svg) Per i commercianti B2B, è necessaria un’estensione separata da installare. Questa estensione aggiunge il supporto di eventi specifici B2B. [Ulteriori informazioni](#install-the-b2b-extension).

1. Per scaricare i `experience-platform-connector` esegui quanto segue dalla riga di comando:

   ```bash
   composer require magento/experience-platform-connector
   ```

   Questo metapackage contiene i seguenti moduli ed estensioni:

   * `module-experience-connector-admin` - Aggiorna l’interfaccia utente di amministrazione in modo da poter selezionare l’ID di Datastream per una specifica istanza di Adobe Commerce
   * `module-experience-connector` - Imposta il `Organization ID` e `datastreamId` nell’SDK per storefront Events
   * `data-services` - Fornisce il contesto dell&#39;attributo per gli eventi di vetrina. Ad esempio, quando si verifica un evento di pagamento, vengono incluse informazioni sul numero di elementi presenti nel carrello e sui dati degli attributi del prodotto per tali elementi.
   * `services-id` - Collega l’istanza Adobe Commerce a [SaaS per Adobe Commerce](../landing/saas.md) utilizzo di sandbox e chiavi API di produzione e di Adobe Experience Platform per recuperare l’ID organizzazione IMS

1. (Facoltativo) Per includere [!DNL Live Search] i dati, che comprendono eventi di ricerca, installano [[!DNL Live Search]](../live-search/install.md) estensione.

### Installare l’estensione B2B

Per i commercianti B2B, installa la seguente estensione per includere [elenco richieste](events.md#b2b-events) dati evento.

Scarica la `magento/experience-platform-connector-b2b` eseguendo quanto segue dalla riga di comando:

```bash
composer require magento/experience-platform-connector-b2b
```

## Aggiornare il connettore di Experience Platform {#update}

Per aggiornare il connettore di Experience Platform, esegui quanto segue dalla riga di comando:

```bash
composer update magento/experience-platform-connector --with-dependencies
```

o, per i commercianti B2B:

```bash
composer update magento/experience-platform-connector-b2b --with-dependencies
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

o, per i commercianti B2B:

```bash
composer update magento/experience-platform-connector-b2b --with-dependencies
```

## Disinstallare il connettore Experience Platform {#uninstall}

Per disinstallare il connettore di Experience Platform, fai riferimento a [disinstallare i moduli](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/tutorials/uninstall-modules.html).
