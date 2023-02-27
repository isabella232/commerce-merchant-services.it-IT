---
title: Configurazione generale
description: Configurare le impostazioni generali per abilitare [!DNL Store Fulfillment] per il tuo negozio. Configura le impostazioni di estensione globale, le impostazioni di sistema per la registrazione, la sincronizzazione dei dati e la sicurezza. Fornisci dati chiave per abilitare l’integrazione tra Adobe Commerce e i servizi Store Fulfillment.
role: User, Admin
level: Intermediate
exl-id: 51dcfc95-3dd6-40d9-bd26-d8409a25f3c8
source-git-commit: e7493618e00e28e2de5043ae2d7e05a81110d8f1
workflow-type: tm+mt
source-wordcount: '2440'
ht-degree: 0%

---

# Configurazione del servizio store e delle vendite

Configura [!DNL Store Fulfillment] dal [!DNL Commerce] Per abilitare l’estensione, specifica le impostazioni di estensione, configura le impostazioni di sicurezza per gli utenti dell’app Store Assist e imposta le opzioni per i metodi di consegna.

>[!IMPORTANT]
>
>La configurazione del servizio Store Fulfillment si applica solo dopo aver collegato la tua istanza Adobe Commerce e la [!DNL Store Fulfillment] app. Vedi [Esegui il programma Connect Store](connect-set-up-service.md).

## Gestire le impostazioni dei servizi di evasione dell&#39;archivio

Gestire le impostazioni per i servizi Store Fulfillment da [!DNL Commerce Admin Store Configuration] menu.

- Abilita l’estensione, configura le impostazioni globali e specifica le opzioni di sicurezza per le connessioni utente e gli account dell’app Store Assist selezionando **[!UICONTROL Stores > Configuration > Services > Store Fulfillment by Walmart Commerce Technologies]**.

   ![Configurazione dei servizi dell’Admin Store per l’esecuzione dello store](assets/store-services-admin-sf-config.png)

- Configura i metodi di consegna selezionando **[!UICONTROL Store > Configuration > Sales > Delivery Methods > In-Store Pickup]**.

   ![Configurazione vendite dell&#39;Admin Store per l&#39;evasione del negozio](assets/store-sales-admin-sf-deliver-config.png)

## Impostazioni di base

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Price]</strong></td>
<td>Prezzo da pagare al cliente per il ritiro in negozio. Il valore predefinito è zero.</td>
<td>Sito Web</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Search Radius]</strong></td>
<td>Il raggio, in chilometri, da utilizzare quando un acquirente cerca una posizione di ritiro del negozio nel negozio di checkout. I risultati della ricerca restituiscono solo gli archivi situati entro il raggio di ricerca specificato.</td>
<td>Sito Web</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Displayed error message]</strong></td>
<td>Messaggio visualizzato quando un cliente seleziona il ritiro in negozio per un elemento che non è disponibile per il ritiro in negozio. Se necessario, è possibile personalizzare il testo predefinito.
</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody>
</table>

