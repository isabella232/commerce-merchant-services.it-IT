---
title: Installa il [!DNL Express Checkout] per estensione Adobe Commerce
description: Segui questi passaggi per installare [!DNL Upgrade Compatibility Tool] per il progetto Adobe Commerce.
exl-id: e1dabc9a-0ab0-4f8d-98d3-7a32abbedcb8
source-git-commit: 163dd5260908b4ea3a8bfbcfdb834531d1603734
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Installa il [!DNL Express Checkout]

>[!IMPORTANT]
>
> Questa funzione è disponibile solo per gli utenti del programma Early Adopter (EAP) e non è ancora accessibile per tutti i clienti. Attualmente limitato ai clienti statunitensi. Per assistenza e domande, contatta il supporto Adobe Commerce.

La [!DNL Express Checkout] per Adobe Commerce offre un’esperienza di pagamento senza soluzione di continuità progettata per convertire gli acquirenti unici in titolari di account fedeli.

La [!DNL Express Checkout] l&#39;estensione per Adobe Commerce e Magenti Open Source può essere installata con le chiavi del Composer, che sono collegate al [ID Magento (mageid)](https://devdocs.magento.com/marketplace/sellers/profile-personal.html#field-descriptions){target=&quot;_blank&quot;} fornito nel processo di registrazione. Il Compositore utilizza queste chiavi durante l&#39;installazione iniziale di Adobe Commerce o in situazioni in cui le chiavi del Compositore non sono state precedentemente salvate nel `auth.json` file.

Vedi [ottieni le chiavi di autenticazione](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html){target=&quot;_blank&quot;} per ulteriori informazioni su come ottenere le chiavi del Compositore.

Esistono due modi per installare questa estensione: [Adobe Commerce su infrastruttura cloud](#magento-commerce-cloud) o [locale](#on-premises) installazioni. Questi metodi richiedono l’utilizzo dell’interfaccia CLI (Command Line Interface).

## Aggiorna impostazione di stabilità minima

Prima di installare l&#39;estensione, puoi modificare la variabile `minimum-stability` obbligo di `RC` (candidato per il rilascio) nel `composer.json` se desideri provare la versione di release candidate. È possibile utilizzare un IDE o un editor di testo preferito (come Visual Studio Code o Sublime Text).

Nel tuo `composer.json` file, modifica `"minimum-stability": "stable"` a `"minimum-stability": "RC"`.

## Installare l’estensione

È possibile installare [!DNL Express Checkout] estensione sia per Adobe Commerce sull’infrastruttura cloud che per le istanze locali.

### Adobe Commerce su infrastruttura cloud

Questo metodo viene utilizzato per installare [!DNL Express Checkout] estensione per un&#39;istanza Commerce Cloud.

1. Nella workstation locale, passa alla directory principale del progetto Cloud.

1. Aggiorna il tuo `composer.json` file:

   ```bash
   composer require magento/express-checkout --no-update
   ```

1. Aggiorna le dipendenze e installa l&#39;estensione:

   ```bash
   composer update
   ```

   La `composer update` Il comando aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer update magento/express-checkout`.

1. Conferma e invia le modifiche.

### Presso i locali

Questo metodo viene utilizzato per installare [!DNL Express Checkout] estensione per un&#39;istanza on-premise.

1. Aggiungi il modulo Express Checkout al `require` della sezione `composer.json` file:

   ```bash
   composer require magento/express-checkout --no-update
   ```

1. Aggiorna le dipendenze e installa l&#39;estensione:

   ```bash
   composer update
   ```

   La `composer update` Il comando aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer update magento/express-checkout`.

1. Aggiorna Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cancella la cache:

   ```bash
   bin/magento cache:clean
   ```

1. Conferma le modifiche.
1. Aggiorna l’istanza locale per assicurarti che il codice impegnato sia distribuito.

## Aggiornare l’estensione

Quando rilasciamo una nuova versione di [!DNL Express Checkout], puoi facilmente aggiornare l’estensione.

1. Per ottenere la versione più recente del pacchetto:

   ```bash
   composer update
   ```

   La `composer update` Il comando aggiorna tutte le dipendenze. Se non si desidera aggiornare tutte le dipendenze contemporaneamente, utilizzare questo comando: `composer update magento/express-checkout`.

1. Conferma e invia le modifiche.

## Risoluzione dei problemi

Potrebbero verificarsi errori durante il tentativo di installazione del [!DNL Express Checkout] estensione.

Fai riferimento a [risoluzione](../express-checkout/troubleshooting.md) per ulteriori informazioni in caso di problemi durante l&#39;installazione del [!DNL Express Checkout].

## Prerequisiti

Consulta la sezione [prerequisiti](../express-checkout/prerequisites.md) per ulteriori informazioni.
