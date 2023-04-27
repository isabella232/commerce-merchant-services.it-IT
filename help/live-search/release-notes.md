---
title: '''[!DNL Live Search] Note sulla versione"'
description: "Informazioni sulla versione più recente per [!DNL Live Search] da Adobe Commerce."
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
source-git-commit: f955cfc918c19a3c32126d8c9ef8a59b0e0dce0a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Live Search] Note sulla versione

Queste note sulla versione descrivono le versioni più recenti di [!DNL Live Search].
Viene fornito il supporto per la versione principale corrente rilasciata. Per riferimento, sono disponibili note sulla versione per le versioni precedenti.
Gli aggiornamenti includono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Correzione](../assets/fix.svg) Correzioni e miglioramenti
![Bug](../assets/bug.svg) Problemi noti


_25 aprile 2023_

![Nuovo](../assets/new.svg) Ora i clienti di Live Search possono sfruttare i nuovi [Indicizzatore prezzo SaaS](../price-index/index.md).

## [!DNL Live Search] 3.0.1 {#301}

_14 marzo 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

### Nuove funzioni

* Scheda dell’elemento prodotto nell’anteprima delle regole
* [Widget Pagina di elenco prodotti](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-storefront/plp-styling.html)
* [Opzioni di filtro per categorie](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/#facets)
* Aggiunta la possibilità di trascinare per creare eventi Pin
* Nuove azioni pin:
   * Pin to spot - Pulsante Pin per creare un evento Pin con un clic
   * Fissa in alto - Posiziona il prodotto nella prima posizione
   * Pin to bottom - Posiziona il prodotto in fondo ai risultati
   * Sblocca un evento con un solo clic
* [Classifica intelligente per le regole](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-admin/rules/rules-add.html#ranking-type)

### Aggiornamenti

* Configura ora le regole ordinano automaticamente le posizioni in modo univoco
* L&#39;eliminazione di un evento esistente aggiorna ora l&#39;anteprima
* È possibile salvare regole senza eventi
* Rimuovi selettore &quot;Seleziona tipo&quot; di facet
* È stato aggiunto un nuovo stato di &quot;Modifica&quot; per le regole non salvate

### Correzioni

* È stato corretto un errore del server in caso di evento non completato durante il salvataggio
* È stata corretta l’eliminazione corretta di un evento specifico in presenza di più eventi
* È stato corretto un evento di regola esistente che non si aggiornava quando veniva aggiunto un nuovo evento
* È stato corretto il secondo clic &quot;Edit&quot; (Modifica) dai dettagli, [!DNL Live Search] pagina che richiede il ricaricamento
* Sinonimi: È stato risolto un problema che impediva all’utente di tornare a visualizzare il campo su cui faceva clic.
* Altre correzioni di bug minori e aggiornamenti delle prestazioni


* ![Bug](../assets/bug.svg) - La classificazione di &quot;Consigliato per te&quot; è supportata solo all’interno dei widget Live Search. Non è supportato con la funzionalità di ricerca Luma e PWA predefinita.
* ![Bug](../assets/bug.svg) - I facet di attributi di prezzo personalizzati non vengono visualizzati correttamente in Luma, ma l’API vi filtra correttamente.

I merchants devono aggiornare [!DNL Live Search] versione dell&#39;estensione >= 3.0.1 per accedere a queste funzioni.

Si consiglia di eseguire l’aggiornamento e il test prima di passare alla produzione. È consigliabile aggiornare l&#39;ambiente di produzione durante le ore di inattività dopo la verifica dei risultati dell&#39;ambiente di test.

## Versioni precedenti

+++2.0.5 e versioni precedenti

## [!DNL Live Search] 2.0.5 {#205}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Correzione](../assets/fix.svg) - Live Search genera un errore quando le risorse SDK non erano disponibili a causa di problemi di rete. Questo bug è stato corretto.

Per accedere a queste funzioni, i merchants devono aggiornare l’estensione Live Search >= 2.0.5 .

Si consiglia di eseguire l’aggiornamento e il test prima di passare alla produzione. È consigliabile aggiornare l&#39;ambiente di produzione durante le ore di inattività dopo la verifica dei risultati dell&#39;ambiente di test.

### [!DNL Live Search] 2.0.4 {#204}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Live Search supporta ora il filtro tramite l’impostazione &quot;Mostra prodotti non disponibili&quot; nell’amministratore. Se &#39;Display Out of Stock Products&#39; è impostato su false, `inStock = true` viene aggiunto al filtro.
![Correzione](../assets/fix.svg) Per migliorare le prestazioni, il blocco &quot;Suggerimenti&quot; è stato rimosso dalla finestra a comparsa Live Search. I dati vengono comunque trasmessi tramite GraphQL, nel caso in cui desideri sostituire la funzione.
![Correzione](../assets/fix.svg) `categories` e `categoryPath` hanno sostituito `categoryIds` per il filtro delle categorie. Ulteriori informazioni nella sezione [productSearch](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/) argomento.
![Correzione](../assets/fix.svg) In precedenza, un utente legato a un’azienda B2B riceveva un codice del gruppo di clienti errato durante le ricerche. Live Search restituisce ora il valore corretto.
![Correzione](../assets/fix.svg) In precedenza, quando si cercava un termine che non esiste, Live Search restituiva un errore. Questo bug è stato corretto.

I merchants devono aggiornare [!DNL Live Search] versione dell&#39;estensione >= 2.0.4 per accedere a queste funzioni.

Consigliamo agli utenti di eseguire l’aggiornamento e il test prima di passare alla produzione. È consigliabile aggiornare l&#39;ambiente di produzione durante le ore di inattività dopo la verifica dei risultati dell&#39;ambiente di test.

### [!DNL Live Search] 2.0.3 {#203}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Live Search supporta ora le funzioni B2B rispettando le autorizzazioni per le categorie, i cataloghi condivisi e i prezzi specifici per i gruppi di clienti.

I merchants devono aggiornare [!DNL Live Search] versione dell&#39;estensione >= 2.0.3 per accedere a queste funzioni.

Consigliamo agli utenti di eseguire l’aggiornamento e il test prima di passare alla produzione. È consigliabile aggiornare l&#39;ambiente di produzione durante le ore di inattività dopo la verifica dei risultati dell&#39;ambiente di test.

### [!DNL Live Search] 2.0 {#20}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

Esistente [!DNL Live Search] le installazioni devono essere aggiornate a [!DNL Live Search] 2.0.0 per usufruire delle seguenti nuove funzioni, correzioni e miglioramenti:

![Nuovo](../assets/new.svg) [!DNL Live Search] ora supporta PHP 8.1 per le installazioni con Adobe Commerce 2.4.4.
![Nuovo](../assets/new.svg) La `Magento_ElasticsearchCatalogPermissionsGraphQl` Il modulo viene aggiunto all’elenco dei moduli disattivati durante l’installazione.
![Nuovo](../assets/new.svg) Il numero di righe disponibili nel [[!DNL storefront popover]](quick-tour.md) può essere configurato da *Amministratore*.
![Nuovo](../assets/new.svg) Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) compatibilità per [!DNL Live Search].
![Nuovo](../assets/new.svg) La [!DNL Live Search] il processo di installazione viene aggiornato con modifiche avanzate del processo.
![Correzione](../assets/fix.svg) [Ricerca avanzata](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) collegamento rimosso dal piè di pagina della vetrina.
![Bug](../assets/bug.svg) I seguenti attributi di prodotto non sono supportati da [API di Commerce GraphQL](https://developer.adobe.com/commerce/webapi/graphql/) se utilizzato in relazione alla versione beta di PWA: `description`, `name`, `short_description`
![Bug](../assets/bug.svg) Versione beta di PWA per [!DNL Live Search] non supporta [gestione degli eventi](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).

### [!DNL Live Search] 1.3.1 {#131}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) [Attributo prezzo personalizzato](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/attributes-input-types.html) non restituisce più un errore se configurato come [sfaccettatura]({% link live-search/facets-add.md %}).
![Correzione](../assets/fix.svg) È stato risolto un problema che causava un errore in assenza di [simbolo di valuta](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html#step-5%3A-customize-currency-symbols-(optional)) (`data-currency-symbol`) è disponibile.
![Correzione](../assets/fix.svg) [[!DNL Storefront popover]](storefront-popover.md) ora mostra [Prezzo speciale](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-special.html) (prezzo finale minimo) se disponibile.

### [!DNL Live Search] 1.3.0 {#130}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) [Prestazioni](performance.md) il dashboard di reporting fornisce informazioni approfondite sui termini di ricerca utilizzati dagli acquirenti.
![Nuovo](../assets/new.svg) [!DNL Live Search] [SDK per eventi Storefront](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) fornisce l’accesso a un livello di dati comune con servizi di pubblicazione degli eventi e di abbonamento e metriche.
![Correzione](../assets/fix.svg) La [[!DNL Storefront popover]](storefront-popover.md) ha `active` per `.search-autocomplete` contenitore che controlla la visibilità.
![Correzione](../assets/fix.svg) Nella vetrina, il [Termini di ricerca](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html#popular-search-terms) il collegamento a piè di pagina viene rimosso e la relativa cache è disabilitata per [!DNL Live Search] installazioni.
![Bug](../assets/bug.svg) Patch per l&#39;adattatore di ricerca gestisce i prodotti duplicati.
![Bug](../assets/bug.svg) [!DNL Live Search] supporta [a sorgente singola](https://experienceleague.adobe.com/docs/commerce-admin/inventory/sources/sources-manage.html) (fisico) posizioni di inventario con più (virtuali) [stock](https://experienceleague.adobe.com/docs/commerce-admin/inventory/stocks/stocks-manage.html). Più origini di inventario non sono supportate ora.

### [!DNL Live Search] 1.2.0 {#120}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) [[!DNL Storefront popover]](storefront-popover.md) visualizza i prodotti consigliati e le miniature dei risultati di ricerca principali come query di tipo shoppers nella casella di ricerca.
![Nuovo](../assets/new.svg) Commerce *Amministratore* la sessione rimane aperta durante lunghi periodi di inattività della tastiera
![Nuovo](../assets/new.svg) [!DNL Live Search] viene automaticamente attivato dopo l&#39;onboarding
![Correzione](../assets/fix.svg) Il tempo di indicizzazione iniziale è inferiore a un&#39;ora
![Correzione](../assets/fix.svg) Aggiornamenti incrementali dei prodotti in tempo reale (dopo l&#39;installazione e la configurazione)
![Correzione](../assets/fix.svg) Colonne ordinabili nell’editor sinonimo
![Correzione](../assets/fix.svg) [!DNL Live Search] non genera più un errore se i criteri di ricerca contengono un valore di ordinamento vuoto
![Correzione](../assets/fix.svg) Il filtro dell&#39;intervallo non si interrompe più se i codici degli attributi contengono stringhe &quot;to&quot; o &quot;from&quot;

### [!DNL Live Search] 1.1.0 {#110}

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Bug](../assets/bug.svg) La [!DNL Live Search] il servizio supporta solo [valuta di base](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html) dell’installazione di Adobe Commerce.
![Bug](../assets/bug.svg) Quando si aggiunge un facet, il feed degli attributi del prodotto non viene aggiornato correttamente se è impostato su `Update on Save`. Per evitare questo problema, vai a [Gestione dell&#39;indice](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html) e imposta Feed attributi del prodotto su `Update by Schedule`.
![Bug](../assets/bug.svg) [!DNL Live Search] i sinonimi sono definiti per visualizzazione store, ma sono attualmente memorizzati per sito web e identificati con una combinazione di `environmentId` e `storeViewCode`. Di conseguenza, tutti i siti web e le viste store all’interno dell’installazione di Adobe Commerce condividono i sinonimi. Il set di sinonimi creato più di recente per la visualizzazione Store ha la precedenza.
![Bug](../assets/bug.svg) Se un termine sinonimo contiene più parole, ogni parola viene trattata come un sinonimo separato. Ad esempio, se definisci &quot;tempo&quot; come sinonimo di &quot;orologio&quot;, sia &quot;tempo&quot; che &quot;pezzo&quot; vengono trattati come sinonimi di orologio.

+++

## Documentazione

Per ulteriori informazioni:

* [Documentazione per gli sviluppatori di Adobe Commerce](https://developer.adobe.com/commerce/docs)
* [Guida utente di Adobe Commerce](https://experienceleague.adobe.com/docs/commerce.html)
* [[!DNL Live Search] su Marketplace](https://marketplace.magento.com/magento-live-search.html)
