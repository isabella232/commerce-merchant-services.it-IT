---
title: Installazione
description: '"Installa il [!DNL Store Fulfillment solution] per una vetrina Adobe Commerce che utilizza Composer for PHP."'
role: User, Admin
level: Intermediate
exl-id: 6613268a-7d22-4c54-af89-834921b7f262
source-git-commit: 66c4ca972004c43fa55795006b1511820ca9b514
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Installazione

Completare l&#39;installazione iniziale del [!DNL Store Fulfillment for Adobe Commerce by Walmart Commerce Technologies] estensione in un ambiente non di produzione con gestione delle code in esecuzione e memorizzazione in cache configurati per consentire la gestione delle eccezioni. Assicurati che l&#39;ambiente di sviluppo includa strumenti di sviluppo per garantire le best practice per il funzionamento e la manutenzione dell&#39;istanza Adobe Commerce.

## Prerequisiti

Consulta la sezione [requisiti](solution-requirements.md) per la soluzione Store Fulfillment e raccogliere le informazioni richieste prima di installare la [!DNL Store Fulfillment] estensione per Adobe Commerce.

Se hai installato una versione pre-release o beta dell’estensione Store Fulfillment for Adobe Commerce, utilizza il seguente comando per rimuoverlo prima di installare la versione corrente.

```terminal
rm -rf composer.lock vendor/walmart &&
composer require walmart/magento-bopis-metapackage:1.0.0
```

## Requisiti di installazione

- **Accesso all&#39;archivio Store Fulfillment dell&#39;archivio software Walmart Commerce Technologies (file .zip)**- Durante il processo di onboarding e abilitazione, collabora con il tuo Account Manager per accedere al file di installazione per l&#39;estensione Store Fulfillment.

