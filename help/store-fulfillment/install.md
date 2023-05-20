---
title: Installazione
description: "Installare [!DNL Store Fulfillment solution] per una vetrina Adobe Commerce utilizzando Composer for PHP."
role: User, Admin
level: Intermediate
exl-id: 6613268a-7d22-4c54-af89-834921b7f262
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---


# Installazione

Completare l&#39;installazione iniziale del [!DNL Store Fulfillment for Adobe Commerce by Walmart Commerce Technologies] estensione in un ambiente non di produzione con gestione code in esecuzione e caching configurati per consentire la gestione delle eccezioni. Assicurati che il tuo ambiente di sviluppo includa strumenti di sviluppo per garantire best practice per il funzionamento e la manutenzione dell’istanza di Adobe Commerce.

## Prerequisiti

Rivedi [requisiti](solution-requirements.md) per la soluzione Store Fulfillment e raccogliere le informazioni richieste prima di installare [!DNL Store Fulfillment] per Adobe Commerce.

Se hai installato una versione pre-release o beta dell’estensione Store Fulfillment per Adobe Commerce, rimuovilo con il seguente comando prima di installare la versione corrente.

```terminal
rm -rf composer.lock vendor/walmart &&
composer require walmart/magento-bopis-metapackage:1.0.0
```

## Requisiti di installazione

- **Accesso all&#39;archivio software Store Fulfillment di Walmart Commerce Technologies (file .zip)**- Durante il processo di onboarding e abilitazione, rivolgiti al tuo Account Manager per ottenere l’accesso al file di installazione per l’estensione Store Fulfillment.

- **Informazioni sull’account Adobe Commerce**-Installazione di [!DNL Store Fulfillment] la soluzione richiede [[!DNL Commerce] account](https://docs.magento.com/user-guide/magento/magento-account.html){target="_blank"}. È necessario disporre di un ID account e delle credenziali con accesso Proprietario o Amministratore al [!DNL Adobe Commerce] progetto.

- Per [!DNL Adobe Commerce] nei progetti di infrastruttura cloud, i programmi di installazione software devono disporre dell’accesso amministratore al progetto Cloud. Consulta [Gestire l’accesso degli utenti](https://devdocs.magento.com/cloud/project/user-admin.html).

- **Esperienza utilizzando Compositore e[!DNL Commerce CLI]**- Consulta [Installazione generale di CLI](https://devdocs.magento.com/extensions/install/){target="_blank"} per informazioni sull&#39;utilizzo di questi strumenti per installare e gestire le estensioni sul [!DNL Adobe Commerce] piattaforma.

- **Installazione di estensioni di terze parti su Adobe Commerce**- Per maggiori informazioni, consultate la documentazione di Adobe Commerce.

   - [Installare un’estensione per un’istanza di Adobe Commerce sull’infrastruttura cloud](https://devdocs.magento.com/cloud/howtos/install-components.html#install-an-extension).

   - [Installare un’estensione per un’istanza on-premise di Adobe Commerce](https://devdocs.magento.com/extensions/install/).

### Passaggio 1: scaricare il bundle dell’estensione

Segui le istruzioni fornite dai rappresentanti del tuo account per scaricare il file di archivio che contiene i pacchetti Composer per installare l’estensione Store Fulfillment Services.

### Passaggio 2: estrarre gli artefatti dell’estensione nell’applicazione

Estrai il file di archivio che contiene il bundle di integrazione per installare l’estensione Store Fulfillment Services.

1. Creare una directory di destinazione per i file estratti.

   - Dalla riga di comando, vai alla directory principale dei documenti del server web.

   - Creare un `artifacts` directory.

1. Estrarre il file di archivio nella nuova directory.

1. Verificare che i file siano stati estratti correttamente esaminando l&#39;elenco dei file.

   ```
   ../var/www/html/artifacts]$ ls -a
   .
   ..
   bopis-sdk.zip
   module-magento-bopis-alternate-pickup-contact-admin-ui.zip
   module-magento-bopis-alternate-pickup-contact-api.zip
   ```

### Passaggio 3: configurare l’app tramite Compositore

Utilizzare Composer per configurare la directory di origine per l&#39;installazione e installare l&#39;estensione Store Fulfillment Services.

1. Configurare l&#39;archivio di origine per l&#39;installazione del Compositore.

   ```bash
   composer config repositories.artifacts artifact artifacts/
   ```

1. Aggiungi l&#39;estensione Store Fulfillment Services a `composer.json`.

   ```bash
   composer require walmart/magento-bopis-metapackage:1.0.0
   ```

>[!NOTE]
>
>Per migliorare le prestazioni sulle istanze locali di Adobe Commerce, puoi [aggiornare la configurazione del caricamento automatico](https://experienceleague.adobe.com/docs/commerce-operations/performance-best-practices/deployment-flow.html#update-the-autoloader): `composer dump-autoload --optimize`

### Passaggio 4: aggiornare lo schema e i dati del database

Completare l&#39;installazione utilizzando `bin/magento setup:upgrade` per aggiornare lo schema e i dati del database con le modifiche apportate per supportare la soluzione Store Fulfillment.

>[!NOTE]
>
>Per i progetti Adobe Commerce su infrastrutture cloud, non è necessario registrare l’estensione. Esegui il commit delle modifiche al codice rispetto al passaggio precedente e inviale al ramo dell’ambiente. I comandi per aggiornare lo schema e i dati del database vengono eseguiti automaticamente durante il processo di creazione e distribuzione del cloud.

### Passaggio 5: completare l&#39;installazione

1. Registrare l&#39;estensione con Adobe Commerce utilizzando `setup:upgrade` Comando Magento CLI.

   ```terminal
   bin/magento setup:upgrade
   ```

1. Se richiesto, ricompila il [!DNL Commerce] progetto.

   ```bash
   bin/magento setup:di:compile
   ```

1. Pulire la cache.

   ```bash
   bin/magento cache:clean
   ```

1. Disattiva la modalità di manutenzione.

   ```bash
   bin/magento maintenance:disable
   ```

### Passaggio 6: verificare l’installazione

Dal server Adobe Commerce, verifica che i moduli per l’estensione Store Fulfillment Services siano installati e abilitati.

1. Accedi al server.

   Per le installazioni su Adobe Commerce su infrastrutture cloud, [utilizzare SSH per accedere all&#39;ambiente remoto](https://devdocs.magento.com/cloud/env/environments-ssh.html#ssh).

1. Verificare che i moduli Servizi di evasione del punto vendita siano abilitati.

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

Se necessario, utilizza [configurazione:static-content:distribuire](https://experienceleague.adobe.com/docs/commerce-operations/reference/commerce-on-premises.html){target="_blank"} Comando CLI per distribuire i file di visualizzazione statica nell&#39;ambiente di produzione.

```terminal
php bin/magento setup:static-content:deploy -f
```

Il `-f` L’opzione è obbligatoria se utilizzi un tema vuoto.

>[!NOTE]
>
>Per ulteriori informazioni, vedere [Best practice per l’implementazione di contenuti statici in Adobe Commerce](https://experienceleague.adobe.com/docs/commerce-operations/implementation-playbook/best-practices/development/static-content-deployment.html) nell’Aiuto di Adobe Commerce.

