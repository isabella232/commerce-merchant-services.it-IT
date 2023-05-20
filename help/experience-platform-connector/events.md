---
title: Eventi
description: Scopri i dati acquisiti da ogni evento.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
source-git-commit: ddacfc053f83be750c63ba376519169b38f7f478
workflow-type: tm+mt
source-wordcount: '4596'
ht-degree: 0%

---

# Eventi connettore Experience Platform

Di seguito è riportato un elenco degli eventi Commerce disponibili quando installi l’estensione del connettore Experience Platform. I dati raccolti da questi eventi vengono inviati a Adobe Experience Platform Edge. Puoi anche creare [eventi personalizzati](custom-events.md) per la raccolta di dati aggiuntivi non inclusi nella confezione.

Oltre ai dati raccolti dai seguenti eventi, otterrai anche [altri dati](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) fornite da Adobe Experience Platform Web SDK.

## Eventi vetrina

Gli eventi di vetrina raccolgono dati comportamentali anonimi dai tuoi acquirenti durante la navigazione sul tuo sito. I dati raccolti da questi eventi possono essere utilizzati per creare promozioni e campagne mirate a un gruppo specifico di acquirenti.

>[!NOTE]
>
>Tutti gli eventi della vetrina includono [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) , che include l&#39;indirizzo e-mail dell&#39;acquirente, se disponibile, ed ECID. Includendo questi dati di profilo in ogni evento, non è necessario un’importazione separata dell’account utente da Adobe Commerce.

### addToCart

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un prodotto viene aggiunto al carrello o quando la quantità di un prodotto nel carrello viene incrementata. | `commerce.productListAdds` |

#### Dati raccolti da addToCart

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productListAdds` | Indica se un prodotto è stato aggiunto a un carrello. Un valore di `1` indica che è stato aggiunto un prodotto. |
| `productListItems` | Un array di prodotti aggiunti al carrello |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `quantity` | Numero di unità prodotto aggiunte al carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta per il prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |
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
| `productListItems` | Un array di prodotti aggiunti al carrello |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `quantity` | Numero di unità prodotto aggiunte al carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta per il prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### removeFromCart

| Descrizione | Nome evento XDM |
|---|---|
| Viene attivato ogni volta che un prodotto viene rimosso o ogni volta che la quantità di un prodotto nel carrello diminuisce. | `commerce.productListRemovals` |

#### Dati raccolti da removeFromCart

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productListRemovals` | Indica se un prodotto è stato rimosso dal carrello. Un valore di `1` indica che un prodotto è stato rimosso dal carrello. |
| `productListItems` | Un array di prodotti rimossi dal carrello |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `quantity` | Numero di unità prodotto rimosse dal carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta per il prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### shoppingCartView

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione al caricamento di qualsiasi pagina del carrello. | `commerce.productListViews` |