>[!NOTE]
>
>La [!UICONTROL Search Radius] viene utilizzata solo se hai configurato il [posizione dell&#39;archivio e configurazione della mappatura](store-location-map-provider-setup.md) per Adobe Commerce.

## Abilita la soluzione Store Fulfillment

Abilita la [!DNL Store Fulfillment] soluzione per aggiungere le funzionalità di ritiro in-store e curbside alle esperienze di acquisto e pagamento nella tua vetrina Adobe Commerce.

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
 </thead>
 <tbody>
<tr>
<td><strong>[!UICONTROL Enabled]</strong></td>
<td>Abilita o disabilita la soluzione. Quando abilitato, configura e utilizza le funzionalità di Store Fulfillment e stabilisce la connessione tra il tuo archivio Adobe Commerce e [!DNL Store Fulfillment] servizi. Se disabilitata, tutte le funzioni di Store Fulfillment sono disabilitate e non è disponibile alcuna comunicazione tra Adobe Commerce e i servizi Store Fulfillment. Impossibile elaborare o ricevere le informazioni sull'ordine.</td>
<td>Sito Web</td>
<td>Sì</td>
</tr>
</tbody>
</table>

## Aggiungi credenziali account

<table>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
<tr>
<td><strong>[!UICONTROL Environment]</strong></td>
<td>Seleziona o <i>[!UICONTROL Sandbox]</i> o <i>[!UICONTROL Production]</i><br></br>Selezione [!UICONTROL Sandbox] consente la comunicazione con i servizi di esecuzione in un ambiente di test.<br></br>Selezione [!UICONTROL Production] consente la comunicazione con i servizi di realizzazione in un ambiente live.<br></br>A ogni ambiente viene assegnato un set di credenziali e puoi gestire entrambi i set nella stessa installazione. <br></br>Salvare le credenziali prima di convalidare la connessione.</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL API Server URL]</strong></td>
<td>URL dell’endpoint API per l’evasione di Walmart Store. Deve essere l’URL completo fornito durante il processo di onboarding. I clienti Store Fulfillment ricevono sia un URL Sandbox che di Produzione. Quando aggiungi i valori, accertati di copiare e incollare l’URL completo, inclusa la barra finale "/".</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Token Auth Server URL]</strong></td>
<td>L'URL dell'endpoint di autenticazione per l'evasione dell'archivio Walmart. Il valore deve essere l’URL completo fornito durante il processo di onboarding. Ricevi sia un URL Sandbox che di produzione. Quando aggiungi i valori, accertati di copiare e incollare l’URL completo, inclusa la barra finale "/".</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Merchant Id]</strong></td>
<td>L’ID commerciante (tenant) univoco fornito durante il processo di onboarding. Questo ID viene utilizzato per instradare gli ordini in modo che gli archivi commerciali li ricevano.</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Consumer Id]</strong></td>
<td>L'ID di integrazione univoco fornito durante il processo di onboarding. Questo ID viene utilizzato per autenticare tutte le comunicazioni tra Adobe Commerce e i servizi di evasione degli archivi</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Consumer Secret]</strong></td>
<td>Chiave di integrazione univoca fornita durante il processo di onboarding. Questa chiave viene utilizzata per autenticare tutte le comunicazioni tra Adobe Commerce e il servizio di evasione degli archivi.</td>
<td>Globale</td>
<td>Sì</td>
</tr>
</table>

Dopo aver configurato le [!UICONTROL Account Credentials], seleziona <strong>[!UICONTROL Validate Credentials]</strong> per verificare e stabilire una connessione al servizio di esecuzione del negozio per la prima volta.

## Configurare la registrazione

I registri per i servizi di evasione dell’archivio sono disponibili nel file di registro `var/log/walmart-bopis.log`.

Chiedi all’amministratore di sistema di configurare gli ambienti per consentire la gestione delle eccezioni in modo che le eccezioni relative alle API possano essere acquisite tramite il firewall o la cache.

Poiché il file di registro dell&#39;applicazione può crescere rapidamente, abilita la registrazione per l&#39;applicazione solo per un breve periodo di tempo quando necessario, ad esempio quando si risolvono i problemi di evasione dell&#39;archivio per un [!DNL Commerce] ordine. Questa configurazione evita i problemi di tempo di risposta negli ambienti di produzione causati da file di registro di grandi dimensioni.

>[!TIP]
>
>Per le installazioni on-premise di Adobe Commerce, chiedi all’amministratore di sistema di configurare la rotazione dei log per `var/log/walmart-bopis.log` per ridurre al minimo le dimensioni. Per le installazioni on-premise di Adobe Commerce, vedi [Rotazione del registro](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/next-steps/configuration.html#server-settings) in _Guida all’installazione di Adobe Commerce_. Per Adobe Commerce sui progetti di infrastruttura cloud, consulta [Visualizzare e gestire i registri](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/develop/test/log-locations.html).

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Debug Mode]</strong></td>
<td>La modalità Debug viene utilizzata per aumentare l'attività registrata all'interno dell'integrazione. Se disabilitata, non vengono registrate informazioni di debug. Quando abilitata, tutte le informazioni di debug vengono registrate <br></br>Tutti i dati registrati si trovano nel file : <pre>var/log/walmart-bopis.log</pre>
<td>Globale</td>
<td>No</td>
</tr>
</tbody>
</table>

