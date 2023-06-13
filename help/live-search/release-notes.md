---
title: '''[!DNL Live Search] Note sulla versione'
description: "Informazioni aggiornate sulla versione di [!DNL Live Search] da Adobe Commerce."
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
source-git-commit: d4f22cdae9b4b0a19691465ae87e344847672698
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 0%

---

# [!DNL Live Search] Note sulla versione

Queste note sulla versione descrivono le versioni più recenti di [!DNL Live Search].
È disponibile il supporto per la versione principale rilasciata corrente. Vengono fornite a titolo di riferimento le note sulla versione per le versioni precedenti.
Gli aggiornamenti includono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Correzione](../assets/fix.svg) Correzioni e miglioramenti
![Bug](../assets/bug.svg) Problemi noti


_13 giugno 2023_

![Nuovo](../assets/new.svg) Live Search ora supporta altri 5 [valori di configurazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-admin/configuration.html).
![Correzione](../assets/fix.svg) È stato risolto un problema che causava problemi di classificazione per alcuni caratteri, ad esempio virgolette o apostrofi. La reindicizzazione risolverà questi problemi.

_25 aprile 2023_

![Nuovo](../assets/new.svg) I clienti di Live Search ora possono sfruttare la nuova [Indicizzatore prezzi SaaS](../price-index/index.md).

## [!DNL Live Search] 3.0.1 {#301}

_14 marzo 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

### Nuove funzioni

* Scheda articolo prodotto nell’anteprima delle regole
* [Widget pagina elenco prodotti](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-storefront/plp-styling.html)
* [Opzioni filtro categorie](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/#facets)
* Aggiunta la possibilità di trascinare e rilasciare per creare eventi pin
* Nuove azioni pin:
   * Fissa al punto - Fissa il pulsante per creare l’evento Fissa con un clic
   * Fissa in alto - Posiziona il prodotto in prima posizione
   * Fissa in basso: inserisce il prodotto nella parte inferiore dei risultati.
   * Sbloccare un evento con un clic
* [Classificazione intelligente per le regole](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-admin/rules/rules-add.html#ranking-type)

### Aggiornamenti

* Configura regole ora ordina automaticamente le posizioni in modo univoco
* L’eliminazione di un evento esistente aggiorna l’anteprima
* È possibile salvare regole senza eventi
* Rimuovi selettore &quot;Seleziona tipo&quot; facet
* È stato aggiunto il nuovo stato &quot;Modifica&quot; per le regole non salvate

### Correzioni

* È stato corretto un errore del server in presenza di un evento non completato durante il salvataggio
* È stata corretta l’eliminazione di un evento specifico in presenza di più eventi
* È stato corretto un evento regola esistente che non viene aggiornato quando viene aggiunto un nuovo evento
* Risolto il secondo clic &quot;Modifica&quot; dai dettagli, [!DNL Live Search] pagina da ricaricare
* Sinonimi: è stato risolto un problema che impediva all’utente di uscire dall’input in quanto non poteva riportare lo stato attivo sul campo
* Altre correzioni di bug minori e aggiornamenti delle prestazioni


* ![Bug](../assets/bug.svg) - La classificazione per &quot;Consigliato per te&quot; è supportata solo all’interno dei widget Live Search. Non è supportato con le funzionalità di ricerca Luma e PWA predefinite.
* ![Bug](../assets/bug.svg) - I facet di attributi di prezzo personalizzati non vengono visualizzati correttamente in Luma, ma l’API li filtra correttamente.

I commercianti devono aggiornare [!DNL Live Search] versione dell&#39;estensione >= 3.0.1 per accedere a queste funzioni.

Si consiglia di eseguire l’aggiornamento e il test prima di passare alla produzione. Dopo aver verificato i risultati dell’ambiente di test, è consigliabile aggiornare l’ambiente di produzione nelle ore di minore utilizzo.

## Versioni precedenti

+++2.0.5 e precedenti

## [!DNL Live Search] 2.0.5 {#205}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Correzione](../assets/fix.svg) - Live Search genererebbe un errore quando le risorse SDK non erano disponibili a causa di problemi di rete. Questo bug è stato corretto.

Per accedere a queste funzioni, i commercianti devono aggiornare la versione dell’estensione Live Search >= 2.0.5.

Si consiglia di eseguire l’aggiornamento e il test prima di passare alla produzione. Dopo aver verificato i risultati dell’ambiente di test, è consigliabile aggiornare l’ambiente di produzione nelle ore di minore utilizzo.

### [!DNL Live Search] 2.0.4 {#204}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Live Search ora supporta il filtro in base all’impostazione &quot;Visualizza prodotti esauriti&quot; nell’amministratore. Se &#39;Visualizza prodotti esauriti&#39; è impostato su false, `inStock = true` viene aggiunto al filtro.
![Correzione](../assets/fix.svg) Per migliorare le prestazioni, il blocco &quot;Suggerimenti&quot; è stato rimosso dal pop-up Live Search. I dati vengono comunque trasmessi tramite GraphQL, nel caso in cui desideri sostituire la funzione.
![Correzione](../assets/fix.svg) `categories` e `categoryPath` hanno sostituito `categoryIds` per il filtro delle categorie. Per ulteriori informazioni, consulta [productSearch](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/) argomento.
![Correzione](../assets/fix.svg) In precedenza, un utente associato a un’azienda B2B riceveva un codice di gruppo cliente errato durante le ricerche. Live Search ora restituisce il valore corretto.
![Correzione](../assets/fix.svg) In precedenza, quando si cercava un termine che non esiste, Live Search restituiva un errore. Questo bug è ora corretto.

I commercianti devono aggiornare [!DNL Live Search] versione dell&#39;estensione >= 2.0.4 per accedere a queste funzioni.

Si consiglia agli utenti di eseguire l’aggiornamento e il test prima di passare alla produzione. Dopo aver verificato i risultati dell’ambiente di test, è consigliabile aggiornare l’ambiente di produzione nelle ore di minore utilizzo.

### [!DNL Live Search] 2.0.3 {#203}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Live Search ora supporta le funzioni B2B rispettando le autorizzazioni per le categorie, i cataloghi condivisi e i prezzi specifici per i gruppi di clienti.

I commercianti devono aggiornare [!DNL Live Search] versione dell&#39;estensione >= 2.0.3 per accedere a queste funzioni.

Si consiglia agli utenti di eseguire l’aggiornamento e il test prima di passare alla produzione. Dopo aver verificato i risultati dell’ambiente di test, è consigliabile aggiornare l’ambiente di produzione nelle ore di minore utilizzo.

### [!DNL Live Search] 2.0 {#20}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

Esistente [!DNL Live Search] le installazioni devono essere aggiornate a [!DNL Live Search] 2.0.0 per usufruire delle seguenti nuove funzioni, correzioni e miglioramenti:

![Nuovo](../assets/new.svg) [!DNL Live Search] ora supporta PHP 8.1 per le installazioni con Adobe Commerce 2.4.4.
![Nuovo](../assets/new.svg) Il `Magento_ElasticsearchCatalogPermissionsGraphQl` viene aggiunto all&#39;elenco dei moduli disattivati durante l&#39;installazione.
![Nuovo](../assets/new.svg) Numero di righe disponibili nel [[!DNL storefront popover]](quick-tour.md) può essere configurato dal *Amministratore*.
![Nuovo](../assets/new.svg) Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) compatibilità per [!DNL Live Search].
![Nuovo](../assets/new.svg) Il [!DNL Live Search] il processo di installazione viene aggiornato con modifiche avanzate.
![Correzione](../assets/fix.svg) [Ricerca avanzata](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) collegamento rimosso dal piè di pagina vetrina.
![Bug](../assets/bug.svg) I seguenti attributi di prodotto non sono supportati da [API Commerce GraphQL](https://developer.adobe.com/commerce/webapi/graphql/) se utilizzato in relazione alla versione beta di PWA: `description`, `name`, `short_description`
![Bug](../assets/bug.svg) Versione beta di PWA per [!DNL Live Search] non supporta [gestione degli eventi](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).

### [!DNL Live Search] 1.3.1 {#131}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) [Attributo prezzo personalizzato](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/attributes-input-types.html) non restituisce più un errore quando è configurato come [facet]({% link live-search/facets-add.md %}).
![Correzione](../assets/fix.svg) È stato risolto un problema che causava la visualizzazione di un errore in caso di [simbolo di valuta](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html#step-5%3A-customize-currency-symbols-(optional)) (`data-currency-symbol`).
![Correzione](../assets/fix.svg) [[!DNL Storefront popover]](storefront-popover.md) mostra ora il [Prezzo speciale](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-special.html) (prezzo finale minimo) se disponibile.

### [!DNL Live Search] 1.3.0 {#130}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) [Prestazioni](performance.md) il dashboard di reporting fornisce informazioni approfondite sui termini di ricerca utilizzati dagli acquirenti.
![Nuovo](../assets/new.svg) [!DNL Live Search] [SDK per eventi storefront](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) fornisce l’accesso a un livello dati comune con servizi e metriche di pubblicazione e abbonamento di eventi.
![Correzione](../assets/fix.svg) Il [[!DNL Storefront popover]](storefront-popover.md) ha un nuovo `active` classe per `.search-autocomplete` contenitore che controlla la visibilità.
![Correzione](../assets/fix.svg) Nella vetrina, il [Termini di ricerca](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html#popular-search-terms) il collegamento del piè di pagina viene rimosso e la relativa cache disabilitata per [!DNL Live Search] installazioni.
![Bug](../assets/bug.svg) La patch per l&#39;adattatore di ricerca gestisce i prodotti duplicati.
![Bug](../assets/bug.svg) [!DNL Live Search] supporta [fonte singola](https://experienceleague.adobe.com/docs/commerce-admin/inventory/sources/sources-manage.html) ubicazioni di inventario (fisiche) con più ubicazioni (virtuali) [scorte](https://experienceleague.adobe.com/docs/commerce-admin/inventory/stocks/stocks-manage.html). Al momento non sono supportate più origini inventario.

### [!DNL Live Search] 1.2.0 {#120}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) [[!DNL Storefront popover]](storefront-popover.md) consente di visualizzare i prodotti suggeriti e le miniature dei risultati di ricerca principali quando gli acquirenti digitano query nella casella Ricerca.
![Nuovo](../assets/new.svg) Commerce *Amministratore* la sessione rimane aperta durante periodi prolungati di inattività della tastiera
![Nuovo](../assets/new.svg) [!DNL Live Search] viene abilitato automaticamente dopo l’onboarding
![Correzione](../assets/fix.svg) Il tempo di indicizzazione iniziale è inferiore a un&#39;ora
![Correzione](../assets/fix.svg) Aggiornamenti incrementali dei prodotti quasi in tempo reale (dopo l&#39;installazione e l&#39;installazione)
![Correzione](../assets/fix.svg) Colonne ordinabili nell’editor sinonimo
![Correzione](../assets/fix.svg) [!DNL Live Search] non genera più un errore se il criterio di ricerca contiene un valore di ordinamento vuoto
![Correzione](../assets/fix.svg) Il filtro degli intervalli non si interrompe più se i codici attributo contengono stringhe &quot;a&quot; o &quot;da&quot;

### [!DNL Live Search] 1.1.0 {#110}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Bug](../assets/bug.svg) Il [!DNL Live Search] il servizio supporta solo [valuta di base](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html) dell’installazione di Adobe Commerce.
![Bug](../assets/bug.svg) Quando si aggiunge un facet, il feed degli attributi del prodotto non viene aggiornato correttamente se impostato su `Update on Save`. Per evitare questo problema, vai a [Gestione indice](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html) e impostare Product Attributes Feed su `Update by Schedule`.
![Bug](../assets/bug.svg) [!DNL Live Search] i sinonimi sono definiti per visualizzazione store, ma sono attualmente memorizzati per sito web e identificati con una combinazione di `environmentId` e `storeViewCode`. Di conseguenza, tutti i siti web e le visualizzazioni dello store all’interno dell’installazione di Adobe Commerce condividono i sinonimi. Il set di sinonimi creato più di recente per la visualizzazione Store ha la precedenza.
![Bug](../assets/bug.svg) Se un sinonimo contiene più parole, ogni parola viene trattata come un sinonimo separato. Ad esempio, se definisci &quot;pezzo orario&quot; come sinonimo di &quot;orologio&quot;, sia &quot;tempo&quot; che &quot;pezzo&quot; vengono trattati come sinonimi di orologio.

+++

## Documentazione

Per ulteriori informazioni:

* [Documentazione per gli sviluppatori di Adobe Commerce](https://developer.adobe.com/commerce/docs)
* [Guida utente di Adobe Commerce](https://experienceleague.adobe.com/docs/commerce.html)
* [[!DNL Live Search] su Marketplace](https://marketplace.magento.com/magento-live-search.html)
