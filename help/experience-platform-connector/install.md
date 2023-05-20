---
title: Installare e configurare il connettore Adobe Experience Platform da Adobe Commerce
description: Scopri come installare, configurare, aggiornare e disinstallare il connettore Adobe Experience Platform da Adobe Commerce.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
source-git-commit: 898d49cbeb4711862a47693a0d608b74730dc845
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Installare e configurare il connettore Experience Platform

Prima di installare l’estensione, [esaminare i prerequisiti](overview.md#prereqs).

## Installare l’estensione

L&#39;estensione del connettore di Experience Platform è disponibile dal [Adobe Marketplace](https://marketplace.magento.com/magento-experience-platform-connector.html). Quando installi questa estensione dalla riga di comando del server, questa si connette all’installazione di Adobe Commerce come [servizio](../landing/saas.md). Al termine del processo, **Connettore Experience Platform** e **Connettore Commerce Services** vengono visualizzati sul **Sistema** menu in **Servizi** in Commerce _Amministratore_.

>[!NOTE]
>
>![B2B per Adobe Commerce](../assets/b2b.svg) Per i commercianti B2B, è necessario installare un’estensione separata. Questa estensione aggiunge il supporto per eventi specifici B2B. [Ulteriori informazioni](#install-the-b2b-extension).


1. Per scaricare `experience-platform-connector` , eseguire quanto segue dalla riga di comando:

   ```bash
   composer require magento/experience-platform-connector
   ```

   Questo metapacchetto contiene i moduli e le estensioni seguenti:

   * `module-experience-connector-admin` : aggiorna l’interfaccia utente di amministrazione in modo da poter selezionare l’ID dello stream di dati per una specifica istanza di Adobe Commerce
   * `module-experience-connector` - Imposta il `Organization ID` e `datastreamId` nell’SDK degli eventi di Storefront
   * `data-services` : fornisce il contesto degli attributi per gli eventi storefront. Ad esempio, quando si verifica un evento di pagamento, vengono incluse informazioni sul numero di elementi presenti nel carrello e i dati degli attributi del prodotto relativi a tali elementi.
   * `services-id` : collega l’istanza Adobe Commerce a [SaaS Adobe Commerce](../landing/saas.md) utilizzando le chiavi sandbox e API di produzione e in Adobe Experience Platform per recuperare l’ID organizzazione IMS

1. (Facoltativo) Da includere [!DNL Live Search] , che include eventi di ricerca, installa il [[!DNL Live Search]](../live-search/install.md) estensione.

### Installare l’estensione B2B

Per gli esercenti B2B, installa la seguente estensione per includere [elenco richieste di acquisto](events.md#b2b-events) dati evento.

Scarica il file `magento/experience-platform-connector-b2b` eseguendo quanto segue dalla riga di comando:

```bash
composer require magento/experience-platform-connector-b2b
```

## Aggiornare il connettore di Experience Platform {#update}

Per aggiornare il connettore di Experience Platform, eseguire quanto segue dalla riga di comando:

```bash
composer update magento/experience-platform-connector --with-dependencies
```

oppure, per gli esercenti B2B:

```bash
composer update magento/experience-platform-connector-b2b --with-dependencies
```

Per aggiornare a una versione principale, ad esempio da 1.0.0 a 2.0.0, modifica la directory principale del progetto [!DNL Composer] `.json` file come segue:

1. Apri la directory principale `composer.json` file e ricerca `magento/platform-connector`.

1. In `require` , aggiorna il numero di versione come segue:

   ```json
   "require": {
      ...
      "magento/experience-platform-connector": "^2.0",
      ...
    }
   ```

1. **Salva** `composer.json`. Quindi, esegui quanto segue dalla riga di comando:

   ```bash
   composer update magento/experience-platform-connector –-with-dependencies
   ```

   oppure, per gli esercenti B2B:

   ```bash
   composer update magento/experience-platform-connector-b2b --with-dependencies
   ```

## Disinstallare il connettore di Experience Platform {#uninstall}

Per disinstallare il connettore di Experience Platform, fare riferimento a [disinstalla moduli](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/tutorials/uninstall-modules.html).