## Gestisci sincronizzazione ordine

Configura le impostazioni per gestire gli errori per la sincronizzazione degli ordini, gli attributi del catalogo da utilizzare per la scansione dei codici a barre durante il prelievo degli ordini e configura le dimensioni dei batch degli ordini per la coda di evasione degli archivi.

Puoi visualizzare i dettagli sulle operazioni di sincronizzazione degli ordini dal dashboard Gestione code di evasione archivio nell&#39;Admin (
<strong>[!UICONTROL System > Tools > Store Fulfillment Queue]</strong>).

### Gestione degli errori di sincronizzazione

<table>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
<tr>
<td><strong>[!UICONTROL Retry Critical Error]</strong></td>
<td>Specifica i tentativi per un'operazione di sincronizzazione dei record dopo un errore critico.<br></br>Errori critici si verificano ogni volta che l'integrazione non riceve una risposta positiva dal servizio di evasione. Ciò può verificarsi quando il servizio è inattivo o quando si verifica un errore nei dati dell’ordine che si inviano.<br></br>Una volta raggiunta la soglia per i tentativi, l’elemento rimane in una coda ma non viene elaborato di nuovo. Visualizza tutti gli elementi con errori da <strong>[!UICONTROL System > Tools > Store Fulfillment Queue]</strong> Gestione in Admin. Per risolvere i problemi relativi agli elementi che si verificano con regolarità, contatta il tuo Account Manager.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Error Notification Email]</strong></td>
<td>Abilitare le notifiche di errore per ricevere un messaggio e-mail quando la variabile [!UICONTROL Retry Critical Error Threshold] viene raggiunto per un ordine. La notifica include tutti i dettagli disponibili sull’errore.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Send Error Notification Email To]</strong></td>
<td>Elenco delimitato da virgole degli indirizzi e-mail dei destinatari per le notifiche di errore.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Order Sync Exception Email Template]</strong></td>
<td>Specifica il modello e-mail utilizzato per avvisare i destinatari degli errori di sincronizzazione dell’ordine. Viene fornito un modello predefinito. Non supporta la personalizzazione.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</table>

### Sincronizzazione degli ordini

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Barcode Source]</strong></td>
<td>L'attributo di catalogo che memorizza il codice scannable per gli articoli corrispondenti nelle posizioni degli esercenti.<br></br>Se disponi di una sola posizione commerciale esistente, è probabile che tu utilizzi i codici UPC, mentre il tuo canale di e-commerce identifica i prodotti per SKU. Se questo è il tuo scenario, seleziona l'attributo di catalogo che contiene il codice UPC.<br></br>Questa impostazione assicura che gli ordini inviati ai punti vendita elenchi con l'identificatore corretto in modo che gli associati all'archivio possano eseguire una scansione accurata degli elementi durante il processo di prelievo.<br></br>Se non sei sicuro, controlla con i tuoi associati di evasione nel reparto Spedizione e prelievo per determinare quale attributo deve essere inviato. Potrebbe essere necessario aggiungere l'attributo appropriato al set di attributi di prodotto Adobe Commerce se l'attributo non è attualmente incluso nel database.</td>
<td>Sito Web</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Barcode Type]</strong></td>
<td>Attributo di catalogo che memorizza l’origine del codice a barre per gli articoli corrispondenti nelle posizioni degli esercenti.<br></br>Questa impostazione assicura che gli ordini inviati ai punti vendita elenchi con l'identificatore corretto in modo che gli associati all'archivio possano eseguire una scansione accurata degli elementi durante il processo di prelievo. Le opzioni includono: SKU, UPC, GTIN, UPCA, EAN13, UPCE0, DISA, UAB, CODABAR, Price Embedded UPC.<br></br>Se non sei sicuro, seleziona l’opzione che assomiglia maggiormente ai valori contenuti nel tuo [!UICONTROL Barcode Source] attributo. I collaboratori dello store possono comunque corrispondere gli elementi manualmente dal loro elenco di selezione.</td>
<td>Sito Web</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Max Number of Items]</strong></td>
<td>Il numero massimo di elementi da inviare contemporaneamente dalla coda di evasione dell'archivio.<br></br>Gli ordini BOPIS vengono inviati al servizio di evasione a intervalli regolari in batch. Questa impostazione consente di controllare le dimensioni del batch.<br></br>Il valore predefinito è 100 elementi. A seconda del volume e della capacità dell'ordine, potrebbe essere necessario regolare questo valore in alto o in basso.</td>
<td>Globale</td>
<td>No</td>
</tr>
</tbody>
</table>

