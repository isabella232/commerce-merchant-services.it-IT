---
title: Eventi
description: Scopri quali dati acquisisce ogni evento.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
source-git-commit: 8e5fb65363b2fa39f44da86d7ba0cc5459b18768
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Eventi del connettore Experience Platform

Di seguito sono elencati gli eventi Commerce disponibili quando installi l’estensione del connettore Experience Platform. I dati raccolti da questi eventi vengono inviati al server Edge di Adobe Experience Platform. Puoi anche creare [eventi personalizzati](custom-events.md) raccogliere dati aggiuntivi non forniti al momento.

Oltre ai dati raccolti dai seguenti eventi, ottieni anche [altri dati](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) fornito dall’SDK Web di Adobe Experience Platform.

## Eventi Storefront

Gli eventi di vetrina raccolgono dati comportamentali anonimi dai tuoi acquirenti mentre navigano sul tuo sito. I dati raccolti da questi eventi possono essere utilizzati per creare promozioni e campagne mirate a un set specifico di acquirenti.

>[!NOTE]
>
>Tutti gli eventi della vetrina includono [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) , che include l&#39;indirizzo e-mail dell&#39;acquirente, se disponibile, e ECID. Includendo questi dati di profilo in ogni evento, non è necessaria un’importazione separata di account utente da Adobe Commerce.

### addToCart

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un prodotto viene aggiunto al carrello o quando la quantità di un prodotto nel carrello viene incrementata. | `commerce.productListAdds` |

#### Dati raccolti da addToCart

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productListAdds` | Indica se un prodotto è stato aggiunto a un carrello. Un valore di `1` indica che è stato aggiunto un prodotto. |
| `productListItems` | Una serie di prodotti aggiunti al carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `quantity` | Numero di unità di prodotto aggiunte al carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### openCart

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando viene creato un nuovo carrello, ovvero quando un prodotto viene aggiunto a un carrello vuoto. | `commerce.productListOpens` |

#### Dati raccolti da openCart

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productListOpens` | Indica se è stato creato un carrello. Un valore di `1` indica che è stato creato un carrello. |
| `productListItems` | Una serie di prodotti aggiunti al carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `quantity` | Numero di unità di prodotto aggiunte al carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### removeFromCart

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione ogni volta che un prodotto viene rimosso o ogni volta che la quantità di un prodotto nel carrello viene diminuita. | `commerce.productListRemovals` |

#### Dati raccolti da removeFromCart

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productListRemovals` | Indica se un prodotto è stato rimosso dal carrello. Un valore di `1` indica che un prodotto è stato rimosso dal carrello. |
| `productListItems` | Una serie di prodotti rimossi dal carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `quantity` | Numero di unità di prodotto rimosse dal carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### shoppingCartView

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando viene caricata una pagina del carrello. | `commerce.productListViews` |

#### Dati raccolti da shoppingCartView

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productListViews` | Indica se è stato visualizzato un elenco di prodotti |
| `productListItems` | Una serie di prodotti nel carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `quantity` | Numero di unità di prodotto nel carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### pageView

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione al caricamento di qualsiasi pagina. | `web.webpagedetails.pageViews` |

#### Dati raccolti da pageView

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `pageViews` | Indica se è stata caricata una pagina. A `value` di `1` indica che la pagina è stata caricata. |

### productPageView

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione al caricamento di qualsiasi pagina di prodotto. | `commerce.productViews` |

