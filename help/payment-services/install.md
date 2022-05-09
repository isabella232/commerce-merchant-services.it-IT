---
title: Installa [!DNL Payment Services]
description: Installa l'estensione Payments Services.
exl-id: babaa91a-9376-4acb-b934-a89f9df52016
source-git-commit: 9596815e31402f23b399b223f3221074331c1773
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Installa [!DNL Payment Services]

Installazione di [!DNL Payment Services] estensione per [!DNL Adobe Commerce] e [!DNL Magento Open Source] è un passaggio preliminare per l’utilizzo di [!DNL Payment Services].

![[!DNL Payment Services] vista amministratore dell&#39;estensione](assets/admin-view.png)

La [!DNL Payment Services] estensione per [!DNL Adobe Commerce] e [!DNL Magento Open Source] può essere installato con le chiavi del Compositore , collegate all’ID Magento ([mageid](https://devdocs.magento.com/marketplace/sellers/profile-personal.html#field-descriptions) fornito nel processo di registrazione. Il Compositore utilizza queste chiavi durante l&#39;installazione iniziale di [!DNL Adobe Commerce]o in situazioni in cui le chiavi del Compositore non sono state precedentemente salvate nel `auth.json` file.

Vedi [Ottieni le chiavi di autenticazione](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) per ulteriori informazioni su come ottenere le chiavi Composer.

Esistono due modi per installare questa estensione: [[!DNL Adobe Commerce] sull&#39;infrastruttura cloud](install.md#adobe-commerce-on-cloud-infrastructure) o [Presso i locali](install.md#on-premises) installazioni. Questi metodi richiedono l’utilizzo dell’interfaccia CLI (Command Line Interface).

## Aggiorna impostazione di stabilità minima

Prima di installare l&#39;estensione, devi modificare la `minimum-stability` obbligo di `RC` (candidato per il rilascio) nel `composer.json` file. È possibile utilizzare un IDE o un editor di testo preferito (come Visual Studio Code o Sublime Text).

Nel tuo `composer.json` file, modifica `"minimum-stability": "stable"` a `"minimum-stability": "RC"`.

## Installare l’estensione

È possibile installare [!DNL Payment Services] estensione per entrambi [!DNL Adobe Commerce] su infrastrutture cloud e istanze locali.

### [!DNL Adobe Commerce] sull&#39;infrastruttura cloud

Questo metodo viene utilizzato per installare [!DNL Payment Services] estensione per un&#39;istanza Commerce Cloud.

1. Aggiorna il tuo `composer.json` file:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Aggiorna le dipendenze e installa l&#39;estensione:

   ```bash
   composer update
   ```

   La `composer update` Il comando aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer require magento/payment-services`.

1. Conferma e invia le modifiche.

### Presso i locali

Questo metodo viene utilizzato per installare [!DNL Payment Services] estensione per un&#39;istanza on-premise.

1. Per ottenere l&#39;estensione, esegui i seguenti comandi:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Aggiorna le dipendenze e installa l&#39;estensione:

   ```bash
   composer update
   ```

   La `composer update` Il comando aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer require magento/payment-services`.

1. Aggiornamento [!DNL Adobe Commerce]:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cancella la cache:

   ```bash
   bin/magento cache:clean
   ```

1. Conferma le modifiche.
1. Per assicurarti che il codice impegnato sia distribuito, aggiorna la tua istanza on-premise .

## Aggiornare l’estensione

Quando una nuova versione di [!DNL Payment Services] viene rilasciata e puoi facilmente aggiornare l’estensione.

1. Per ottenere la versione più recente del pacchetto:

   ```bash
   composer update
   ```

   La `composer update` Il comando aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer update magento/payment-services`.

1. Conferma e invia le modifiche.

## Risoluzione dei problemi

Potrebbero verificarsi errori durante il tentativo di installazione del [!DNL Payment Services] estensione. Per risolvere gli errori, utilizzare i seguenti metodi di risoluzione dei problemi.

### Tasti compositore errati

Se vedi il seguente errore che indica che hai le chiavi Composer non corrette:

```terminal
Could not find a matching version of package magento/payment-services. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).
```

Verifica che le chiavi del Compositore siano collegate all’ID Magento utilizzato durante [!DNL Payment Services] registrazione.

Per vedere quali chiavi del Compositore sono configurate:

1. Trova la posizione del `auth.json` file:

   ```bash
   composer config --global home
   ```

1. Visualizza la `auth.json` file:

   ```bash
   cat /path/to/auth.json
   ```

1. Vedi [quali chiavi sono associate al tuo ID Magento](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html).

### Memoria insufficiente per PHP

Se vedi il seguente errore che indica che non hai abbastanza memoria per PHP:

```terminal
Fatal error: Allowed memory size of 2146435072 bytes exhausted (tried to allocate 4096 bytes) in phar:///usr/local/bin/composer/src/Composer/DependencyResolver/RuleWatchGraph.php on line 52
```

[Aumentare il limite di memoria](https://devdocs.magento.com/cloud/project/magento-app-php-ini.html#increase-php-memory-limit) per PHP sul tuo ambiente in `php.ini`.

In alternativa, è possibile specificare il limite di memoria utilizzando questo comando: `php -d memory_limit=-1 [path to composer]/composer require magento/payment-services`.

Ad esempio:

```bash
php -d memory_limit=-1 vendor/bin/composer require magento/payment-services
```