## Abilita opzioni di spedizione per l&#39;evasione del negozio

Configura le opzioni di spedizione Store Fulfillment che determinano la disponibilità delle opzioni di ritiro in negozio e consegna a domicilio per i tuoi negozi Adobe Commerce.

### Negozio di spedizione

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Enable Ship To Store]</strong></td>
<td>L'impostazione "nave-to-store" si basa sulle capacità esistenti di spedizione-to-store. Se utilizzi Inventory management o se puoi accettare e soddisfare ordini in posizioni commerciali senza inventario tramite trasferimenti di inventario da negozio a negozio, imposta questa opzione su "Sì".<br></br>Se non è possibile supportare l'opzione di consegna al negozio o non si desidera offrirla, impostare su "No". Se disabilitata, gli articoli nel catalogo con inventario zero per un negozio di merchant o quelli che si trovano al di sotto di tale posizione [!DNL Out of Stock Threshold], non sono offerte con opzioni di ritiro in negozio.<br></br>Si tratta di un’impostazione globale che può essere regolata in base alla posizione del commerciante.</td>
<td>Globale</td>
<td>No</td>
</tr>
</tbody>
</table>

### Negozio a partire da spedizione

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Enable Ship From Store]</strong></td>
<td>Abilita o disabilita l’opzione Consegna iniziale negli archivi commerciali. Quando abilitata, le posizioni del tuo negozio di esercenti sono considerate in aggregato con altre sorgenti assegnate nel stock associato al tuo sito web.<br></br>Nei servizi Inventory management standard, la [!DNL Ship from Store] l’opzione è intrinseca e non può essere disabilitata. Con la soluzione Store Fulfillment, è possibile attivarla o disattivarla.<br></br>Questa è un'impostazione globale. È inoltre possibile regolare questa impostazione per posizione e prodotto mercante.</td>
<td>Globale</td>
<td>No</td>
</tr>
</tbody>
</table>


## Gestisci account e autorizzazioni per l&#39;utilizzo dell&#39;app dell&#39;archivio

Configura le impostazioni per l’account utente dell’app di evasione archivio e la sicurezza della password e l’autenticazione a due fattori.

### App Security

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
 </thead>
 <tbody>
<tr>
<td><strong>[!UICONTROL User Session Lifetime]</strong></td>
<td>L'intervallo di tempo, in secondi, in cui una sessione utente associata allo store rimane attiva prima del logout automatico. I valori validi sono compresi tra 60 e 31536000.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Maximum Login Failures to Lockout Account]</strong></td>
<td>Specifica il numero di tentativi di accesso non riusciti consentiti prima che un associato dello store venga bloccato dal proprio account.<br></br>Per disattivare il blocco degli account, imposta il valore su 0.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Lockout Time (minutes)]</strong></td>
<td>Numero di minuti per bloccare un account dopo un errore di accesso.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Force Password Change]</strong></td>
<td><em>[!UICONTROL Yes]</em>: Richiedi all'utente di cambiare la password dopo la configurazione dell'account.<br></br><em>[!UICONTROL No]</em>: Consiglia all'utente di cambiare la password dopo la configurazione dell'account.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Password Lifetime]</strong></td>
<td>Il numero di giorni in cui una password rimane valida prima della modifica della password richiesta. Lascia vuoto per disabilitare questa opzione.</td>
<td>Globale</td>
<td>No</td>
</tr>
</tbody>
</table>

## Metodi di Consegna

