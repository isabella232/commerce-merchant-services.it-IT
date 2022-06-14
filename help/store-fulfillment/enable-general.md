---
title: Configurazione generale
description: Configurare le impostazioni generali per abilitare [!DNL Store Fulfillment] per il tuo negozio. Configura le impostazioni di estensione globale, le impostazioni di sistema per la registrazione, la sincronizzazione dei dati e la sicurezza. Fornisci dati chiave per abilitare l’integrazione tra Adobe Commerce e i servizi Store Fulfillment.
role: User, Admin
level: Intermediate
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '2409'
ht-degree: 0%

---

# Configurazione generale

Nell’amministratore di Adobe Commerce, configura le impostazioni di configurazione generali per abilitare [!DNL Store Fulfillment] servizi per il tuo archivio, configura le impostazioni di estensione globale e fornisci i dati chiave per l&#39;integrazione configurando il [!UICONTROL Account Credentials].

L&#39;integrazione deve essere collegata al servizio Store Fulfillment. Inoltre, configura le impostazioni generali di Store Fulfillment per abilitare e personalizzare i servizi Store Fulfillment in base alle funzionalità e ai requisiti operativi della tua organizzazione.

La configurazione generale per [!DNL Store Fulfillment] include le seguenti impostazioni di configurazione:

- [Abilita l&#39;estensione](#enable-the-extension)
- [Gestire le credenziali dell&#39;account per connettersi ai servizi di evasione dell&#39;archivio](#account-credentials)
- [Configurare la registrazione](#configure-logging)
- [Impostare le opzioni per la gestione delle operazioni di [sincronizzazione ordine]](#order-synchronization)
- [Abilita opzioni di spedizione per l&#39;evasione del negozio](#enable-store-fullment-shipping-options)
- [Configurare le impostazioni di sicurezza e autenticazione per l’app Store Fulfillment](#store-fulfillment-app)
- [Imposta la disponibilità e la configurazione dei messaggi del metodo di consegna](#in-store-delivery-methods)


## Abilita l&#39;estensione

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enabled]** | Abilita o disabilita la soluzione. Quando abilitato, configura e utilizza le funzionalità di Store Fulfillment e stabilisce la connessione tra i servizi Adobe Commerce Store e Store Fulfillment. Quando è disabilitata, tutte le funzioni di Store Fulfillment sono disabilitate e non vi è comunicazione tra Adobe Commerce e i servizi Store Fulfillment. Impossibile elaborare o ricevere le informazioni sull&#39;ordine. | Globale | Sì |


Per completare questa configurazione, vedi **Negozi → Configurazione → Servizi → Store Fulfillment by Walmart Commerce Technologies**.

## Aggiungi credenziali account



| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Environment]** | Può selezionare *Sandbox* o *Produzione*:</br> Sandbox comunica con i servizi di evasione in un test.</br>La produzione comunica con un ambiente live. Utilizzo **only** in produzione.</br>Puoi assegnare un set di credenziali per ogni ambiente e gestire entrambi i set nella stessa installazione. </br></br>Salvare le credenziali prima di convalidare la connessione. | Globale | Sì |
| **[!UICONTROL API Server URL]** | URL dell’endpoint API per l’evasione di Walmart Store. Questo deve essere un URL completo fornito durante il processo di onboarding. I clienti Store Fulfillment ricevono sia un URL Sandbox che di Produzione. Assicurati di copiare/incollare l’URL completo, inclusa la barra finale &quot;/&quot;. | Globale | Sì |
| **[!UICONTROL Token Auth Server URL]** | L&#39;URL dell&#39;endpoint di autenticazione per l&#39;evasione dell&#39;archivio Walmart. Il valore deve essere l’URL completo fornito durante il processo di onboarding. Ricevi sia un URL Sandbox che di produzione. Assicurati di copiare/incollare l’URL completo, inclusa la barra finale `/`&quot;. | Globale | Sì |
| **[!UICONTROL Merchant Id]** | L’ID commerciante (tenant) univoco fornito durante il processo di onboarding. L&#39;ID viene utilizzato per instradare gli ordini e assicura che i negozi commerciali li ricevano. | Globale | Sì |
| **[!UICONTROL Consumer Id]** | L&#39;ID di integrazione univoco. Questo viene fornito durante il processo di onboarding. Non cambia. Viene utilizzato per autenticare tutte le comunicazioni con i servizi di evasione. | Globale | Sì |
| **[!UICONTROL Consumer Secret]** | Chiave di integrazione univoca. Questo viene fornito durante il processo di onboarding. Viene utilizzato per autenticare tutte le comunicazioni con i servizi di evasione. | Globale | Sì |

Dopo aver configurato le credenziali account, seleziona **[!UICONTROL Validate Credentials]** per verificare e stabilire una connessione al servizio Web di evasione per la prima volta.

## Configurare la registrazione

Quando la registrazione è abilitata, il file di registro può espandersi rapidamente. Per evitare problemi di tempo di risposta negli ambienti di produzione, fai attenzione ad abilitare la registrazione e attiva solo per un breve periodo di tempo quando necessario.

Chiedi all’amministratore di sistema di configurare gli ambienti per consentire la gestione delle eccezioni in modo che le eccezioni relative alle API possano essere acquisite tramite il firewall o la cache. È inoltre possibile chiedere all&#39;amministratore di sistema di impostare la rotazione del registro su questo file per ridurre al minimo le dimensioni.

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **Modalità debug** | La modalità Debug viene utilizzata per aumentare l&#39;attività registrata all&#39;interno dell&#39;integrazione. Se disabilitata, non vengono registrate informazioni di debug. Quando abilitata, tutte le informazioni di debug vengono registrate.</br> Tutti i dati registrati si trovano nel file : `var/log/walmart-bopis.log` | Globale | No |

## Gestisci sincronizzazione ordine

Configura le impostazioni per gestire gli errori per la sincronizzazione degli ordini, gli attributi del catalogo da utilizzare per la scansione dei codici a barre durante il prelievo degli ordini e configura le dimensioni dei batch degli ordini per la coda di evasione degli archivi.

Puoi visualizzare i dettagli sulle operazioni di sincronizzazione degli ordini dal dashboard Gestione code di evasione archivio nell&#39;Admin (
**[!UICONTROL System > Tools > Store Fulfillment Queue]**).

### Gestione degli errori di sincronizzazione

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|-----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|--------------|
| **Errore critico di nuovo** | Specifica i tentativi per un&#39;operazione di sincronizzazione dei record dopo un errore critico.</br></br>Errori critici si verificano ogni volta che l&#39;integrazione non riceve una risposta positiva dal servizio di evasione. Ciò può verificarsi quando il servizio è inattivo o quando si verifica un errore nei dati dell’ordine che si inviano.</br></br>Una volta raggiunta la soglia per i tentativi, l’elemento rimane in una coda ma non viene elaborato di nuovo. Visualizza tutti gli elementi con errori da **[!UICONTROL System → Tools → Store Fulfillment Queue]** Gestione in Admin. Per risolvere i problemi relativi agli elementi che si verificano con regolarità, contatta il tuo Account Manager. | Globale | No |
| **Abilita e-mail di notifica degli errori** | Abilitare le notifiche di errore per ricevere un messaggio e-mail quando la variabile [!UICONTROL Retry Critical Error Threshold] viene raggiunto per un ordine. La notifica include tutti i dettagli disponibili sull’errore. | Globale | No |
| **Invia e-mail di notifica di errore a** | Elenco delimitato da virgole degli indirizzi e-mail dei destinatari per le notifiche di errore. | Globale | No |
| **Modello e-mail eccezione di sincronizzazione ordine** | Specifica il modello e-mail utilizzato per avvisare i destinatari degli errori di sincronizzazione dell’ordine. Viene fornito un modello predefinito. Non supporta la personalizzazione. | Visualizzazione store | No |

### Sincronizzazione degli ordini

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|--------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Barcode Source]** | L&#39;attributo di catalogo che memorizza il codice scannable per gli articoli corrispondenti nelle posizioni degli esercenti.</br></br>Se disponi di una sola posizione commerciale esistente, è probabile che tu utilizzi i codici UPC, mentre il tuo canale di e-commerce identifica i prodotti per SKU. Se questo è il tuo scenario, seleziona l&#39;attributo di catalogo che contiene il codice UPC.</br></br>Questa impostazione assicura che gli ordini inviati al tuo commerciante memorizzino le voci di elenco con l&#39;identificatore corretto, in modo che gli associati al negozio possano eseguire una scansione accurata degli elementi durante il processo di prelievo.</br></br>Se non sei sicuro, controlla con i tuoi associati di evasione nel reparto Spedizione e prelievo per determinare quale attributo deve essere inviato. Potrebbe essere necessario aggiungere l&#39;attributo appropriato al set di attributi di prodotto Adobe Commerce se l&#39;attributo non è attualmente incluso nel database. | Sito Web | Sì |
| **[!UICONTROL Barcode Type]** | Attributo di catalogo che memorizza l’origine del codice a barre per gli articoli corrispondenti nelle posizioni degli esercenti.</br></br>Questa impostazione assicura che gli ordini inviati al commerciante memorizzino gli elementi dell&#39;elenco con l&#39;identificatore corretto, in modo che gli associati all&#39;archivio possano eseguire una scansione accurata degli elementi durante il processo di prelievo. Le opzioni includono: SKU, UPC, GTIN, UPCA, EAN13, UPCE0, DISA, UAB, CODABAR, Price Embedded UPC.</br></br>Se non sei sicuro, seleziona l’opzione che assomiglia maggiormente ai valori contenuti nel tuo [!UICONTROL Barcode Source] attributo. I collaboratori dello store possono comunque corrispondere gli elementi manualmente dal loro elenco di selezione. | Sito Web | Sì |
| **[!UICONTROL Max Number of Items]** | Il numero massimo di elementi da inviare contemporaneamente dalla coda di evasione dell&#39;archivio.</br></br>Gli ordini BOPIS vengono inviati al servizio di evasione a intervalli regolari in batch. Questa impostazione consente di controllare le dimensioni del batch.</br></br>Il valore predefinito è 100 elementi. A seconda del volume e della capacità dell&#39;ordine, potrebbe essere necessario regolare questo valore in alto o in basso. | Globale | No |


## Abilita opzioni di spedizione per l&#39;evasione del negozio

Configura le opzioni di spedizione Store Fulfillment che determinano la disponibilità delle opzioni di ritiro in negozio e consegna a domicilio per i tuoi negozi Adobe Commerce.

### Negozio di spedizione


| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enable Ship To Store]** | L&#39;impostazione &quot;nave-to-store&quot; sfrutta le funzionalità esistenti di spedizione-to-store. Se utilizzi Inventory management o se puoi accettare e soddisfare gli ordini in posizioni commerciali senza inventario tramite trasferimenti di inventario store-to-store, imposta questa opzione su `Yes`.</br></br>Se non è possibile supportare l&#39;opzione di consegna al negozio o non si desidera offrirla, impostare su `No`. Se disabilitata, gli articoli nel catalogo con inventario zero per un negozio di merchant o quelli che si trovano al di sotto di tale posizione [!DNL Out of Stock Threshold], non sono offerte con opzioni di ritiro in negozio.</br></br>Si tratta di un’impostazione globale che può essere regolata in base alla posizione del commerciante. | Globale | No |

### Negozio a partire da spedizione

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enable Ship From Store]** | Abilita o disabilita l’opzione Consegna iniziale negli archivi commerciali. Quando abilitata, le posizioni del tuo negozio di esercenti sono considerate in aggregato con altre sorgenti assegnate nel stock associato al tuo sito web.</br></br>Nei servizi Inventory management standard, la [!DNL Ship from Store] l’opzione è intrinseca e non può essere disabilitata. Con la soluzione Store Fulfillment hai la possibilità di attivarla o disattivarla.</br></br>Questa è un&#39;impostazione globale. È inoltre possibile regolare questa impostazione per posizione e prodotto mercante. | Globale | No |


## Gestisci account e autorizzazioni per l&#39;utilizzo dell&#39;app dell&#39;archivio

Configura le impostazioni per l’account utente dell’app di evasione archivio e la sicurezza della password e l’autenticazione a due fattori.

### App Security

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL User Session Lifetime]** | L&#39;intervallo di tempo, in secondi, in cui una sessione utente associata allo store rimane attiva prima del logout automatico. I valori validi sono compresi tra 60 e 31536000. | Globale | No |
| **[!UICONTROL Maximum Login Failures to Lockout Account]** | Specifica il numero di tentativi di accesso non riusciti consentiti prima che un associato dello store venga bloccato dal proprio account.</br></br>Per disattivare il blocco degli account, imposta il valore su 0. | Globale | No |
| **[!UICONTROL Lockout Time (minutes)]** | Numero di minuti per bloccare un account dopo un errore di accesso. | Globale | No |
| **[!UICONTROL Force Password Change]** | Determina se è richiesta una modifica della password utente.</br></br>`Yes`: Richiedi all&#39;utente di cambiare la password dopo la configurazione dell&#39;account.</br>`No`: Consiglia all&#39;utente di cambiare la password dopo la configurazione dell&#39;account. | Globale | No |
| **Durata della password** | Il numero di giorni in cui una password rimane valida prima della modifica della password richiesta. Lascia vuoto per disabilitare questa opzione. | Globale | No |


