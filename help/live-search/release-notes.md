---
title: Note sulla versione di Live Search
description: Informazioni aggiornate sulla versione di Live Search da Adobe Commerce.
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
source-git-commit: 65126f10574801f7ea8d0a863e9bb512dca13f39
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Live Search] Note sulla versione

Queste note sulla versione descrivono le versioni più recenti di [!DNL Live Search] e comprendono:

* ![Nuovo](../assets/new.svg) - Nuove funzioni
* ![Correzione](../assets/fix.svg) - Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) - Problemi noti

## [!DNL Live Search] 2,0

* Compatibile con Adobe Commerce (EE): 2.4.x
* Compatibile con Adobe Commerce per Cloud (ECE): 2.4.x
* Stabilità: Stabile

Esistente [!DNL Live Search] le installazioni devono essere aggiornate a [!DNL Live Search] 2.0.0 per usufruire delle seguenti nuove funzioni, correzioni e miglioramenti:

* ![Nuovo](../assets/new.svg) - [!DNL Live Search] ora supporta PHP 8.1 per le installazioni con Adobe Commerce 2.4.4.
* ![Nuovo](../assets/new.svg) - `Magento_ElasticsearchCatalogPermissionsGraphQl` Il modulo viene aggiunto all’elenco dei moduli disattivati durante l’installazione.
* ![Nuovo](../assets/new.svg) - Il numero di righe disponibili nel [[!DNL storefront popover]](quick-tour.md) può essere configurato da *Amministratore*.
* ![Nuovo](../assets/new.svg) - Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) compatibilità per [!DNL Live Search].
* ![Nuovo](../assets/new.svg) - [!DNL Live Search] il processo di installazione viene aggiornato con modifiche avanzate del processo.
* ![Correzione](../assets/fix.svg) - [Ricerca avanzata](https://docs.magento.com/user-guide/catalog/search-advanced.html) collegamento rimosso dal piè di pagina della vetrina.
* ![Bug](../assets/bug.svg) - I seguenti attributi di prodotto non sono supportati da [API GraphQL di Magento](https://devdocs.magento.com/guides/v2.4/graphql) se utilizzato in relazione alla versione beta di PWA: `description`, `name`, `short_description`
* ![Bug](../assets/bug.svg) - Versione beta di PWA per [!DNL Live Search] non supporta [gestione degli eventi](https://devdocs.magento.com/shared-services/storefront-events-sdk.html).

## [!DNL Live Search] 1.3.1

* Compatibile con Adobe Commerce (EE): 2.4.x
* Compatibile con Adobe Commerce per Cloud (ECE): 2.4.x
* Stabilità: Stabile

* ![Correzione](../assets/fix.svg) - [Attributo prezzo personalizzato](https://docs.magento.com/user-guide/stores/attributes-input-types.html) non restituisce più un errore se configurato come [sfaccettatura]({% link live-search/facets-add.md %}).
* ![Correzione](../assets/fix.svg) - È stato risolto un problema che causava un errore in assenza di [simbolo di valuta](https://docs.magento.com/user-guide/stores/currency-symbols.html) (`data-currency-symbol`) è disponibile.
* ![Correzione](../assets/fix.svg) - [[!DNL Storefront popover]](storefront-popover.md) ora mostra [Prezzo speciale](https://docs.magento.com/user-guide/catalog/product-price-special.html) (prezzo finale minimo) se disponibile.

## [!DNL Live Search] 1.3.0

* Compatibile con Adobe Commerce (EE): 2.4.x
* Compatibile con Adobe Commerce per Cloud (ECE): 2.4.x
* Stabilità: Stabile

* ![Nuovo](../assets/new.svg) - [Prestazioni](performance.md) il dashboard di reporting fornisce informazioni approfondite sui termini di ricerca utilizzati dagli acquirenti.
* ![Nuovo](../assets/new.svg) - [!DNL Live Search] [SDK per eventi Storefront](https://devdocs.magento.com/shared-services/storefront-events-sdk.html) fornisce l’accesso a un livello di dati comune con servizi di pubblicazione degli eventi e di abbonamento e metriche.
* ![Correzione](../assets/fix.svg) - [[!DNL Storefront Popover]](https://devdocs.magento.com/live-search/storefront-popover.html) ha `active` per `.search-autocomplete` contenitore che controlla la visibilità.
* ![Correzione](../assets/fix.svg) - Nella vetrina, [Termini di ricerca](https://docs.magento.com/user-guide/marketing/search-terms-popular.html) il collegamento a piè di pagina viene rimosso e la relativa cache è disabilitata per [!DNL Live Search] installazioni.
* ![Bug](../assets/bug.svg) - Patch per l&#39;adattatore di ricerca gestisce i prodotti duplicati.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] supporta [a sorgente singola](https://docs.magento.com/user-guide/catalog/inventory-sources.html) (fisico) posizioni di inventario con più (virtuali) [stock](https://docs.magento.com/user-guide/catalog/inventory-stock.html). Al momento non sono supportate più origini di inventario.

## [!DNL Live Search] 1.2.0

* Compatibile con Adobe Commerce (EE): 2.4.x
* Compatibile con Adobe Commerce per Cloud (ECE): 2.4.x
* Stabilità: Stabile

* ![Nuovo](../assets/new.svg) - [[!DNL Storefront popover]](storefront-popover.md) visualizza i prodotti consigliati e le miniature dei risultati di ricerca principali come query di tipo shoppers nella casella di ricerca.
* ![Nuovo](../assets/new.svg) - Commercio *Amministratore* la sessione rimane aperta durante lunghi periodi di inattività della tastiera
* ![Nuovo](../assets/new.svg) - [!DNL Live Search] viene automaticamente attivato dopo l&#39;onboarding
* ![Correzione](../assets/fix.svg) - Il tempo di indicizzazione iniziale è inferiore a un&#39;ora
* ![Correzione](../assets/fix.svg) - Aggiornamenti incrementali dei prodotti in tempo reale (dopo l&#39;installazione e la configurazione)
* ![Correzione](../assets/fix.svg) - Colonne ordinabili nell’editor sinonimo
* ![Correzione](../assets/fix.svg) - [!DNL Live Search] non genera più un errore se i criteri di ricerca contengono un valore di ordinamento vuoto
* ![Correzione](../assets/fix.svg) - Il filtro dell&#39;intervallo non si interrompe più se i codici attributo contengono stringhe &quot;to&quot; o &quot;from&quot;

## [!DNL Live Search] 1.1.0

* Compatibile con Adobe Commerce (EE): 2.4.x
* Compatibile con Adobe Commerce per Cloud (ECE): 2.4.x
* Stabilità: Stabile

* ![Bug](../assets/bug.svg) - [!DNL Live Search] il servizio supporta solo [valuta di base](https://docs.magento.com/user-guide/stores/currency-configuration.html) dell’installazione di Adobe Commerce.
* ![Bug](../assets/bug.svg) - Quando si aggiunge un facet, il feed degli attributi del prodotto non viene aggiornato correttamente se è impostato su `Update on Save`. Per evitare questo problema, vai a [Gestione dell&#39;indice](https://docs.magento.com/user-guide/system/index-management.html) e imposta Feed attributi del prodotto su `Update by Schedule`.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] i sinonimi sono definiti per visualizzazione store, ma sono attualmente memorizzati per sito web e identificati con una combinazione di `environmentId` + `storeViewCode`. Di conseguenza, tutti i siti web e le viste store all’interno dell’installazione di Adobe Commerce condividono lo stesso set di sinonimi. Il set di sinonimi creato più di recente per la visualizzazione Store ha la precedenza.
* ![Bug](../assets/bug.svg) - Se un termine sinonimo contiene più parole, ogni parola viene trattata come un sinonimo separato. Ad esempio, se definisci &quot;tempo&quot; come sinonimo di &quot;orologio&quot;, sia &quot;tempo&quot; che &quot;pezzo&quot; vengono trattati come sinonimi di orologio.

## Documentazione

Per ulteriori informazioni:

* [Documentazione per gli sviluppatori di Adobe Commerce](https://devdocs.magento.com/)
* [Guida utente di Adobe Commerce](https://docs.magento.com/user-guide/)
* [[!DNL Live Search] su Marketplace](https://marketplace.magento.com/magento-live-search.html)