L&#39;evasione dello store funziona estendendo il Adobe Commerce nativo [!DNL In-Store Delivery] funzionalità. Dopo aver installato l&#39;estensione, puoi configurare i metodi di consegna in-store utilizzando le seguenti impostazioni estese aggiunte all&#39;amministratore.

- **Ritiro in negozio**- Opzioni di offerta per la consegna in negozio durante il processo di pagamento Questo è lo scenario di consegna più comune per gli ordini BOPIS.

- **[!UICONTROL Curbside pick up]**- Opzioni di offerta per i clienti per parcheggiare in una posizione del negozio e far loro consegnare il loro ordine da un associato del negozio.

Configura queste impostazioni dall’amministratore selezionando <strong>[!UICONTROL Stores > Configuration > Sales > Delivery Methods > In-Store Pickup]</strong>.

>[!NOTE]
>
>Per ulteriori informazioni sulla configurazione delle opzioni di consegna in-store, vedi [Consegna in-store](https://docs.magento.com/user-guide/shipping/shipping-in-store-delivery.html) in _Guida utente di Adobe Commerce_.


### Configurazione dei metodi di consegna

Con il metodo di consegna in-store, il cliente può selezionare un&#39;origine da utilizzare come posizione di ritiro durante il pagamento.

<table>
<thead>
<tr>
<td><strong>Campo</strong></td>
<td><strong>Descrizione</strong></td>
<td><strong>Ambito</strong></td>
<td><strong>Obbligatorio</strong></td>
</tr>
 </thead>
 <tbody>
<tr>
<td><strong>[!UICONTROL Enable In-Store Pickup]</strong></td>
<td>Attiva o disattiva l'opzione di ritiro in negozio disponibile durante il pagamento per i clienti che scelgono il ritiro dal negozio. Quando il ritiro in negozio è disattivato, l’opzione non viene visualizzata.<br></br>Questa impostazione globale si applica a tutte le posizioni dei punti vendita al dettaglio. Quando abilitato, puoi disattivarlo in modo selettivo nella posizione del negozio.</td>
<td>Sito Web</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Curbside Pickup]</strong></td>
<td>Attiva o disattiva l'opzione di prelievo sul lato curvo durante il processo di pagamento per i clienti che scelgono il ritiro dal negozio.<br></br>Questa impostazione globale si applica a tutte le posizioni dei punti vendita al dettaglio. Quando abilitato, puoi disattivarlo in modo selettivo nella posizione del negozio.</td>
<td>Sito Web</td>
<td>No</td>
</tr>
</tbody>
</table>

### Configurazione del titolo del metodo di consegna

