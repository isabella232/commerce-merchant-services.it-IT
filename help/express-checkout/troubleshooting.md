---
title: Risoluzione dei problemi relativi al [!DNL Express Checkout]
description: Risolvere gli errori e i problemi noti che possono verificarsi durante l'utilizzo del [!DNL Express Checkout] per l'estensione Adobe Commerce.
exl-id: a379ff81-360d-4cb9-a123-47e8cbc0cdbd
source-git-commit: bd9541c5e4810085ab85206b2ecca21e66800a2f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Risolvere i problemi [!DNL Express Checkout] per Adobe Commerce

>[!IMPORTANT]
>
> Questa funzione è disponibile solo per gli utenti del programma Early Adopter (EAP) e non è ancora accessibile per tutti i clienti. Attualmente limitato ai clienti statunitensi. Per assistenza e domande, contatta il supporto Adobe Commerce.

Per risolvere questi problemi specifici, utilizza i seguenti metodi di risoluzione dei problemi.

## Tasti compositore errati

Se vedi il seguente errore che indica che hai le chiavi Composer non corrette:

```terminal
Could not find a matching version of package magento/express-checkout. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (RC).
```

Verifica che le chiavi del tuo Compositore siano collegate all&#39;ID Magento utilizzato durante la registrazione di Express Checkout.

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

## Stabilità minima `composer.json` è impostato su stable

Se vedi il seguente errore che indica che hai le chiavi Composer non corrette:

```terminal
Could not find a matching version of package magento/express-checkout. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).
```

Imposta stabilità minima su `RC` in `composer.json` file.

## Memoria insufficiente per PHP

Se vedi il seguente errore che indica che non hai abbastanza memoria per PHP:

```terminal
Fatal error: Allowed memory size of 2146435072 bytes exhausted (tried to allocate 4096 bytes) in phar:///usr/local/bin/composer/src/Composer/DependencyResolver/RuleWatchGraph.php on line 52
```

[Aumentare il limite di memoria](https://devdocs.magento.com/cloud/project/magento-app-php-ini.html#increase-php-memory-limit) per PHP sul tuo ambiente in `php.ini`.

In alternativa, è possibile specificare il limite di memoria utilizzando questo comando: `php -d memory_limit=-1 [path to composer]/composer require magento/express-checkout`.

Ad esempio:

```bash
php -d memory_limit=-1 vendor/bin/composer require magento/express-checkout
```

## Indirizzo di spedizione non valido

È presente un problema noto per [!DNL Express Checkout].

Se l&#39;indirizzo di spedizione predefinito non è valido, il cliente viene reindirizzato alla fase dell&#39;indirizzo di spedizione. Storefront mostra solo indirizzi di spedizione validi.

>[!WARNING]
>
> se non sono presenti indirizzi di spedizione validi, il cliente non visualizza alcun indirizzo di spedizione disponibile.

Fai riferimento a [dettagli di spedizione](../express-checkout/shipping-details.md) per ulteriori informazioni.

## Aggiungi linee di indirizzo di strada con un nuovo indirizzo di spedizione

È presente un problema noto per [!DNL Express Checkout].

Quando [accesso con un account Bolt](https://help.bolt.com/shoppers/guides/checkout/log-in/) è possibile aggiungere un nuovo indirizzo di spedizione con un limite di 4 righe per indirizzo stradale.

In genere, Adobe Commerce può essere configurato per supportare fino a 20 righe di indirizzo postale.

## Casella di controllo `enable terms and conditions` non visualizzato correttamente

È presente un problema noto per [!DNL Express Checkout].

Quando si abilita la `Enable terms and conditions` in Admin e accedi con un [!DNL Bolt] il conto `Enable terms and conditions` la casella di controllo non viene visualizzata durante il pagamento. Fai riferimento a [accedere](https://help.bolt.com/shoppers/account/login-dashboard/) [!DNL Bolt] per ulteriori informazioni.

Vedi [termini e condizioni](https://docs.magento.com/user-guide/sales/terms-and-conditions.html) per ulteriori informazioni sulla configurazione amministratore.

## Comportamento imprevisto quando `Display Billing Address On` è impostato su `payment page`

È presente un problema noto per [!DNL Express Checkout].

Se imposti la `Display Billing Address On` parametro a `payment page` e [accesso con un account Bolt](https://help.bolt.com/shoppers/guides/checkout/log-in/) quando controlli la `My billing and shipping address are the same` casella di controllo:

![Stesso indirizzo](assets/checked-address.png)

Display dei pulsanti di scelta `use existing card`.

Vedi [Pagamento](https://docs.magento.com/user-guide/configuration/sales/checkout.html) per ulteriori informazioni sul `Display Billing Address On` parametro .

## Traduzione del [!DNL Express Checkout] estensione

Adobe Commerce consente di localizzare il negozio per più aree geografiche e mercati. Puoi anche localizzare i messaggi di errore nella visualizzazione Amministratore.

Fai riferimento a [traduzione e localizzazione](https://devdocs.magento.com/guides/v2.4/frontend-dev-guide/translations/xlate.html) per ulteriori informazioni.

## Svuotare la cache

1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

## Assistenza

Contatto [!DNL Adobe Commerce] team di progettazione attraverso lo Slack assegnato [Canale dei programmi Adobe Beta](http://adobe-beta-programs.slack.com/) per qualsiasi assistenza.