- **Informazioni sull’account Adobe Commerce**-Installazione del [!DNL Store Fulfillment] una soluzione richiede [Account Commerce](https://docs.magento.com/user-guide/magento/magento-account.html){target=&quot;_blank&quot;}. È necessario un ID account e le credenziali con accesso Proprietario o Amministratore al [!DNL Adobe Commerce] progetto.

- Per [!DNL Adobe Commerce] nei progetti di infrastruttura cloud, i programmi di installazione del software devono disporre dell’accesso amministratore al progetto Cloud. Vedi [Gestire l’accesso utente](https://devdocs.magento.com/cloud/project/user-admin.html).

- **Esperienza con Compositore e[!DNL Commerce CLI]**—Vedi [Installazione generale CLI](https://devdocs.magento.com/extensions/install/){target=&quot;_blank&quot;} per informazioni sull&#39;utilizzo di questi strumenti per installare e gestire le estensioni in [!DNL Adobe Commerce] piattaforma.

- **Esperienza con l’installazione di estensioni di terze parti in Adobe Commerce**- Per riferimento, consulta la documentazione di Adobe Commerce.

   - [Installare un’estensione per un’istanza di Adobe Commerce su un’infrastruttura cloud](https://devdocs.magento.com/cloud/howtos/install-components.html#install-an-extension).

   - [Installa un&#39;estensione per un&#39;istanza on-premise di Adobe Commerce](https://devdocs.magento.com/extensions/install/).

### Passaggio 1: Scarica il pacchetto di estensione

Segui le istruzioni fornite dai rappresentanti del tuo account per scaricare il file di archivio contenente i pacchetti Composer per l&#39;installazione dell&#39;estensione Store Fulfillment Services .

### Passaggio 2: Estrarre gli artefatti dell&#39;estensione nell&#39;applicazione

Estrai il file di archivio che contiene il bundle di integrazione per installare l&#39;estensione Store Fulfillment Services.

1. Crea una directory di destinazione per i file estratti.

   - Dalla riga di comando, passare alla directory principale doc del server Web.

   - Crea un `artifacts` directory.

1. Estrai il file di archivio nella nuova directory.

1. Verifica che i file estratti siano rivisti l’elenco dei file.

   ```
   ../var/www/html/artifacts]$ ls -a
   .
   ..
   bopis-sdk.zip
   module-magento-bopis-alternate-pickup-contact-admin-ui.zip
   module-magento-bopis-alternate-pickup-contact-api.zip
   ```

### Passaggio 3: Configurare l’app tramite Composer

Utilizza Compositore per configurare la directory di origine per l&#39;installazione e installare l&#39;estensione Store Fulfillment Services .

1. Configura l&#39;archivio sorgente per l&#39;installazione del Composer.

   ```bash
   composer config repositories.artifacts artifact artifacts/
   ```

1. Aggiungi l’estensione Store Fulfillment Services a `composer.json`.

   ```bash
   composer require walmart/magento-bopis-metapackage:1.0.0
   ```

>[!NOTE]
>
>Per prestazioni migliori sulle istanze on-premise di Adobe Commerce, puoi [aggiorna la configurazione del caricamento automatico](https://experienceleague.adobe.com/docs/commerce-operations/performance-best-practices/deployment-flow.html#update-the-autoloader): `composer dump-autoload --optimize`

### Passaggio 4: Aggiornare lo schema e i dati del database

Completa l’installazione utilizzando il `bin/magento setup:upgrade` aggiornare lo schema del database e i dati con le modifiche per supportare la soluzione Store Fulfillment.

>Nota:
>Per Adobe Commerce sui progetti di infrastruttura cloud, non è necessario registrare l’estensione. Esegui il commit delle modifiche del codice dal passaggio precedente e inviale al ramo dell&#39;ambiente. I comandi per aggiornare lo schema e i dati del database vengono eseguiti automaticamente durante il processo di creazione e distribuzione del cloud.

### Passaggio 5: Completare l&#39;installazione

1. Registra l&#39;estensione con Adobe Commerce utilizzando `setup:upgrade` Comando CLI del Magento.

   ```terminal
   bin/magento setup:upgrade
   ```

1. Se richiesto, ricompilare il [!DNL Commerce] progetto.

   ```bash
   bin/magento setup:di:compile
   ```

1. Pulisci la cache.

   ```bash
   bin/magento cache:clean
   ```

1. Disattiva la modalità di manutenzione.

   ```bash
   bin/magento maintenance:disable
   ```

### Passaggio 6: Verificare l’installazione

Dal server Adobe Commerce, verifica che i moduli per l’estensione Store Fulfillment Services siano installati e abilitati.

1. Accedi al server.

   Per installazioni su Adobe Commerce su infrastruttura cloud, [utilizzare SSH per accedere all’ambiente remoto](https://devdocs.magento.com/cloud/env/environments-ssh.html#ssh).

1. Verifica che i moduli Store Fulfillment Services siano abilitati.

   ```bash
   bin/magento module:status  --enabled | grep Walmart
   ```

   L’output deve includere i seguenti moduli:

   ```
   Walmart_BopisBase
   Walmart_BopisAlternatePickupContact
   Walmart_BopisAlternatePickupContactFrontend
   Walmart_BopisApiConnector
   Walmart_BopisAlternatePickupContactAdminUi
   Walmart_BopisCheckoutPickInStoreApi
   Walmart_BopisInventorySourceAdminUi
   Walmart_BopisCheckoutPickInStore
   Walmart_BopisInventoryCatalogApi
   Walmart_BopisPreferredLocationApi
   Walmart_BopisHomeDeliveryApi
   Walmart_BopisHomeDelivery
   Walmart_BopisPreferredLocation
   Walmart_BopisInventoryCatalog
   Walmart_BopisPreferredLocationFrontend
   Walmart_BopisCheckoutPickInStoreAdminUi
   Walmart_BopisInventorySourceApi
   Walmart_BopisInventorySourceFaasSync
   Walmart_BopisInventorySourceReservation
   Walmart_BopisLocationCheckInApi
   Walmart_BopisLogging
   Walmart_BopisStoreAssociateApi
   Walmart_BopisLocationCheckInFrontend
   Walmart_BopisStoreAssociate
   Walmart_BopisOperationQueue
   Walmart_BopisOperationQueueAdminUi
   Walmart_BopisOperationQueueApi
   Walmart_BopisOrderFaasSync
   Walmart_BopisOrderUpdateApi
   Walmart_BopisLocationCheckIn
   Walmart_BopisInventoryCatalogAdminUi
   Walmart_BopisPreferredLocationAdminUi
   Walmart_BopisDeliverySelection
   Walmart_BopisCheckoutPickInStoreFrontend
   Walmart_BopisLocationCheckInAdminUi
   Walmart_BopisStoreAssociateAdminUi
   Walmart_BopisOrderUpdate
   Walmart_BopisStoreAssociateTfa
   Walmart_BopisStoreAssociateTfaApi
   ```

### Passaggi aggiuntivi

Se necessario, utilizza le `[setup:static-content: deploy](https://devdocs.magento.com/guides/v2.4/reference/cli/magento-commerce.html#setupstatic-contentdeploy)` Comando CLI per distribuire i file di visualizzazione statici nell&#39;ambiente di produzione.

```terminal
php bin/magento setup:static-content:deploy -f
```

La `-f` se utilizzi un tema vuoto, è necessaria l’opzione .

>[!NOTE]
>
>Per ulteriori informazioni, consulta [Best practice per l’implementazione dei contenuti statici in Adobe Commerce](https://support.magento.com/hc/en-us/articles/360031624091) nel Centro assistenza Adobe Commerce.