### Autenticazione a due fattori

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **APP utente 2FA** | Abilita o disabilita l’autenticazione a due fattori per gli associati allo store. Quando è abilitata, all&#39;associazione store viene richiesto di fornire una password una tantum generata da un provider di autenticazione. | Globale | No |
| **Criterio APP 2FA** | Imposta i criteri di imposizione per l’autenticazione a due fattori.</br></br>**[!UICONTROL Optional]**: L&#39;associazione allo store può ignorare l&#39;autenticazione a due fattori se non è impostato alcun provider.</br></br>**[!UICONTROL Mandatory]**: L&#39;associazione allo store è necessaria per completare l&#39;autenticazione a due fattori. | Globale | No |
| **Provider 2FA** | Selezionare uno o più servizi del provider di autenticazione per offrire ai collaboratori dello store. Per impostare l’autenticazione e l’autenticazione a due fattori, gli associati allo store devono installare l’app di autenticazione da uno dei provider disponibili installati sui propri dispositivi mobili. | Globale | No |

### Metodi di Consegna

L&#39;evasione dello store funziona estendendo il Adobe Commerce nativo [!DNL In-Store Delivery] funzionalità.
Dopo aver installato l’estensione, sono disponibili ulteriori opzioni di configurazione amministratore per i metodi di consegna in-store. Configura queste opzioni aggiuntive dall’amministratore selezionando **[!UICONTROL Stores > Configuration > Sales > Delivery Methods > In-Store Pickup]**.

