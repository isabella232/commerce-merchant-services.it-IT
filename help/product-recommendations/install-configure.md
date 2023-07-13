---
title: Installazione e configurazione
description: Scopri come installare, aggiornare e disinstallare [!DNL Product Recommendations].
exl-id: fa599f72-1064-41da-ac54-2b3a3c16a1fe
role: Admin, Developer
source-git-commit: 9ae4aff1851e9ce9920c4fbf11d2616d6f0f6307
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%

---

# Installazione e configurazione

Distribuzione [!DNL Product Recommendations] nella vetrina e l&#39;amministratore richiede di installare il modulo e configurare [Connettore Commerce Services](../landing/saas.md). Man mano che gli aggiornamenti vengono rilasciati, puoi aggiornare facilmente l’installazione con l’ultima versione.

- [Installa](#install)
- [Configura](#configure)
- [Aggiorna](#update)
- [Disinstalla](#uninstall)

## Installa [!DNL Product Recommendations] {#install}

Perché il [!DNL Product Recommendations] Il modulo di è un metapacchetto autonomo; gli aggiornamenti vengono rilasciati più frequentemente rispetto ad Adobe Commerce. Per essere certi di essere aggiornati sulle ultime correzioni di bug e funzioni, consulta [note sulla versione](release-notes.md).

Installare `magento/product-recommendations` Modulo con Compositore:

```bash
composer require magento/product-recommendations
```

### Supporto per Aggiungi Page Builder {#pbsupport}

[!DNL Product Recommendations] per Page Builder è un modulo opzionale e viene installato separatamente. Da utilizzare [!DNL Product Recommendations] con Page Builder, installare il modulo eseguendo il comando seguente:

```bash
composer require magento/module-page-builder-product-recommendations
```

Attivando [!DNL Product Recommendations] in Page Builder, è possibile aggiungere un elemento attivo esistente [unità consigli](https://experienceleague.adobe.com/docs/commerce-admin/page-builder/add-content/recommendations.html) a qualsiasi contenuto creato in Page Builder, ad esempio pagine, blocchi e blocchi dinamici.

Consulta [Utilizzo di [!DNL Product Recommendations] con contenuto Page Builder](page-builder.md) per ulteriori istruzioni.

### Aggiungi tipo di consiglio per somiglianza visiva {#vissimsupport}

Il _Somiglianza visiva_ tipo di consiglio consente di distribuire un’unità di consigli nella pagina dei dettagli del prodotto, in cui vengono visualizzati i prodotti [visivamente simile](type.md#visualsim) al prodotto visualizzato. Questo tipo di consigli è più utile quando le immagini e gli aspetti visivi dei prodotti sono parti importanti dell’esperienza di acquisto. Installare _Somiglianza visiva_ tipo di consiglio eseguendo il comando seguente:

```bash
composer require magento/module-visual-product-recommendations
```

## Configura [!DNL Product Recommendations] {#configure}

Dopo aver installato `magento/product-recommendations` , è necessario configurare il [Connettore Commerce Services](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) specificando le chiavi API e selezionando uno spazio dati SaaS.

Per garantire il corretto funzionamento dell’esportazione del catalogo, verifica che [cron](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs.html) job e [indici](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/manage-indexers.html) sono in esecuzione e `Product Feed` indicizzatore impostato su `Update by Schedule`.

Una volta effettuato correttamente il collegamento a Commerce Services tramite le chiavi API e specificato SaaS Data Space, inizia la sincronizzazione del catalogo. Potrai quindi [verifica](verify.md) i dati comportamentali vengono inviati alla vetrina.

## Aggiorna il tuo [!DNL Product Recommendations] installazione {#update}

Come tutte le soluzioni Adobe Commerce, [!DNL Product Recommendations] utilizza Composer per l&#39;installazione e gli aggiornamenti. Per aggiornare `magento/product-recommendations` eseguire quanto segue:

```bash
composer update magento/product-recommendations --with-dependencies
```

Per eseguire l’aggiornamento a una versione principale, ad esempio da 3.0 a 4.0, devi modificare la directory principale `composer.json` per il progetto. (consultare la [note sulla versione](release-notes.md) per informazioni sull&#39;ultima versione). Ad esempio, apriamo l’elemento principale `composer.json` e cercare il file `magento/product-recommendations` modulo:

```json
"require": {
    ...
    "magento/product-recommendations": "^3.0",
    ...
}
```

Saltiamo la versione principale da `3.0` a `4.0`:

```json
"require": {
    ...
    "magento/product-recommendations": "^4.0",
    ...
}
```

Salva il `composer.json` file ed esegui:

```bash
composer update magento/product-recommendations --with-dependencies
```

Oppure, se hai installato `magento/module-visual-product-recommendations` e `magento/module-page-builder-product-recommendations` moduli:

```bash
composer update --with-dependencies magento/product-recommendations magento/module-visual-product-recommendations magento/module-page-builder-product-recommendations
```

>[!NOTE]
>
> Nelle versioni 3.x.x di Product Recommendations, era necessaria una sola chiave API. Nelle versioni 4.x.x e successive, devi fornire le chiavi API di produzione pubbliche e private nonché le chiavi API sandbox pubbliche e private. Se non fornisci entrambe le coppie di chiavi API, non puoi accedere alla funzione Product Recommendations in Admin. La raccolta dei dati, tuttavia, continuerà nella tua vetrina e i consigli esistenti continueranno a essere visualizzati ai tuoi acquirenti.

## Disinstalla [!DNL Product Recommendations] {#uninstall}

Se necessario, puoi [disinstalla](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/tutorials/uninstall-modules.html) il modulo prodotti-consigli.