<table>
<thead>
<tr>
<th><strong>Campo</strong></th>
<th><strong>Descrizione</strong></th>
<th><strong>Ambito</strong></th>
<th><strong>Obbligatorio</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>Titolo della consegna casa</strong></td>
<td>Specifica il titolo da visualizzare per l'opzione Consegna iniziale nelle aree di prodotto, carrello e pagamento. La consegna a domicilio si riferisce alle capacità di spedizione standard di Adobe Commerce, da un magazzino, da un vettore o direttamente all'indirizzo di spedizione fornito dal cliente. </br></br>Questa etichetta non influisce sulle etichette del metodo di spedizione per il vettore di spedizione selezionato.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Descrizione della consegna</strong></td>
<td>Una descrizione facoltativa che viene visualizzata ogni volta che il Titolo della consegna principale viene mostrato ai clienti. Nella maggior parte dei casi, la descrizione è un messaggio statico per comunicare le promesse di consegna. Alcuni esempi:</br><code>Same-day shipping on orders by 4</code></br></br><code>Ships within 2 business days</code></td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Titolo del ritiro store</strong></td>
<td>Quando a un cliente vengono presentate le opzioni di consegna ed è disponibile il ritiro in negozio, viene visualizzata questa etichetta. </br></br>Puoi personalizzare questa etichetta, che viene visualizzata nelle aree prodotto, carrello e pagamento.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<td><strong>Descrizione del ritiro dal negozio</strong></td>
<td>Ovunque sia visualizzato il Titolo del ritiro dell’archivio, puoi facoltativamente includere una descrizione. Questo messaggio statico consente di migliorare le comunicazioni dei clienti relative all’esperienza di ritiro dal negozio. Alcuni esempi:</br></br><code>Get it today for free!</code></br></br><code>Ready for pickup in an hour!</code></td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Titolo del prelievo nello store</strong></td>
<td>Quando il Pickup in-store è abilitato, questo titolo viene mostrato ai clienti come opzione di consegna Store Pickup. Puoi personalizzare la relativa etichetta.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<tr>
<td><strong>Titolo del pickup</strong></td>
<td>Quando Curbside Pickup è abilitato, l’opzione viene mostrata ai clienti come opzione di consegna Store Pickup. Puoi personalizzare la relativa etichetta qui.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Istruzioni per il caricamento nello store</strong></td>
<td>Quando un ordine è pronto per il ritiro presso i negozi al dettaglio, il cliente riceve una notifica tramite e-mail. Se il cliente ha selezionato [!DNL In-Store Pickup] durante il pagamento, è possibile personalizzare le istruzioni di ritiro qui. </br></br>Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare le istruzioni a livello di posizione del punto vendita.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Istruzioni per l'accesso a Curbside</strong></td>
<td>Specifica le istruzioni di prelievo dell'ordine personalizzate da includere nelle notifiche e-mail del cliente per gli ordini di ritiro curbside. </br></br>Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare le istruzioni a livello di posizione del punto vendita.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Lead time di recupero stimato</strong></td>
<td>Il numero di minuti necessari prima che un ordine venga ricevuto, evaso e pronto per essere prelevato. Queste informazioni vengono mostrate al cliente quando si seleziona una posizione del negozio al dettaglio per l'opzione di consegna del ritiro dal negozio. Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare il lead time a livello di posizione del negozio.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Etichetta del tempo di recupero stimato</strong></td>
<td>Visualizza il tempo stimato fino a quando un ordine non è disponibile per il ritiro del cliente. Queste informazioni vengono mostrate ai clienti quando selezionano una posizione di vendita al dettaglio per [!DNL In-Store Pickup] opzione di consegna. </br></br>Quando personalizzi questa etichetta, puoi utilizzare il codice <code>%1</code> per inserire il <strong>Lead time di recupero stimato</strong>. Ad esempio:</br></br><code>Ready for Pickup in %1 minutes.</code></br></br>Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare il lead time a livello di posizione del negozio.</br></br><code>Ready for Pickup in %1 minutes.</code></br></br></td>
<td>Visualizzazione store</td>
<td>No</td>
<tr>
<td><strong>Disclaimer sul tempo di recupero</strong></td>
<td>Contenuto visualizzato nella descrizione del prodotto nella descrizione che elenca le ore di memorizzazione, le festività, le chiusure impreviste e così via</td>
<td>Visualizzazione store
</td>
<td>No
</td>
</tr>
</tbody></table>

### Configurazione dei titoli di disponibilità stock

<table>
<thead>
<tr>
<th><strong>Campo</strong></th>
<th><strong>Descrizione</strong></th>
<th><strong>Ambito</strong></th>
<th><strong>Obbligatorio</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>Disponibile</strong></td>
<td>Quando un cliente utilizza la collocazione del negozio al dettaglio, la disponibilità di inventario per gli articoli correnti viene visualizzata per ogni posizione. </br></br>Puoi personalizzare le <em>[!UICONTROL in-stock]</em> etichetta di stato.</br></br></td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Non disponibile</strong></td>
<td>Quando un cliente utilizza l'indicatore di posizione del negozio al dettaglio, viene visualizzata la disponibilità di inventario per tutti gli articoli correnti per ogni posizione.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Disponibile parzialmente</strong></td>
<td>Quando un cliente utilizza la collocazione del negozio al dettaglio, la disponibilità di inventario per gli articoli correnti viene visualizzata per ogni posizione. </br></br>Puoi personalizzare le <em>[!UICONTROL partially in-stock]</em> etichetta di stato.</br></br></td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>