Nelle impostazioni Store Fulfillment (Esegui evasione archivio), puoi configurare i seguenti metodi di consegna per gli ordini In-Store Pickup.

- **Ritiro in negozio**- Opzioni di offerta per la consegna in negozio durante il processo di pagamento Questo è lo scenario di consegna più comune per gli ordini BOPIS.

- **Curbside pick**- Opzioni di offerta per i clienti per parcheggiare in una posizione del negozio e far loro consegnare il loro ordine da un associato del negozio.

#### Configurazione dei metodi di consegna

<!---
In-store pickup, says its global setting, but scope is Website.  How do you configure the in-store pickup options at the retail level?
--->

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enable In-Store Pickup]** | Attiva o disattiva l&#39;opzione di ritiro in negozio disponibile durante il pagamento per i clienti che scelgono il ritiro dal negozio. Quando il ritiro in negozio è disattivato, l’opzione non viene visualizzata.</br></br>Questa impostazione globale si applica a tutte le posizioni dei punti vendita al dettaglio. Quando abilitato, puoi disattivarlo in modo selettivo nella posizione del negozio. | Sito Web | No |
| **Abilita ritocco urbano** | Attiva o disattiva l&#39;opzione di prelievo sul lato curvo durante il processo di pagamento per i clienti che scelgono il ritiro dal negozio.</br></br>Questa impostazione globale si applica a tutte le posizioni dei punti vendita al dettaglio. Quando abilitato, puoi disattivarlo in modo selettivo nella posizione del negozio. | Sito Web | No |

