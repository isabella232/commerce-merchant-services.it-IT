---
title: "Installa [!DNL Quick Checkout] per estensione Adobe Commerce"
description: "Segui questi passaggi per installare [!DNL Quick Checkout] nel progetto Adobe Commerce."
exl-id: e1dabc9a-0ab0-4f8d-98d3-7a32abbedcb8
feature: Checkout, Services, Install
source-git-commit: b1984a26463e14b8dc9a789421e49e5ea81ad039
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---

# Installa [!DNL Quick Checkout]

Il [!DNL Quick Checkout] estensione per Adobe Commerce e [!DNL Magento Open Source] può essere installato con [!DNL Composer keys], collegati all’account Commerce [`mageid`](https://devdocs.magento.com/marketplace/sellers/profile-personal.html#field-descriptions){target="_blank"} fornite nel processo di abbonamento. Compositore utilizza queste chiavi durante l’installazione iniziale di Adobe Commerce o in situazioni in cui [!DNL Composer keys] non sono stati salvati in precedenza in `auth.json` file.

Consulta [ottenere le chiavi di autenticazione](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html){target="_blank"} per ulteriori informazioni su come ottenere [!DNL Composer keys].

Esistono due modi per installare questa estensione: [Adobe Commerce sull’infrastruttura cloud](#magento-commerce-cloud) o [on-premise](#on-premises) installazioni. Questi metodi richiedono l&#39;utilizzo dell&#39;interfaccia della riga di comando (CLI).

## Aggiorna impostazione stabilità minima

Prima di installare l’estensione, assicurati che `minimum-stability` campo nel tuo `composer.json` il file è impostato su `"stable"`:

`"minimum-stability": "stable"`

## Installare l’estensione

È possibile installare [!DNL Quick Checkout] estensione sia per Adobe Commerce sull’infrastruttura cloud che per le istanze locali.

### Adobe Commerce sull’infrastruttura cloud

Questo metodo viene utilizzato per installare [!DNL Quick Checkout] estensione per un’istanza Commerce Cloud.

1. Nella workstation locale, passa alla directory principale del progetto Cloud.

1. Aggiorna il tuo `composer.json` file:

   ```bash
   composer require magento/quick-checkout --no-update
   ```

1. Aggiorna le dipendenze e installa l’estensione:

   ```bash
   composer update
   ```

   Il `composer update` aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer update magento/quick-checkout`.

1. Eseguire il commit e inviare le modifiche.

### On-premise

Questo metodo viene utilizzato per installare [!DNL Quick Checkout] estensione per un’istanza on-premise.

1. Aggiungere il modulo Check-Out rapido a `require` sezione del `composer.json` file:

   ```bash
   composer require magento/quick-checkout --no-update
   ```

1. Aggiorna le dipendenze e installa l’estensione:

   ```bash
   composer update
   ```

   Il `composer update` aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer update magento/quick-checkout`.

1. Aggiorna Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cancella la cache:

   ```bash
   bin/magento cache:clean
   ```

1. Conferma modifiche.
1. Aggiorna l’istanza on-premise per garantire che il codice confermato sia distribuito.

## Aggiornare l’estensione

Quando viene rilasciata una nuova versione di [!DNL Quick Checkout], puoi aggiornare facilmente l’estensione.

1. Per ottenere la versione più recente del pacchetto:

   ```bash
   composer update
   ```

   Il `composer update` aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer update magento/quick-checkout`.

1. Eseguire il commit e inviare le modifiche.

## Risoluzione dei problemi

È possibile che vengano visualizzati errori durante il tentativo di installazione di [!DNL Quick Checkout] estensione.

In caso di problemi durante il [!DNL Quick Checkout] processo di installazione, vedere [Risoluzione dei problemi di Check-Out rapido](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/quick-checkout-issues.html) nel Centro assistenza Adobe Commerce.

## Prerequisiti

Consulta la [prerequisiti](../quick-checkout/prerequisites.md) per ulteriori informazioni.
