---
title: Installazione e configurazione
description: Scopri come installare, aggiornare e disinstallare [!DNL Product Recommendations].
source-git-commit: 4ad607c8595b25d01b5f5020b787fc1d35d4df25
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Installazione e configurazione

Distribuzione [!DNL Product Recommendations] per la vetrina e l’amministratore richiede l’installazione del modulo e la configurazione del connettore Commerce Services. Man mano che vengono rilasciati gli aggiornamenti, puoi facilmente aggiornare l’installazione con la versione più recente.

- [Installa](#install)
- [Configura](#configure)
- [Aggiorna](#update)
- [Disinstalla](#uninstall)

## Installa [!DNL Product Recommendations] {#install}

Perché [!DNL Product Recommendations] Il modulo è un metapackage autonomo, gli aggiornamenti vengono rilasciati più frequentemente di Adobe Commerce. Per essere sicuro di essere aggiornato con le ultime correzioni e funzioni di bug, fai riferimento alla [note sulla versione](release-notes.md).

Installa il `magento/product-recommendations` Modulo con Compositore:

```bash
composer require magento/product-recommendations
```

### Aggiunta del supporto per Page Builder {#pbsupport}

[!DNL Product Recommendations] per Page Builder è un modulo facoltativo e viene installato separatamente. Per utilizzare [!DNL Product Recommendations] con Page Builder, installa il modulo eseguendo il seguente comando:

```bash
composer require magento/module-page-builder-product-recommendations
```

Attivando [!DNL Product Recommendations] in Page Builder, puoi aggiungere un [unità di raccomandazione](https://docs.magento.com/user-guide/cms/page-builder-add-recommendations.html) a qualsiasi contenuto creato in Page Builder, ad esempio pagine, blocchi e blocchi dinamici.

### Aggiungi tipo di raccomandazione per similarità visiva {#vissimsupport}

La _Somiglianza visiva_ il tipo di raccomandazione consente di distribuire un&#39;unità di raccomandazione alla pagina dei dettagli del prodotto che visualizza i prodotti che sono [visivamente simile](type.md#visualsim) al prodotto visualizzato. Questo tipo di raccomandazione è particolarmente utile quando le immagini e gli aspetti visivi dei prodotti sono parti importanti dell’esperienza di acquisto. Installa il _Somiglianza visiva_ tipo di raccomandazione eseguendo il comando seguente:

```bash
composer require magento/module-visual-product-recommendations
```

## Configura [!DNL Product Recommendations] {#configure}

Dopo aver installato `magento/product-recommendations` modulo, devi configurare il [Connettore Commerce Services](https://docs.magento.com/user-guide/configuration/services/saas.html) specificando la chiave API e selezionando uno spazio dati SaaS.

Per verificare che l’esportazione del catalogo sia corretta, verifica che la [cron](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html) l&#39;occupazione e [indicizzatori](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html) sono in esecuzione e `Product Feed` indexer impostato su `Update by Schedule`.

Quando si effettua un collegamento a Commerce Services tramite la chiave API e si specifica lo spazio dati SaaS, la sincronizzazione del catalogo viene avviata e [verifica](verify.md) che i dati comportamentali vengono inviati alla tua vetrina.

## Aggiorna il tuo [!DNL Product Recommendations] installazione {#update}

Come tutti Adobe Commerce, [!DNL Product Recommendations] utilizza Composer per l&#39;installazione e gli aggiornamenti. Per aggiornare `magento/product-recommendations` , esegui quanto segue:

```bash
composer update magento/product-recommendations --with-dependencies
```

Per eseguire l’aggiornamento a una versione principale, ad esempio da 2.0 a 3.0, devi modificare la directory principale del progetto `composer.json` file. (Vedi [note sulla versione](release-notes.md) per informazioni sull&#39;ultima versione). Ad esempio, apriamo il `composer.json` e cerca il `magento/product-recommendations` modulo:

```json
"require": {
    ...
    "magento/product-recommendations": "^2.0",
    ...
}
```

Scarichiamo la versione principale da `2.0` a `3.0`:

```json
"require": {
    ...
    "magento/product-recommendations": "^3.0",
    ...
}
```

Salva il `composer.json` file ed esecuzione:

```bash
composer update magento/product-recommendations --with-dependencies
```

## Disinstalla [!DNL Product Recommendations] {#uninstall}

Se necessario, puoi [disinstallare](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-uninstall-mods.html) il modulo product-recommendations.