Per informazioni dettagliate su come personalizzare i metodi di consegna nelle posizioni dei punti vendita al dettaglio selezionate, consulta **Configurazione punto vendita al dettaglio**.


#### Configurazione del titolo del metodo di consegna

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
<td>Specifica il titolo da visualizzare per l'opzione Consegna iniziale nelle aree di prodotto, carrello e pagamento. La consegna a domicilio si riferisce alle capacità di spedizione standard di Adobe Commerce, da un magazzino, da un vettore, direttamente all'indirizzo di spedizione fornito dal cliente.</br></br>Questa etichetta non influisce sul vettore di spedizione selezionato o sulle relative etichette del metodo di spedizione disponibili.</td>
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
<td>Quando a un cliente vengono presentate le opzioni di consegna ed è disponibile il ritiro in negozio, viene visualizzata questa etichetta.</br></br>Puoi personalizzare questa etichetta, che viene visualizzata nelle aree prodotto, carrello e pagamento.</td>
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
<td>Quando un ordine è pronto per il ritiro presso i negozi al dettaglio, il cliente riceve una notifica tramite e-mail. Se il cliente ha selezionato [!DNL In-Store Pickup] durante il pagamento, è possibile personalizzare le istruzioni di ritiro qui.</br></br>Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare le istruzioni a livello di posizione del punto vendita.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Istruzioni per l'accesso a Curbside</strong></td>
<td>Specifica le istruzioni personalizzate di prelievo ordine da includere nelle notifiche e-mail del cliente per gli ordini di ritiro dei curbside.</br></br>Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare le istruzioni a livello di posizione del punto vendita.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Lead time di recupero stimato</strong></td>
<td>Il numero di minuti necessari prima che un ordine venga ricevuto, evaso e pronto per essere prelevato. Queste informazioni vengono mostrate al cliente quando si seleziona una posizione del negozio al dettaglio per l'opzione di consegna del ritiro dal negozio.</br></br>Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare il lead time a livello di posizione del negozio.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Etichetta del tempo di recupero stimato</strong></td>
<td>Visualizza il tempo stimato fino a quando un ordine non è disponibile per il ritiro del cliente. Queste informazioni vengono mostrate ai clienti quando selezionano una posizione del negozio al dettaglio per l'opzione di consegna del ritiro dal negozio.</br></br>Quando personalizzi questa etichetta, puoi utilizzare il codice <code>%1</code> per inserire il <strong>Lead time di recupero stimato</strong>Ad esempio:</br></br><code>Ready for Pickup in %1 minutes.</code></br></br>Si tratta di un'impostazione globale che si applica a tutte le posizioni dei punti vendita al dettaglio. È inoltre possibile personalizzare il lead time a livello di posizione del negozio.</br></br><code>Ready for Pickup in %1 minutes.</code></br></br></td>
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

#### Configurazione titoli disponibilità stock

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
<td>Quando un cliente utilizza l'indicatore di posizione del negozio al dettaglio, viene visualizzata la disponibilità di inventario per l'articolo o gli articoli correnti per ogni posizione.</br></br>Puoi personalizzare l’etichetta di stato "in-stock" qui.</td>
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
<td>Quando un cliente utilizza la collocazione del negozio al dettaglio, la disponibilità di inventario per gli articoli correnti viene visualizzata per ogni posizione.</br></br>Puoi personalizzare l’etichetta di stato "parziale disponibile" qui.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>





