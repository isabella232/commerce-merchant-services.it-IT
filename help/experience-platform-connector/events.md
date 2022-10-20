---
title: Eventi
description: Scopri quali dati acquisisce ogni evento.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
source-git-commit: bd1cf8a3b4740594cf6b8678d899d771a886cb2e
workflow-type: tm+mt
source-wordcount: '1987'
ht-degree: 0%

---

# Eventi del connettore Experience Platform

Di seguito sono elencati gli eventi Commerce disponibili quando installi l’estensione del connettore Experience Platform. I dati raccolti da questi eventi vengono inviati al server Edge di Adobe Experience Platform. Puoi anche creare [eventi personalizzati](custom-events.md) raccogliere dati aggiuntivi non forniti al momento.

Oltre ai dati raccolti dai seguenti eventi, ottieni anche [altri dati](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) fornito dall’SDK Web di Adobe Experience Platform.

>[!NOTE]
>
>Tutti gli eventi della vetrina includono `personID` campo , che è un identificatore univoco della persona.

## addToCart

Attivazione quando un prodotto viene aggiunto al carrello o quando la quantità di un prodotto nel carrello viene incrementata.

### Nome evento XDM

`commerce.productListAdds`

### Tipo

Vetrina

### Dati raccolti

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

## openCart

Attivazione quando viene creato un nuovo carrello, ovvero quando un prodotto viene aggiunto a un carrello vuoto.

### Nome evento XDM

`commerce.productListOpens`

### Tipo

Vetrina

### Dati raccolti

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

## removeFromCart

Attivazione ogni volta che un prodotto viene rimosso o ogni volta che la quantità di un prodotto nel carrello viene diminuita.

### Nome evento XDM

`commerce.productListRemovals`

### Tipo

Vetrina

### Dati raccolti

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

## shoppingCartView

Attivazione quando viene caricata una pagina del carrello.

### Nome evento XDM

`commerce.productListViews`

### Tipo

Vetrina

### Dati raccolti

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

## pageView

Attivazione al caricamento di qualsiasi pagina.

### Nome evento XDM

`web.webpagedetails.pageViews`

### Tipo

Vetrina

### Dati raccolti

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `pageViews` | Indica se è stata caricata una pagina. A `value` di `1` indica che la pagina è stata caricata. |

## productPageView

Attivazione al caricamento di qualsiasi pagina di prodotto.

### Nome evento XDM

`commerce.productViews`

### Tipo

Vetrina

### Dati raccolti

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

## startCheckout

Attivazione quando l&#39;acquirente fa clic su un pulsante di pagamento.

### Nome evento XDM

`commerce.checkouts`

### Tipo

Vetrina

### Dati raccolti

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

## completeCheckout

Attivazione quando l&#39;acquirente effettua un ordine.

### Nome evento XDM

`commerce.order`

### Tipo

Vetrina

### Dati raccolti

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
| `productListItems` | Una serie di prodotti nel carrello |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `priceTotal` | Prezzo totale dell&#39;articolo della linea di prodotti |
| `quantity` | Numero di unità di prodotto nel carrello |
| `discountAmount` | Indica l&#39;importo dello sconto applicato |
| `currencyCode` | La [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codice valuta utilizzato per i totali dell&#39;ordine. |
| `productImageUrl` | URL immagine principale del prodotto |
| `selectedOptions` | Campo utilizzato per un prodotto configurabile. `attribute` identifica un attributo del prodotto configurabile, ad esempio `size` o `color` e `value` identifica il valore dell&#39;attributo, ad esempio `small` o `black`. |

## signIn

Attivazione quando un acquirente tenta di accedere.

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

### Nome evento XDM

`userAccount.login`

### Tipo

Profilo

### Dati raccolti

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

## signOut

Attivazione quando un acquirente tenta di disconnettersi.

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

### Nome evento XDM

`userAccount.logout`

### Tipo

Profilo

### Dati raccolti

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `eventType` | Il tipo di evento principale per questo record della serie temporale, ad esempio: `userAccount.logout` |
| `userAccount` | Indica eventuali dettagli fedeltà, preferenze, processi di accesso e altre preferenze dell’account |
| `logout` | Indica se un visitatore ha tentato di disconnettersi |

## createAccount

Attivazione quando un acquirente tenta di creare un account.

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

### Nome evento XDM

`userAccount.createProfile`

### Tipo

Profilo

### Dati raccolti

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

## editAccount

Attivazione quando un acquirente tenta di modificare un account.

>[!NOTE]
>
> Questo evento viene attivato quando si tenta l&#39;azione specifica. Non indica che l’azione è stata eseguita correttamente.

### Nome evento XDM

`userAccount.updateProfile`

### Tipo

Profilo

### Dati raccolti

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

## searchRequestSent

Attivato dai seguenti eventi nel puntatore &quot;cerca come digiti&quot;:

- Premi Invio
- Fai clic su _Visualizza tutto_

Attivazione dai seguenti eventi nelle pagine dei risultati di ricerca:

- Selezionare un filtro
- Cambia l&#39;ordinamento (_Ordina per_)
- Cambia la direzione di ordinamento (crescente o decrescente)
- Modifica il numero di risultati per pagina (_Mostra n. per pagina_)
- Passa alla pagina successiva
- Passa alla pagina precedente
- Passa a una pagina diversa

>[!NOTE]
>
>Gli eventi di ricerca non sono supportati in Adobe Commerce Enterprise Edition con il modulo B2B installato.

### Nome evento XDM

`searchRequest`

### Tipo

Ricerca

### Dati raccolti

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `searchRequest` | Indica se è stata inviata una richiesta di ricerca |
| `filter` | Indica se sono stati applicati filtri per limitare i risultati della ricerca |
| `attribute` (filtro) | Facet di un elemento utilizzato per determinare se includerlo nei risultati della ricerca |
| `value` | Valori degli attributi utilizzati per determinare quali elementi sono inclusi nei risultati di ricerca |
| `isRange` | Se true, i valori indicano gli endpoint di un intervallo di valori accettabile |
| `sort` | Indica come ordinare i risultati della ricerca |
| `attribute` (ordinamento) | Attributo utilizzato per ordinare gli elementi nei risultati di ricerca |
| `order` | Ordine in cui restituire i risultati della ricerca |
| `query` | Termini cercati |

## searchResponseReceived

Attivato quando Live Search restituisce i risultati per la pagina &quot;search as you type&quot; o risultati di ricerca.

>[!NOTE]
>
>Gli eventi di ricerca non sono supportati in Adobe Commerce Enterprise Edition con il modulo B2B installato.

### Nome evento XDM

`searchResponse`

### Tipo

Ricerca

### Dati raccolti

Nella tabella seguente sono descritti i dati raccolti per questo evento.

| Campo | Descrizione |
|---|---|
| `searchResponse` | Indica se è stata ricevuta una risposta di ricerca |
| `suggestions` | Matrice di stringhe che includono i nomi dei prodotti e delle categorie presenti nel catalogo simili alla query di ricerca |
| `numberOfResults` | Numero di prodotti restituiti |
| `productListItems` | Una serie di prodotti nel carrello. |
| `SKU` | Unità di conservazione delle scorte. Identificatore univoco per il prodotto. |
| `name` | Nome visualizzato o nome leggibile del prodotto |
| `productImageUrl` | URL immagine principale del prodotto |