#### Dati raccolti da productPageView

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productViews` | Indica se il prodotto è stato visualizzato |
| `productListItems` | Una serie di prodotti nel carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |

### startCheckout

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando l&#39;acquirente fa clic su un pulsante di pagamento. | `commerce.checkouts` |

#### Dati raccolti da startCheckout

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `checkouts` | Indica se si è verificata un&#39;azione durante il processo di pagamento |
| `productListItems` | Una serie di prodotti nel carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `quantity` | Numero di unità di prodotto nel carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### completeCheckout

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando l&#39;acquirente effettua un ordine. | `commerce.order` |

#### Dati raccolti da completeCheckout

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `purchases` | Indica se un ordine è stato accettato |
| `order` | Contiene informazioni sull&#39;ordine inserito per uno o più prodotti |
| `purchaseID` | Identificatore univoco assegnato dal venditore per l&#39;acquisto o il contratto. Non c&#39;è garanzia che l&#39;ID sia univoco. |
| `orderType` | Indica il tipo di ordine inserito, ad esempio Pagamento o Acquisto istantaneo |
| `payments` | Elenco dei pagamenti per l&#39;ordine |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento. Ad esempio: `USD` o `EUR`. |
| `paymentAmount` | Valore del pagamento |
| `paymentType` | Modalità di pagamento dell&#39;ordine. Le opzioni sono: `cash`, `credit_card`, `debit_card`, `gift_card`, `check`, `paypal`, `wire_transfer`, `credit_card_reference`, `other` |
| `transactionID` | Identificatore univoco della transazione per l&#39;elemento di pagamento |
| `shipping` | Dettagli di spedizione per uno o più prodotti. |
| `shippingMethod` | Il metodo di spedizione scelto dal cliente, ad esempio consegna standard, consegna rapida, ritiro in negozio e così via |
| `shippingAmount` | Costo totale di spedizione per gli articoli nel carrello |
| `promotionID` | Identificatore univoco della promozione, se presente |
| `personalEmail` | Specifica l&#39;indirizzo e-mail personale |
| `address` | L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi |
| `productListItems` | Una serie di prodotti nel carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `quantity` | Numero di unità di prodotto nel carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per i totali dell&#39;ordine. |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |

## Eventi di profilo

Gli eventi di profilo includono informazioni sull’account, ad esempio `signIn`, `signOut`, `createAccount`e `editAccount`. Questi dati vengono utilizzati per popolare i dettagli chiave dei clienti necessari per definire meglio i segmenti o eseguire campagne di marketing, ad esempio per indirizzare gli acquirenti che vivono a New York.

### signIn

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di accedere. | `userAccount.login` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da signIn

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `eventType` | Il tipo di evento principale per questo record della serie temporale, ad esempio: `userAccount.login` |
| `person` | Un singolo attore, contatto o proprietario |
| `accountID` | Acquisisce l’ID dell’account utente |
| `personalEmailID` | Specifica l’identificatore univoco dell’e-mail personale. |
| `address` | L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi |
| `userAccount` | Indica eventuali dettagli fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `login` | Indica se un visitatore ha tentato l&#39;accesso |

### signOut

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di disconnettersi. | `userAccount.logout` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da signOut

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `eventType` | Il tipo di evento principale per questo record della serie temporale, ad esempio: `userAccount.logout` |
| `userAccount` | Indica eventuali dettagli fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `logout` | Indica se un visitatore ha tentato di disconnettersi |

### createAccount

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di creare un account. | `userAccount.createProfile` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da createAccount

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `eventType` | Il tipo di evento principale per questo record della serie temporale, ad esempio: `account.createProfile` |
| `person` | Un singolo attore, contatto o proprietario |
| `accountID` | Acquisisce l’ID dell’account utente |
| `accountType` | Acquisisce il tipo di account utente, ad esempio `Personal` o `Company`se del caso |
| `personalEmailID` | Specifica l’identificatore univoco dell’e-mail personale. |
| `address` | L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi |
| `userAccount` | Indica eventuali dettagli fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `createProfile` | Indica se un utente ha creato un profilo di account |

### editAccount

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di modificare un account. | `userAccount.updateProfile` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da editAccount

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `eventType` | Il tipo di evento principale per questo record della serie temporale, ad esempio: `account.updateProfile` |
| `person` | Un singolo attore, contatto o proprietario |
| `accountID` | Acquisisce l’ID dell’account utente |
| `accountType` | Acquisisce il tipo di account utente, ad esempio `Personal` o `Company`se del caso |
| `personalEmailID` | Specifica l’identificatore univoco dell’e-mail personale. |
| `personalEmail` | Specifica l&#39;indirizzo e-mail personale |
| `address` | L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi |
| `userAccount` | Indica eventuali dettagli fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `updateProfile` | Indica se un utente ha aggiornato il proprio profilo account |

## Eventi di ricerca

Gli eventi di ricerca forniscono dati pertinenti all’intento dell’acquirente. Approfondisci l&#39;intento di un acquirente che aiuta i commercianti a vedere come i consumatori cercano gli articoli, cosa cliccano e alla fine acquistano o abbandonano. Un esempio di come utilizzare questi dati è se desideri indirizzare gli acquirenti esistenti che cercano il tuo prodotto principale, ma non acquistano mai il prodotto.

Utilizza la `uniqueIdentifier` campo trovato in entrambi i `searchRequestSent` e `searchResponseReceived` eventi per fare riferimento incrociato una richiesta di ricerca con la risposta di ricerca corrispondente.

### searchRequestSent

| Descrizione | Nome evento XDM |
|---|---|
| Attivato dai seguenti eventi nel puntatore &quot;cerca come digiti&quot;:<br><br>Premi Invio, Fai Clic Su _Visualizza tutto_<br><br> Attivazione dai seguenti eventi nelle pagine dei risultati di ricerca:<br><br>Seleziona un filtro, Cambia l’ordinamento (_Ordina per_), Cambia l&#39;ordinamento (crescente o decrescente), Cambia il numero di risultati per pagina (_Mostra n. per pagina_), passare alla pagina successiva, passare alla pagina precedente e passare a una pagina diversa | `searchRequest` |

>[!NOTE]
>
>Gli eventi di ricerca non sono supportati in Adobe Commerce Enterprise Edition con il modulo B2B installato.

#### Dati raccolti da searchRequestSent

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `searchRequest` | Indica se è stata inviata una richiesta di ricerca |
| `id` | ID univoco per questa particolare richiesta di ricerca |
| `filter` | Indica se sono stati applicati filtri per limitare i risultati della ricerca |
| `attribute` (filtro) | Facet di un elemento utilizzato per determinare se includerlo nei risultati della ricerca |
| `value` | Valori degli attributi utilizzati per determinare quali elementi sono inclusi nei risultati di ricerca |
| `isRange` | Se true, i valori indicano gli endpoint di un intervallo di valori accettabile |
| `sort` | Indica come ordinare i risultati della ricerca |
| `attribute` (ordinamento) | Attributo utilizzato per ordinare gli elementi nei risultati di ricerca |
| `order` | Ordine in cui restituire i risultati della ricerca |
| `query` | Termini cercati |

### searchResponseReceived

| Descrizione | Nome evento XDM |
|---|---|
| Attivato quando Live Search restituisce i risultati per la pagina &quot;search as you type&quot; o risultati di ricerca. | `searchResponse` |

>[!NOTE]
>
>Gli eventi di ricerca non sono supportati in Adobe Commerce Enterprise Edition con il modulo B2B installato.

#### Dati raccolti da searchResponseReceived

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `searchResponse` | Indica se è stata ricevuta una risposta di ricerca |
| `id` | ID univoco per questa particolare risposta di ricerca |
| `suggestions` | Matrice di stringhe che includono i nomi dei prodotti e delle categorie presenti nel catalogo simili alla query di ricerca |
| `numberOfResults` | Numero di prodotti restituiti |
| `productListItems` | Una serie di prodotti nel carrello. |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |

## Eventi B2B

![B2B per Adobe Commerce](../assets/b2b.svg) Per i commercianti B2B, devi [installare](install.md#install-the-b2b-extension) la `experience-platform-connector-b2b` per abilitare questi eventi.

Gli eventi B2B contengono [elenco richieste](https://experienceleague.adobe.com/docs/commerce-admin/b2b/requisition-lists/requisition-lists.html) informazioni, ad esempio se un elenco di richieste di acquisto è stato creato, aggiunto o eliminato da. Tracciando gli eventi specifici degli elenchi di richieste di acquisto, puoi vedere quali prodotti i clienti acquistano frequentemente e creare campagne in base a tali dati.

### createRequestList

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente crea un nuovo elenco di richieste di acquisto. | `commerce.requisitionListOpens` |

#### Dati raccolti da createRequestList

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `requisitionList` | Proprietà dell&#39;elenco delle richieste di acquisto creato dal cliente |
| `ID` | Identificatore univoco dell&#39;elenco richieste di acquisto |
| `name` | Nome dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `description` | Descrizione dell&#39;elenco di richieste di acquisto specificato dal cliente |

### addToRichiesteList

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente aggiunge un prodotto a un elenco di richieste esistente o durante la creazione di un nuovo elenco. | `commerce.requisitionListAdds` |

>[!NOTE]
>
>`addToRequisitionList` non è supportato nelle pagine di visualizzazione categoria o per i prodotti configurabili. È supportato nelle pagine di visualizzazione dei prodotti e per i prodotti semplici.

#### Dati raccolti da addToRequestList

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `requisitionList` | Proprietà dell&#39;elenco delle richieste di acquisto creato dal cliente |
| `ID` | Identificatore univoco dell&#39;elenco richieste di acquisto |
| `name` | Nome dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `description` | Descrizione dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `productListItems` | Matrice di prodotti aggiunti all&#39;elenco delle richieste di acquisto |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `quantity` | Numero di unità di prodotto aggiunte |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |

### removeFromRequestList

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente rimuove un prodotto da un elenco di richieste di acquisto. | `commerce.requisitionListRemovals` |

#### Dati raccolti da removeFromRequestList

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `requisitionList` | Proprietà dell&#39;elenco delle richieste di acquisto creato dal cliente |
| `ID` | Identificatore univoco dell&#39;elenco richieste di acquisto |
| `name` | Nome dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `description` | Descrizione dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `productListItems` | Matrice di prodotti aggiunti all&#39;elenco delle richieste di acquisto |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `quantity` | Numero di unità di prodotto aggiunte |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |

## Eventi back office

Gli eventi back office contengono informazioni sullo stato di un ordine, ad esempio se un ordine è stato effettuato, annullato, rimborsato, spedito o completato. I dati raccolti da questi eventi lato server mostrano una visualizzazione 360 dell&#39;ordine dell&#39;acquirente. Questa visualizzazione consente ai commercianti di eseguire meglio il targeting o di analizzare l’intero stato dell’ordine durante lo sviluppo di campagne di marketing. Ad esempio, è possibile individuare le tendenze in alcune categorie di prodotti che presentano buone prestazioni in diversi momenti dell’anno. Ad esempio, vestiti invernali che vendono meglio durante i mesi più freddi o alcuni colori di prodotto che i consumatori sono interessati nel corso degli anni. Inoltre, i dati sullo stato dell&#39;ordine possono essere utili per calcolare il valore del cliente a vita, comprendendo la propensione di un acquirente alla conversione in base agli ordini precedenti.

>[!NOTE]
>
>Tutti gli eventi back office includono [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) , che fornisce l’indirizzo e-mail dell’acquirente. Includendo questi dati di profilo in ogni evento, non è necessaria un’importazione separata di account utente da Adobe Commerce.

### orderPlaced

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente effettua un ordine. | `commerce.backofficeOrderPlaced` |

#### Dati raccolti da orderPlaced

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `address` | L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi |
| `eventType` | `commerce.backofficeOrderPlaced` |
| `productListItems` | Un array di prodotti nell&#39;ordine |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `quantity` | Numero di unità di prodotto nel carrello |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `order` | Contiene informazioni sull&#39;ordine |
| `purchaseID` | Identificatore univoco assegnato dal venditore per l&#39;acquisto o il contratto. Non c&#39;è garanzia che l&#39;ID sia univoco |
| `purchaseOrderNumber` | Identificatore univoco assegnato dall&#39;acquirente per l&#39;acquisto o il contratto |
| `payments` | Elenco dei pagamenti per l&#39;ordine |
| `paymentType` | Modalità di pagamento dell&#39;ordine. Valori enumerati personalizzati consentiti. |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento |
| `paymentAmount` | Valore del pagamento |
| `taxAmount` | Importo dell&#39;imposta versato dall&#39;acquirente nel quadro del pagamento finale |
| `createdDate` | L&#39;ora e la data in cui viene creato un nuovo ordine nel sistema commerce. Ad esempio: `2022-10-15T20:20:39+00:00` |
| `shipping` | Dettagli di spedizione per uno o più prodotti |
| `shippingMethod` | Il metodo di spedizione scelto dal cliente, ad esempio consegna standard, consegna rapida, ritiro in negozio e così via |
| `shippingAddress` | Indirizzo spedizione fisica |
| `street1` | Informazioni principali sul livello della strada, numero dell&#39;appartamento, numero della strada e nome della strada |
| `shippingAmount` | Importo che il cliente ha dovuto pagare per la spedizione. |
| `billingAddress` | Indirizzo postale di fatturazione |
| `street1` | Informazioni principali sul livello della strada, numero dell&#39;appartamento, numero della strada e nome della strada |
| `street2` | Campo aggiuntivo per informazioni a livello stradale |
| `city` | Nome della città |
| `state` | Nome dello stato. Questo è un campo in formato libero. |
| `postalCode` | Codice postale della posizione. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi ciò conterrà solo una parte del codice postale. |
| `country` | Nome del territorio amministrato dal governo. Diversi da `xdm:countryCode`, è un campo in formato libero che può avere il nome del paese in qualsiasi lingua. |

### orderItemsShipped

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando viene spedito un ordine. | `commerce.backofficeOrderItemsShipped` |

#### Dati raccolti da orderItemsShipped

Nella tabella seguente sono descritti i dati raccolti per questo evento.
|Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi| |`eventType`|`commerce.backofficeOrderItemsShipped`| |`productListItems`|Matrice di prodotti nell&#39;ordine| |`name`|Nome visualizzato o nome leggibile del prodotto| |`SKU`|Unità di conservazione delle scorte. Identificatore univoco per il prodotto.| |`quantity`|Numero di unità di prodotto nel carrello| |`priceTotal`|Il prezzo totale per l&#39;articolo della linea di prodotti| |`discountAmount`|Indica l&#39;importo dello sconto applicato| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore per l&#39;acquisto o il contratto. Non esiste alcuna garanzia che l&#39;ID sia univoco| |`purchaseOrderNumber`|Identificatore univoco assegnato dall&#39;acquirente per l&#39;acquisto o il contratto| |`payments`|Elenco dei pagamenti per l&#39;ordine| |`paymentType`|Modalità di pagamento dell&#39;ordine. Valori enumerati personalizzati consentiti.| |`currencyCode`|Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento| |`paymentAmount`|Valore del pagamento| |`trackingNumber`|Numero di registrazione fornito dal vettore per una spedizione di un articolo d&#39;ordine| |`trackingURL`|L&#39;URL per tenere traccia dello stato di spedizione di un articolo dell&#39;ordine| |`lastUpdatedDate`|Data e ora dell&#39;ultimo aggiornamento di un determinato record dell&#39;ordine nel sistema commerce| |`shipping`|Dettagli di spedizione per uno o più prodotti| |`shippingMethod`|Il metodo di spedizione scelto dal cliente, ad esempio la consegna standard, la consegna rapida, il ritiro in negozio e così via| |`shippingAddress`|Indirizzo di spedizione fisica| |`street1`|Informazioni principali sul livello della strada, numero dell&#39;appartamento, numero della strada e nome della strada| |`shippingAmount`|Importo che il cliente ha dovuto pagare per la spedizione.| |`billingAddress`|Indirizzo postale di fatturazione| |`street1`|Informazioni principali sul livello della strada, numero dell&#39;appartamento, numero della strada e nome della strada| |`street2`|Campo aggiuntivo per informazioni a livello stradale| |`city`|Nome della città| |`state`|Nome dello stato. Questo è un campo in formato libero.| |`postalCode`|Il codice postale del luogo. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi ciò conterrà solo una parte del codice postale.| |`country`|Nome del territorio amministrato dal governo. Diversi da `xdm:countryCode`, è un campo a forma libera che può avere il nome del paese in qualsiasi lingua.|

### orderCancelled

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente annulla un ordine. | `commerce.backofficeOrderCancelled` |

#### Dati raccolti da orderCancelled

Nella tabella seguente sono descritti i dati raccolti per questo evento.
|Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi| |`eventType`|`commerce.backofficeOrderCancelled`| |`productListItems`|Matrice di prodotti nell&#39;ordine| |`name`|Nome visualizzato o nome leggibile del prodotto| |`SKU`|Unità di conservazione delle scorte. Identificatore univoco per il prodotto.| |`quantity`|Numero di unità di prodotto nel carrello| |`priceTotal`|Il prezzo totale per l&#39;articolo della linea di prodotti| |`discountAmount`|Indica l&#39;importo dello sconto applicato| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore per l&#39;acquisto o il contratto. Non esiste alcuna garanzia che l&#39;ID sia univoco| |`purchaseOrderNumber`|Identificatore univoco assegnato dall&#39;acquirente per l&#39;acquisto o il contratto| |`cancelDate`|La data e l&#39;ora in cui un acquirente annulla un ordine| |`lastUpdatedDate`|Data e ora dell&#39;ultimo aggiornamento di un determinato record dell&#39;ordine nel sistema commerce|

### creditMemoEmittenti

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente restituisce un elemento in un ordine. | `commerce.backofficeCreditMemoIssued` |

#### Dati raccolti da creditMemoIssues

Nella tabella seguente sono descritti i dati raccolti per questo evento.
|Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi| |`eventType`|`commerce.backofficeCreditMemoIssued`| |`productListItems`|Matrice di prodotti nell&#39;ordine| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore per l&#39;acquisto o il contratto. Non esiste alcuna garanzia che l&#39;ID sia univoco| |`purchaseOrderNumber`|Identificatore univoco assegnato dall&#39;acquirente per l&#39;acquisto o il contratto| |`lastUpdatedDate`|Data e ora dell&#39;ultimo aggiornamento di un determinato record dell&#39;ordine nel sistema commerce|

### orderShipmentCompleted

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente restituisce un elemento in un ordine. | `commerce.backofficeOrderShipmentCompleted` |

#### Dati raccolti da orderShipmentCompleted

Nella tabella seguente sono descritti i dati raccolti per questo evento.
|Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi| |`eventType`|`commerce.backofficeOrderShipmentCompleted`| |`productListItems`|Matrice di prodotti nell&#39;ordine| |`name`|Nome visualizzato o nome leggibile del prodotto| |`SKU`|Unità di conservazione delle scorte. Identificatore univoco per il prodotto.| |`quantity`|Numero di unità di prodotto nel carrello| |`priceTotal`|Il prezzo totale per l&#39;articolo della linea di prodotti| |`discountAmount`|Indica l&#39;importo dello sconto applicato| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore per l&#39;acquisto o il contratto. Non esiste alcuna garanzia che l&#39;ID sia univoco| |`purchaseOrderNumber`|Identificatore univoco assegnato dall&#39;acquirente per l&#39;acquisto o il contratto| |`taxAmount`|Importo dell&#39;imposta versato dall&#39;acquirente nel quadro del pagamento finale.| |`createdDate`|L&#39;ora e la data in cui viene creato un nuovo ordine nel sistema commerce. Ad esempio: `2022-10-15T20:20:39+00:00`| |`payments`|Elenco dei pagamenti per l&#39;ordine| |`paymentType`|Modalità di pagamento dell&#39;ordine. Valori enumerati personalizzati consentiti.| |`currencyCode`|Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento| |`paymentAmount`|Valore del pagamento| |`shipping`|Dettagli di spedizione per uno o più prodotti| |`shippingMethod`|Il metodo di spedizione scelto dal cliente, ad esempio la consegna standard, la consegna rapida, il ritiro in negozio e così via| |`shippingAddress`|Indirizzo di spedizione fisica| |`street1`|Informazioni principali sul livello della strada, numero dell&#39;appartamento, numero della strada e nome della strada| |`shippingAmount`|Importo che il cliente ha dovuto pagare per la spedizione.| |`personalEmail`|Specifica l&#39;indirizzo e-mail personale| |`address`|L&#39;indirizzo tecnico, ad esempio `name@domain.com` come comunemente definito nella RFC2822 e negli standard successivi| |`billingAddress`|Indirizzo postale di fatturazione| |`street1`|Informazioni principali sul livello della strada, numero dell&#39;appartamento, numero della strada e nome della strada| |`street2`|Campo aggiuntivo per informazioni a livello stradale| |`city`|Nome della città| |`state`|Nome dello stato. Questo è un campo in formato libero.| |`postalCode`|Il codice postale del luogo. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi questi dati contengono solo una parte del codice postale.| |`country`|Nome del territorio amministrato dal governo. Diversi da `xdm:countryCode`, è un campo a forma libera che può avere il nome del paese in qualsiasi lingua.|