#### Dati raccolti da shoppingCartView

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productListViews` | Indica se è stato visualizzato un elenco di prodotti |
| `productListItems` | Un array di prodotti nel carrello |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `quantity` | Numero di unità prodotto nel carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta per il prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### pageView

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione al caricamento di qualsiasi pagina. | `web.webpagedetails.pageViews` |

#### Dati raccolti da pageView

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `pageViews` | Indica se una pagina è stata caricata. A `value` di `1` indica che la pagina è stata caricata. |

### productPageView

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione al caricamento di qualsiasi pagina di prodotto. | `commerce.productViews` |

#### Dati raccolti da productPageView

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `productViews` | Indica se il prodotto è stato visualizzato |
| `productListItems` | Un array di prodotti nel carrello |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta per il prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |

### startCheckout

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando l&#39;acquirente fa clic su un pulsante di pagamento. | `commerce.checkouts` |

#### Dati raccolti da startCheckout

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `checkouts` | Indica se si è verificata un&#39;azione durante il processo di pagamento |
| `productListItems` | Un array di prodotti nel carrello |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `quantity` | Numero di unità prodotto nel carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta per il prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |
| `cartID` | ID univoco che identifica il carrello del cliente |

### completeCheckout

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando l’acquirente effettua un ordine. | `commerce.order` |

#### Dati raccolti da completeCheckout

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `purchases` | Indica se un ordine è stato accettato |
| `order` | Contiene informazioni sull’ordine effettuato per uno o più prodotti |
| `purchaseID` | Identificatore univoco assegnato dal venditore per questo acquisto o contratto. Non c&#39;è alcuna garanzia che l&#39;ID sia univoco. |
| `orderType` | Indica il tipo di ordine effettuato, ad esempio Pagamento o Acquisto immediato |
| `payments` | L&#39;elenco dei pagamenti per questo ordine |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento. Ad esempio: `USD` o `EUR`. |
| `paymentAmount` | Valore del pagamento |
| `paymentType` | Il metodo di pagamento per questo ordine. Le opzioni sono: `cash`, `credit_card`, `debit_card`, `gift_card`, `check`, `paypal`, `wire_transfer`, `credit_card_reference`, `other` |
| `transactionID` | L’identificatore univoco della transazione per questo elemento di pagamento |
| `shipping` | Dettagli di spedizione per uno o più prodotti. |
| `shippingMethod` | Il metodo di spedizione scelto dal cliente, ad esempio consegna standard, consegna rapida, ritiro in magazzino e così via |
| `shippingAmount` | Il costo totale di spedizione per gli articoli nel carrello |
| `promotionID` | Identificatore univoco della promozione, se presente |
| `personalEmail` | Specifica l&#39;indirizzo e-mail personale |
| `address` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `productListItems` | Un array di prodotti nel carrello |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `quantity` | Numero di unità prodotto nel carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per i totali dell’ordine. |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |

## Eventi profilo

Gli eventi profilo includono informazioni sull’account, ad esempio `signIn`, `signOut`, `createAccount`, e `editAccount`. Questi dati vengono utilizzati per popolare i dettagli chiave dei clienti necessari per definire meglio i segmenti o eseguire campagne di marketing, ad esempio se desideri eseguire il targeting degli acquirenti che vivono a New York.

### signIn

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di accedere. | `userAccount.login` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta di eseguire l’azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da signIn

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `person` | Un singolo attore, contatto o proprietario |
| `accountID` | Acquisisce l’ID dell’account utente |
| `accountType` | Acquisisce il tipo di account utente, ad esempio `Personal` o `Company`, se applicabile |
| `personalEmailID` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `personalEmail` | Acquisisce i dettagli di contatto: un’e-mail e le informazioni associate |
| `address` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `userAccount` | Indica eventuali dettagli di fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `login` | Indica se un visitatore ha tentato di accedere |

### disconnetti

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di uscire. | `userAccount.logout` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta di eseguire l’azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da signOut

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `userAccount` | Indica eventuali dettagli di fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `logout` | Indica se un visitatore ha tentato di disconnettersi |

### createAccount

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di creare un account. | `userAccount.createProfile` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta di eseguire l’azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da createAccount

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `person` | Un singolo attore, contatto o proprietario |
| `accountID` | Acquisisce l’ID dell’account utente |
| `accountType` | Acquisisce il tipo di account utente, ad esempio `Personal` o `Company`, se applicabile |
| `personalEmailID` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `personalEmail` | Acquisisce i dettagli di contatto: un’e-mail e le informazioni associate |
| `address` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `userAccount` | Indica eventuali dettagli di fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `createProfile` | Indica se un utente ha creato un profilo account |

### editAccount

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente tenta di modificare un account. | `userAccount.updateProfile` |

>[!NOTE]
>
> Questo evento viene attivato quando si tenta di eseguire l’azione specifica. Non indica che l’azione è stata eseguita correttamente.

#### Dati raccolti da editAccount

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `person` | Un singolo attore, contatto o proprietario |
| `accountID` | Acquisisce l’ID dell’account utente |
| `accountType` | Acquisisce il tipo di account utente, ad esempio `Personal` o `Company`, se applicabile |
| `personalEmailID` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `personalEmail` | Acquisisce i dettagli di contatto: un’e-mail e le informazioni associate |
| `address` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `userAccount` | Indica eventuali dettagli di fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `updateProfile` | Indica se un utente ha aggiornato il proprio profilo account |

## Cerca eventi

Gli eventi di ricerca forniscono dati rilevanti per l’intento dell’acquirente. L&#39;intuizione dell&#39;intento di un cliente aiuta i commercianti a capire come gli acquirenti stanno cercando gli articoli, cosa cliccano e, in ultima analisi, acquistano o abbandonano. Un esempio di come puoi utilizzare questi dati è se desideri eseguire il targeting degli acquirenti esistenti che cercano il tuo prodotto principale, ma non acquistano mai il prodotto.

Utilizza il `uniqueIdentifier` campo trovato in entrambi `searchRequestSent` e `searchResponseReceived` eventi per fare riferimento incrociato tra una richiesta di ricerca e la risposta di ricerca corrispondente.

### searchRequestSent

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione dai seguenti eventi nel popover &quot;cerca durante la digitazione&quot;:<br><br>Premi Invio, Fai Clic Su _Visualizza tutto_<br><br> Attivato dai seguenti eventi sulle pagine dei risultati di ricerca:<br><br>Selezionare un filtro, Modificare l&#39;ordinamento (_Ordina per_), Cambia la direzione di ordinamento (crescente o decrescente), Cambia il numero di risultati per pagina (_Mostra numero per pagina_), Passa alla pagina successiva, Passa alla pagina precedente, Passa a una pagina diversa | `searchRequest` |

>[!NOTE]
>
>Gli eventi di ricerca non sono supportati in Adobe Commerce Enterprise Edition con il modulo B2B installato.

#### Dati raccolti da searchRequestSent

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `searchRequest` | Indica se è stata inviata una richiesta di ricerca |
| `id` | ID univoco per questa particolare richiesta di ricerca |
| `filter` | Indica se sono stati applicati filtri per limitare i risultati di ricerca |
| `attribute` (filtro) | Facet di un elemento utilizzato per determinare se includerlo nei risultati di ricerca |
| `value` | Valori degli attributi utilizzati per determinare quali elementi sono inclusi nei risultati di ricerca |
| `isRange` | Se è true, i valori indicano gli endpoint di un intervallo di valori accettabile |
| `sort` | Indica come ordinare i risultati della ricerca |
| `attribute` (sort) | Attributo utilizzato per ordinare gli elementi nei risultati di ricerca |
| `order` | Ordine in cui restituire i risultati della ricerca |
| `query` | Termini cercati |

### searchResponseReceived

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando Live Search restituisce i risultati per la pagina dei risultati di ricerca o popover &quot;cerca durante la digitazione&quot;. | `searchResponse` |

>[!NOTE]
>
>Gli eventi di ricerca non sono supportati in Adobe Commerce Enterprise Edition con il modulo B2B installato.

#### Dati raccolti da searchResponseReceived

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `searchResponse` | Indica se è stata ricevuta una risposta di ricerca |
| `id` | ID univoco per questa particolare risposta di ricerca |
| `suggestions` | Matrice di stringhe che includono i nomi di prodotti e categorie presenti nel catalogo simili alla query di ricerca |
| `numberOfResults` | Numero di prodotti restituiti |
| `productListItems` | Un array di prodotti nel carrello. |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |

## Eventi B2B

![B2B per Adobe Commerce](../assets/b2b.svg) Per gli esercenti B2B, devi [installare](install.md#install-the-b2b-extension) il `experience-platform-connector-b2b` per abilitare questi eventi.

Gli eventi B2B contengono [elenco richieste di acquisto](https://experienceleague.adobe.com/docs/commerce-admin/b2b/requisition-lists/requisition-lists.html) informazioni, ad esempio se è stato creato, aggiunto o eliminato un elenco di richieste di acquisto. Tenendo traccia degli eventi specifici degli elenchi di richieste di acquisto, è possibile vedere quali prodotti i clienti acquistano frequentemente e creare campagne basate su tali dati.

### createRichiesteList

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente crea un nuovo elenco di richieste. | `commerce.requisitionListOpens` |

#### Dati raccolti da createRichiesteList

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `requisitionList` | Proprietà dell&#39;elenco di richieste di acquisto creato dal cliente |
| `ID` | Identificatore univoco dell&#39;elenco di richieste di acquisto |
| `name` | Nome dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `description` | Descrizione dell&#39;elenco di richieste di acquisto specificato dal cliente |

### addToRichiesteList

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente aggiunge un prodotto a un elenco di richieste esistente o durante la creazione di un nuovo elenco. | `commerce.requisitionListAdds` |

>[!NOTE]
>
>`addToRequisitionList` non è supportato nelle pagine di visualizzazione per categoria o per i prodotti configurabili. È supportato nelle pagine di visualizzazione del prodotto e per i prodotti semplici.

#### Dati raccolti da addToRichiitionList

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `requisitionList` | Proprietà dell&#39;elenco di richieste di acquisto creato dal cliente |
| `ID` | Identificatore univoco dell&#39;elenco di richieste di acquisto |
| `name` | Nome dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `description` | Descrizione dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `productListItems` | Array di prodotti aggiunti all&#39;elenco delle richieste di acquisto |
| `name` | Nome visualizzato o leggibile del prodotto |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `quantity` | Numero di unità di prodotto aggiunte |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |

### removeFromRichiesteList

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente rimuove un prodotto da un elenco di richieste di acquisto. | `commerce.requisitionListRemovals` |

#### Dati raccolti da removeFromRichiitionList

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `requisitionList` | Proprietà dell&#39;elenco di richieste di acquisto creato dal cliente |
| `ID` | Identificatore univoco dell&#39;elenco di richieste di acquisto |
| `name` | Nome dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `description` | Descrizione dell&#39;elenco di richieste di acquisto specificato dal cliente |
| `productListItems` | Array di prodotti aggiunti all&#39;elenco delle richieste di acquisto |
| `name` | Nome visualizzato o leggibile del prodotto |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `quantity` | Numero di unità di prodotto aggiunte |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell’attributo come `small` o `black`. |

## Eventi back office

Gli eventi di back office contengono informazioni sullo stato di un ordine, ad esempio se un ordine è stato effettuato, annullato, rimborsato, spedito o completato. I dati raccolti da questi eventi lato server mostrano una visualizzazione 360 dell’ordine cliente. Questa visualizzazione consente ai commercianti di eseguire meglio il targeting o analizzare l’intero stato dell’ordine durante lo sviluppo di campagne di marketing. Ad esempio, puoi individuare le tendenze in determinate categorie di prodotti che ottengono risultati ottimali in momenti diversi dell’anno. Ad esempio, vestiti invernali che vendono meglio durante i mesi più freddi o alcuni colori di prodotto che gli acquirenti sono interessati negli anni. Inoltre, i dati sullo stato dell&#39;ordine possono essere utili per calcolare il valore del cliente per tutta la sua durata comprendendo la propensione di un acquirente a eseguire la conversione in base agli ordini precedenti.

>[!NOTE]
>
>Tutti gli eventi di back office includono [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) , che fornisce l&#39;indirizzo e-mail dell&#39;acquirente. Includendo questi dati di profilo in ogni evento, non è necessario un’importazione separata dell’account utente da Adobe Commerce.

### orderPlaced

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente effettua un ordine. | `commerce.backofficeOrderPlaced` |

#### Dati raccolti da orderPlaced

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `address` | L’indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi |
| `productListItems` | Un array di prodotti nell’ordine |
| `id` | L’identificatore di riga per questa voce di prodotto. Il prodotto stesso è identificato tramite `product` campo. |
| `name` | Nome visualizzato o leggibile del prodotto |
| `SKU` | Unità di stoccaggio. L’identificatore univoco del prodotto. |
| `quantity` | Numero di unità prodotto nel carrello |
| `priceTotal` | Prezzo totale per la riga prodotto |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `order` | Contiene informazioni sull’ordine |
| `purchaseID` | Identificatore univoco assegnato dal venditore per questo acquisto o contratto. Non c&#39;è garanzia che l&#39;ID sia univoco |
| `priceTotal` | Il prezzo totale di questo ordine dopo l&#39;applicazione di tutti gli sconti e le imposte |
| `currencyCode` | Il codice valuta ISO 4217 utilizzato per i totali dell’ordine |
| `purchaseOrderNumber` | Identificatore univoco assegnato dall’acquirente a questo acquisto o contratto |
| `payments` | L&#39;elenco dei pagamenti per questo ordine |
| `paymentType` | Il metodo di pagamento per questo ordine. Valori enumerati e personalizzati consentiti. |
| `currencyCode` | Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento |
| `paymentAmount` | Valore del pagamento |
| `taxAmount` | Importo dell&#39;imposta pagato dall&#39;acquirente come parte del pagamento finale |
| `createdDate` | L’ora e la data di creazione di un nuovo ordine nel sistema commerce. Ad esempio: `2022-10-15T20:20:39+00:00` |
| `shipping` | Dettagli di spedizione per uno o più prodotti |
| `shippingMethod` | Il metodo di spedizione scelto dal cliente, ad esempio consegna standard, consegna rapida, ritiro in magazzino e così via |
| `shippingAmount` | L&#39;importo che il cliente ha dovuto pagare per la spedizione. |
| `address` | Indirizzo di spedizione fisico |
| `street1` | Informazioni stradali primarie, numero di appartamento, numero civico e nome della strada |
| `street2` | Campo aggiuntivo per informazioni a livello stradale |
| `city` | Il nome della città |
| `state` | Nome dello stato. Questo è un campo in formato libero. |
| `postalCode` | Il codice postale della località. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi, questa conterrà solo una parte del codice postale. |
| `country` | Il nome del territorio amministrato dal governo. Diverso da `xdm:countryCode`, questo è un campo in formato libero che può contenere il nome del paese in qualsiasi lingua. |
| `billingAddress` | Indirizzo postale di fatturazione |
| `street1` | Informazioni stradali primarie, numero di appartamento, numero civico e nome della strada |
| `street2` | Campo aggiuntivo per informazioni a livello stradale |
| `city` | Il nome della città |
| `state` | Nome dello stato. Questo è un campo in formato libero. |
| `postalCode` | Il codice postale della località. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi, questa conterrà solo una parte del codice postale. |
| `country` | Il nome del territorio amministrato dal governo. Diverso da `xdm:countryCode`, questo è un campo in formato libero che può contenere il nome del paese in qualsiasi lingua. |
| `personalEmail` | Un indirizzo e-mail personale |
| `address` | L’indirizzo tecnico, ad esempio &quot;name@domain.com&quot;, come comunemente definito in RFC2822 e standard successivi |

### orderItemsShipped

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando viene spedito un ordine. | `commerce.backofficeOrderItemsShipped` |

#### Dati raccolti da orderItemsShipped

Nella tabella seguente sono descritti i dati raccolti per questo evento.
Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi| |`productListItems`|Un array di prodotti nell’ordine| |`id`|L’identificatore di riga per questa voce di prodotto. Il prodotto stesso è identificato tramite `product` campo.| |`name`|Nome visualizzato o leggibile del prodotto| |`SKU`|Unità di gestione delle scorte. L’identificatore univoco del prodotto.| |`quantity`|Numero di unità di prodotto nel carrello| |`priceTotal`|Il prezzo totale per la voce di prodotto| |`discountAmount`|Indica l&#39;importo dello sconto applicato| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore a questo acquisto o contratto. Non c&#39;è garanzia che l&#39;ID sia univoco| |`priceTotal`|Il prezzo totale dell&#39;ordine dopo l&#39;applicazione di tutti gli sconti e le tasse| |`currencyCode`|Il codice valuta ISO 4217 utilizzato per i totali dell’ordine| |`purchaseOrderNumber`|Identificatore univoco assegnato dall’acquirente a questo acquisto o contratto| |`payments`|L’elenco dei pagamenti per questo ordine| |`paymentType`|Il metodo di pagamento per questo ordine. Valori enumerati e personalizzati consentiti.| |`currencyCode`|Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento| |`paymentAmount`|Valore del pagamento| |`lastUpdatedDate`|L’ora dell’ultimo aggiornamento di un particolare record dell’ordine nel sistema commerciale| |`shipping`|Dettagli di spedizione per uno o più prodotti| |`shippingMethod`|Il metodo di spedizione scelto dal cliente, ad esempio consegna standard, consegna rapida, ritiro in magazzino e così via| |`trackingNumber`|Il numero di registrazione fornito dal vettore di spedizione per una spedizione dell&#39;articolo dell&#39;ordine| |`trackingURL`|L&#39;URL per tenere traccia dello stato di spedizione di un ordine| |`shipDate`|Data di spedizione di uno o più articoli di un ordine| |`address`|Indirizzo fisico di spedizione| |`street1`|Informazioni stradali primarie, numero di appartamento, numero civico e nome della strada| |`street2`|Campo aggiuntivo per informazioni a livello stradale| |`city`|Il nome della città| |`state`|Il nome dello Stato. Questo è un campo in formato libero.| |`postalCode`|Il codice postale della località. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi, questa conterrà solo una parte del codice postale.| |`country`|Il nome del territorio amministrato dal governo. Diverso da `xdm:countryCode`, questo è un campo in formato libero che può contenere il nome del paese in qualsiasi lingua.| |`shippingAmount`|L&#39;importo che il cliente ha dovuto pagare per la spedizione.| |`billingAddress`|Indirizzo postale di fatturazione| |`street1`|Informazioni stradali primarie, numero di appartamento, numero civico e nome della strada| |`street2`|Campo aggiuntivo per informazioni a livello stradale| |`city`|Il nome della città| |`state`|Il nome dello Stato. Questo è un campo in formato libero.| |`postalCode`|Il codice postale della località. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi, questa conterrà solo una parte del codice postale.| |`country`|Il nome del territorio amministrato dal governo. Diverso da `xdm:countryCode`, questo è un campo in formato libero che può contenere il nome del paese in qualsiasi lingua.| |`personalEmail`|Un indirizzo e-mail personale| |`address`|L’indirizzo tecnico, ad esempio &quot;name@domain.com&quot;, come comunemente definito nella RFC2822 e nelle norme successive|

### orderCanceled

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente annulla un ordine. | `commerce.backofficeOrderCancelled` |

#### Dati raccolti da orderCanceled

Nella tabella seguente sono descritti i dati raccolti per questo evento.
Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi| |`productListItems`|Un array di prodotti nell’ordine| |`id`|L’identificatore di riga per questa voce di prodotto. Il prodotto stesso è identificato tramite `product` campo.| |`name`|Nome visualizzato o leggibile del prodotto| |`SKU`|Unità di gestione delle scorte. L’identificatore univoco del prodotto.| |`quantity`|Numero di unità di prodotto nel carrello| |`priceTotal`|Il prezzo totale per la voce di prodotto| |`discountAmount`|Indica l&#39;importo dello sconto applicato| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore a questo acquisto o contratto. Non c&#39;è garanzia che l&#39;ID sia univoco| |`purchaseOrderNumber`|Identificatore univoco assegnato dall’acquirente a questo acquisto o contratto| |`cancelDate`|Data e ora in cui un acquirente annulla un ordine| |`lastUpdatedDate`|L’ora dell’ultimo aggiornamento di un particolare record dell’ordine nel sistema commerciale| |`personalEmail`|Un indirizzo e-mail personale| |`address`|L’indirizzo tecnico, ad esempio &quot;name@domain.com&quot;, come comunemente definito nella RFC2822 e nelle norme successive|

### creditMemoIssued

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente restituisce un articolo in un ordine. | `commerce.backofficeCreditMemoIssued` |

#### Dati raccolti da creditMemoIssued

Nella tabella seguente sono descritti i dati raccolti per questo evento.
Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi| |`productListItems`|Un array di prodotti nell’ordine| |`id`|L’identificatore di riga per questa voce di prodotto. Il prodotto stesso è identificato tramite `product` campo.| |`name`|Nome visualizzato o leggibile del prodotto| |`SKU`|Unità di gestione delle scorte. L’identificatore univoco del prodotto.| |`quantity`|Numero di unità di prodotto nel carrello| |`priceTotal`|Il prezzo totale per la voce di prodotto| |`discountAmount`|Indica l&#39;importo dello sconto applicato| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore a questo acquisto o contratto. Non c&#39;è garanzia che l&#39;ID sia univoco| |`purchaseOrderNumber`|Identificatore univoco assegnato dall’acquirente a questo acquisto o contratto| |`lastUpdatedDate`|L’ora dell’ultimo aggiornamento di un particolare record dell’ordine nel sistema commerciale| |`personalEmail`|Un indirizzo e-mail personale| |`address`|L’indirizzo tecnico, ad esempio &quot;name@domain.com&quot;, come comunemente definito nella RFC2822 e nelle norme successive|

### orderShipmentCompleted

| Descrizione | Nome evento XDM |
|---|---|
| Attivazione quando un acquirente restituisce un articolo in un ordine. | `commerce.backofficeOrderShipmentCompleted` |

#### Dati raccolti da orderShipmentCompleted

Nella tabella seguente sono descritti i dati raccolti per questo evento.
Campo|Descrizione| |—|—| |`address`|L&#39;indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi| |`productListItems`|Un array di prodotti nell’ordine| |`id`|L’identificatore di riga per questa voce di prodotto. Il prodotto stesso è identificato tramite `product` campo.| |`name`|Nome visualizzato o leggibile del prodotto| |`SKU`|Unità di gestione delle scorte. L’identificatore univoco del prodotto.| |`quantity`|Numero di unità di prodotto nel carrello| |`priceTotal`|Il prezzo totale per la voce di prodotto| |`discountAmount`|Indica l&#39;importo dello sconto applicato| |`order`|Contiene informazioni sull&#39;ordine| |`purchaseID`|Identificatore univoco assegnato dal venditore a questo acquisto o contratto. Non c&#39;è garanzia che l&#39;ID sia univoco| |`priceTotal`|Il prezzo totale dell&#39;ordine dopo l&#39;applicazione di tutti gli sconti e le tasse| |`currencyCode`|Il codice valuta ISO 4217 utilizzato per i totali dell’ordine| |`purchaseOrderNumber`|Identificatore univoco assegnato dall’acquirente a questo acquisto o contratto| |`taxAmount`|Importo dell&#39;imposta pagata dall&#39;acquirente nel quadro del pagamento finale.| |`createdDate`|L’ora e la data di creazione di un nuovo ordine nel sistema commerciale. Ad esempio: `2022-10-15T20:20:39+00:00`| |`payments`|L’elenco dei pagamenti per questo ordine| |`paymentType`|Il metodo di pagamento per questo ordine. Valori enumerati e personalizzati consentiti.| |`currencyCode`|Il [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per questo elemento di pagamento| |`paymentAmount`|Valore del pagamento| |`shipping`|Dettagli di spedizione per uno o più prodotti| |`shippingMethod`|Il metodo di spedizione scelto dal cliente, ad esempio consegna standard, consegna rapida, ritiro in magazzino e così via| |`address`|Indirizzo fisico di spedizione| |`street1`|Informazioni stradali primarie, numero di appartamento, numero civico e nome della strada| |`street2`|Campo aggiuntivo per informazioni a livello stradale| |`city`|Il nome della città| |`state`|Il nome dello Stato. Questo è un campo in formato libero.| |`postalCode`|Il codice postale della località. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi, questa conterrà solo una parte del codice postale.| |`country`|Il nome del territorio amministrato dal governo. Diverso da `xdm:countryCode`, questo è un campo in formato libero che può contenere il nome del paese in qualsiasi lingua.| |`shippingAmount`|L&#39;importo che il cliente ha dovuto pagare per la spedizione.| |`address`|L&#39;indirizzo tecnico, ad esempio: `name@domain.com` come comunemente definito in RFC2822 e standard successivi| |`billingAddress`|Indirizzo postale di fatturazione| |`street1`|Informazioni stradali primarie, numero di appartamento, numero civico e nome della strada| |`street2`|Campo aggiuntivo per informazioni a livello stradale| |`city`|Il nome della città| |`state`|Il nome dello Stato. Questo è un campo in formato libero.| |`postalCode`|Il codice postale della località. I codici postali non sono disponibili per tutti i paesi. In alcuni paesi, questi dati contengono solo una parte del codice postale.| |`country`|Il nome del territorio amministrato dal governo. Diverso da `xdm:countryCode`, questo è un campo in formato libero che può contenere il nome del paese in qualsiasi lingua.| |`personalEmail`|Un indirizzo e-mail personale| |`address`|L’indirizzo tecnico, ad esempio &quot;name@domain.com&quot;, come comunemente definito nella RFC2822 e nelle norme successive|
