---
title: Esecuzione del test e distribuzione dello store
description: Piano di test per verificare la funzionalità Store Fulfillment. I test coprono l’API di sincronizzazione dell’inventario, il flusso di lavoro di evasione end-to-end per gli ordini annullati, la gestione degli utenti dell’app di evasione dell’archivio e l’esperienza di archiviazione dei clienti.
role: User, Admin
level: Intermediate
exl-id: 77285a66-5161-407b-94cd-b3f412d7949d
source-git-commit: 556cbf803a0f8569e8561d2b33b7a976065ae814
workflow-type: tm+mt
source-wordcount: '2652'
ht-degree: 0%

---

# Esecuzione di test e distribuisci store per Adobe Commerce

Dopo aver completato il processo di onboarding nell&#39;ambiente di sviluppo, puoi avviare il processo per testare e distribuire la soluzione Store Fulfillment nell&#39;ambiente di produzione.

**Prerequisiti**

Prima di testare o sincronizzare le informazioni, gli archivi o gli ordini, verifica di aver completato le seguenti attività:

- Completato il [Configurazione generale](enable-general.md) per i servizi Store Fulfillment.

- [Aggiungi e convalida le credenziali dell’account e i dettagli di connessione per la sandbox e gli ambienti di produzione](connect-set-up-service.md#configure-store-fulfillment-account-credentials)

- Conferma che [Integrazione Adobe Commerce](connect-set-up-service.md#configure-store-fulfillment-account-credentials) per la soluzione Store Fulfillment è disponibile e autorizzata.

## Preparazione al test

La configurazione della connessione deve essere completata prima di poter creare qualsiasi ordine di test o eseguire test di integrazione. Prima di eseguire il test, è inoltre necessario verificare che i dati dell&#39;archivio siano sincronizzati.

1. Sincronizza le origini di Store Fulfillment.

   - Vai a **[!UICONTROL Stores > Sources]**.

   - Seleziona **[!UICONTROL Synchronize Store Fulfillment Sources]**.

1. Dalla griglia dello store, verificare che gli archivi siano stati contrassegnati come `Synced` prima di creare ordini di test.

## Piano di test di esempio

I rivenditori convalidano le funzionalità di base della soluzione Store Fulfillment durante la configurazione e il test delle fasi di una distribuzione. Questo piano di prova campione fornisce un punto di partenza per le prove. Aggiungi scenari aggiuntivi in base alle tue esigenze.

>[!NOTE]
>
>Dopo aver completato l&#39;onboarding iniziale per la soluzione Store Fulfillment o aggiornato un&#39;installazione esistente, testa sempre l&#39;applicazione in un ambiente non di produzione prima di distribuirla in produzione.

Questo piano di prova campione riguarda i seguenti settori funzionali:

| Area funzionale | Funzione | Ruolo |
|-------------------------------------|------------------------------------------|----------------------------------|
| Sincronizzazione dell&#39;inventario e degli ordini | Sincronizzazione API inventario | Amministratore Adobe Commerce |
| Fine-fine | Flussi di lavoro di annullamento ordini | Cliente, Amministratore, Store Associate |
| Amministratore | Autorizzazioni per l&#39;app per l&#39;evasione dell&#39;archivio | Amministratore |
| Adobe Commerce Frontend | Tipi di prodotti | Cliente, Amministratore |
| Pagamento senza frontiere</br>Modulo di archiviazione | Esperienza di check-in | Cliente, Amministratore |
| App Store Assist | Ordine</br>Selezione</br>Stage</br>e Handoff | Associato store |

### Sincronizzazione API di Inventory

Questa sezione del piano di test riguarda l’inventario e la sincronizzazione degli ordini per verificare che gli aggiornamenti alle origini di prelievo e alle scorte siano sincronizzati correttamente tra Adobe Commerce e la soluzione Store Fulfillment.

**Area funzionale**: Sincronizzazione dell&#39;inventario e degli ordini</br>
**Ruolo:** Amministratore</br>
**Tipo di prova:** Tutto positivo

<table>
<thead>
<tr>
<th>Funzione</th>
<th>Scenario di prova</th>
<th>Risultati attesi</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Aggiungi sorgente di ritiro</strong></td>
<td>Salvare una nuova sorgente di ritiro.</td>
<td>La sincronizzazione in tempo reale invia i dettagli dell'origine al servizio Walmart GIF entro 5 minuti.</td>
</tr>
<tr>
<td><strong>Aggiorna l'origine del ritiro esistente</strong></td>
<td>Salvare gli aggiornamenti a un'origine di ritiro esistente.</td>
<td>L'operazione di sincronizzazione in tempo reale invia i dettagli a Walmart GIF entro 5 minuti</td>
</tr>
<tr>
<td><strong>Fonte di prelievo</br><code>Is Synced</code> status</br><code>Is Synced</code></strong></td>
<td>Salvare gli aggiornamenti a un'origine di ritiro esistente.</td>
<td>Dopo un'operazione riuscita, la <code>Is Synced</code> della colonna della pagina Gestisci origine aggiornamenti da <code>No</code> a <code>Yes</code>.</td>
</tr>
<tr>
<td><strong>Processo di prenotazione delle scorte modificato</strong></td>
<td>Crea e invia un nuovo ordine per un prodotto.</td>
<td>La quantità vendibile del prodotto diminuisce di conseguenza.</td>
</tr>
<tr>
<td><strong>Nuovo ordine push, sincronizzazione API—Ordine cliente</strong></td>
<td>Il cliente invia un ordine di ritiro dal negozio.</td>
<td><ul><li>Nella vista Ordine di amministrazione, un <strong>Utente amministratore Adobe Commerce</strong> visualizza lo stato di Order Sync aggiornato in <code>Sent</code></li><li>Il registro dei dettagli dell’ordine include il messaggio <code>Order was sent to BOPIS solution for sync, it’s not yet acknowledged yet.</code></li></ul></td>
</tr>
<tr>
<td><strong>Nuovo ordine push, sincronizzazione API: l’amministratore invia l’ordine</strong></td>
<td>Un Adobe Commerce <strong>Amministratore</strong> invia un ordine di ritiro.</td>
<td><ul><li>Nella vista Ordine di amministrazione, lo stato Sincronizzazione ordine viene aggiornato a <code>Sent</code>.</li><li>Il registro dei dettagli dell’ordine include il messaggio <code>Order was sent to BOPIS solution for sync, it’s not yet acknowledged yet.</code></li></ul></td>
</tr>
<tr>
<td><strong>Nuovo ordine push, coda eccezioni<strong></td>
<td>Identifica diversi prodotti virtuali e scaricabili nell’amministratore di Adobe Commerce che possono essere soddisfatti tramite Adobe Commerce senza richiedere l’interazione con il servizio Fulfillment (FaaS).</td>
<td>Questi prodotti vengono rimossi o contrassegnati in modo appropriato nell'esportazione per evitare un conflitto a valle con gli FaaS.</td>
</tr>
</tbody>
</table>

### Flussi di lavoro di annullamento ordini

Questa sezione del piano di test include scenari per testare il flusso di lavoro end-to-end per gli ordini annullati tramite Adobe Commerce.

**Area funzionale:** Amministratore Adobe Commerce</br>
**Ruolo:** End-to-end (Amministratore, Store Associate, Cliente)</br>
**Tipo di risultato del test:** Positivo per tutti gli scenari

<table style="table-layout:fixed">
<tr>
<th>Funzione</th>
<th>Scenario</th>
<th>Risultati attesi</th>
</tr>
<tr>
<td><strong>Cancellazione completa dell'ordine</strong></td>
<td><ol>
<li>Ordinare.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verifica la creazione della fattura (se autorizzata e acquisita) la ricezione dell'e-mail della fattura.</li>
<li>Crea nota di accredito con tutti i prodotti ordinati dalla vista Fattura.</li>
</ol>
</td>
<td>
<ul>
<li>Storico degli ordini aggiornato con <code>We refunded $X online. Transaction ID: transactionID</code> e <code>Received Cancel acknowledgment from the BOPIS solution.</code></li>
<li>Lo stato dell'ordine è <code>Closed</code>. (Abbiamo impostato la REVISIONE DEI PAGAMENTI ora.)</li>
<li>Nota di credito creata in Adobe Commerce. (Aspetta che il cron funzioni.)</li>
<li>Se tutti gli elementi selezionati, allora pronto per il ritiro e-mail <code>DISPLAY COMMENT HISTORY</code> show <code>Order is ready for pickup</code> (<code>CUSTOMER NOTIFIED</code> flag è <code>true</code>.)</li>
<li>Se tutti gli elementi non sono stati selezionati, l'e-mail di annullamento e-mail e VISUALIZZA CRONOLOGIA COMMENTO mostra <code>Order has been canceled - all items were not available</code></li>
<li><code>CUSTOMER NOTIFIED</code> flag è <code>true</code>.)</li>
</ul>
</td>
</tr>
<tr><td><strong>Annullamento parziale dell’ordine<strong></td>
<td>
<ol>
<li>Ordinare con almeno due prodotti.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Attendi due ore per il regolamento della transazione.</li>
<li>Crea nota di accredito con solo una parte dei prodotti ordinati dalla vista Fattura.</li>
</td>
<td>
<ul>
<li>Aggiornamento della cronologia degli ordini: <code>We refunded $X online. Transaction ID: transactionID</code></li>
<li>Aggiornamento della cronologia degli ordini: <code>Order notified as partly canceled at: Date and Hour</code></li>
<li>Ricezione del messaggio e-mail di rimborso ordine: <code>$x amount was refunded</code></li>
<li>Lo stato dell'ordine è <code>Processing</code>.</li>
<li>Nota di credito creata in Adobe Commerce (Attendere che il cron funzioni).</li>
<li>Se alcuni elementi non sono stati selezionati, verifica che la [!UICONTROL Ready for Pickup] e-mail con la nilpick o la sezione rimborso viene visualizzata. <code>DISPLAY COMMENT HISTORY</code> show <code>Order is ready for pickup, but some items not available.</code>.</li>
<li><code>CUSTOMER NOTIFIED</code> flag è <code>true</code>.</li>
</ul>
</td>
</tr>
<td><strong>Pronto per il ritiro</br></br>Cancellazione completa</br>(tutti i prodotti sono impostati come raccolti con 0 qty)</br></strong></td>
<td>
<ol>
<li>Effettua l'ordine.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Vai a Postman ed esegui la richiesta Ready for Pickup con tutti i prodotti impostati come <code>picked</code> con <code>0 qty</code>.</li>
</ol>
</td>
<td>
<ul>
<li>Storico ordini aggiornato: <code>We refunded $X offline</code></li>
<li>Lo stato dell'ordine è <code>CLOSED</code>.
<li>Viene creata la nota di accredito. (Aspetta che il cron funzioni.)</li>
<li>E-mail di rimborso ricevuta: <code>$x amount was refunded</code></li>
<li>Messaggio e-mail di annullamento ordine inviato.</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Pronto per il ritiro - Annullamento parziale</strong></br></br><strong>(Alcuni prodotti vengono raccolti e alcuni vengono raccolti con <code>0 qty</code>)</strong>
</td>
<td>
<ol>
<li>Effettua l'ordine.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Vai a Postman ed esegui la richiesta Ready for Pickup con parte dei prodotti impostati come raccolto con 0 qty e gli altri selezionati.</li>
</ol>
</td>
<td>
<ul>
<li><code>Your order is ready for pickup</code> con [!UICONTROL Ready for Pickup Items] e [!UICONTROL Canceled Items] tabelle. </li>
<li>Lo stato dell'ordine è PRONTO PER IL PICKUP. </li>
<li>Storico ordini aggiornato: <code>We refunded $X offline.</code>
<li>Storico ordini aggiornato: <code>Order notified as partly canceled at: Date and hour</code>
<li>E-mail di rimborso ricevuta: <code>$x amount was refunded</code>
<li>Viene creata la nota di accredito. (Aspetta che il cron funzioni.)</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Pronto per il pickup - Annullamento parziale</br></br>Alcuni prodotti sono raccolti e alcuni sono raccolti con <code>0 qty</code>)</strong>
</td>
<td><ol>
<li>Effettua l'ordine.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Vai a Postman ed esegui la richiesta Ready for Pickup con parte dei prodotti impostati come raccolto con 0 qty e gli altri selezionati.</li>
</ol>
</td>
<td><ul>
<li><code>Your order is ready for pickup</code> con [!UICONTROL Ready for Pickup Items] e [!UICONTROL Canceled Items] tabelle. </li>
<li>Lo stato dell'ordine è PRONTO PER IL PICKUP. </li>
<li>Storico ordini aggiornato: <code>We refunded $X offline.</code>
<li>Storico ordini aggiornato: <code>Order notified as partly canceled at: Date and hour</code>
<li>E-mail di rimborso ricevuta: <code>$x amount was refunded</code>
<li>Viene creata la nota di accredito. (Aspetta che il cron funzioni.)</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Dispensato (durante la dispensa) </br></br>Cancellazione completa (tutti i prodotti sono impostati come rifiutati)</strong>
</td>
<td>
<ol>
<li>Effettua l'ordine.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Vai a Postman ed esegui la richiesta Ready for Pickup con tutti i prodotti impostati come selezionati.</li>
<li>Apri la tua cassetta postale, trova l'e-mail Ready for Pickup. Quindi fai clic su **[!UICONTROL Confirm Arrival]**</li>
<li>Consegna.</li>
<li>Vai a Postman ed esegui la richiesta Dispensed con tutti i prodotti impostati come rifiutati.</li>
</ol>
<td><ul>
<li>Storico ordini aggiornato: <code>We refunded $X offline.</code></li>
<li>E-mail di rimborso ricevuta: <code>$x amount was refunded</code></li>
<li>Stato impostato su <code>CLOSED</code>.</li>
<li>Nota di accredito creata. (Aspetta che il cron funzioni.)</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Dispensato (durante la dispensa)</br></br>Annullamento parziale</br>(alcuni prodotti sono dispensati; alcuni sono respinti.)</strong>
</br></td>
<td>
<ol>
<li>Effettua l'ordine.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Vai a Postman ed esegui la richiesta Ready for Pickup con tutti i prodotti impostati come selezionati.</li>
<li>Apri la tua cassetta postale. Trova il messaggio e-mail pronto per il ritiro e seleziona <code>Confirm Arrival</code>.</li>
<li>Consegna.</li>
<li>Vai a Postman ed esegui la richiesta Dispensed con alcuni prodotti impostati per essere distribuiti e alcuni impostati per essere rifiutati</li>
</ol>
</td>
<td>
<li>Storico ordini aggiornato: <code>We refunded $X offline</code></li>
<li><code>Order notified as partly canceled at: Date and Hour</code>
<li>E-mail di rimborso ricevuta: <code>$x amount was refunded</code>
<li>Stato ordine impostato su <code>Ready for pickup Dispensed</code>
<li>Nota di accredito creata. (Aspetta che il cron funzioni.)</li>
</td>
</tr>
<tr>
<td> <strong>Nuovo RMA dopo ritorno (completo)</strong>
</td>
<td>
<ol>
<li>Effettua l'ordine.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Scegli tutti i prodotti con Postman.</li>
<li>Consegna.</li>
<li>Faccia una spesa.</li>
<li>Vai all'ordine e seleziona<strong>[!UICONTROL Create returns]=
<li>Creare l’RMA.</li>
</ol>
</td>
<td>
<ul>
<li>La RMA è stata creata e viene visualizzata sotto la <strong>[!UICONTROL Returns]</b> nella vista Ordine.</li>
<li>Il cliente ha ricevuto un'e-mail di conferma RMA.</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Nuovo RMA dopo il ritorno — Parziale</strong>
</td>
<td>
<ol>
<li>Effettua l'ordine.</li>
<li>Attendi la sincronizzazione dell’ordine.</li>
<li>Verificare che la fattura sia stata creata (se autorizzata e acquisita) e che sia stata ricevuta l'e-mail della fattura.</li>
<li>Scegli tutti i prodotti con Postman.</li>
<li>Consegna.</li>
<li>Faccia una spesa.</li>
<li>Vai all'ordine e seleziona  <strong>[!UICONTROL Create returns]</strong></li>
<li>Crea la RMA con parte dei prodotti ordinati.</li>
</ol>
<td>
<ul>
<li>RMA creato e visualizzato sotto <strong>[!UICONTROL Returns]</strong> nella vista Ordine.</li>
<li>Il cliente ha ricevuto l’e-mail di conferma RMA.</li>
<li>Dopo aver creato RMA, ottieni l'autorizzazione RMA: Dall’amministratore, vai a <strong>[!UICONTROL Sales > Returns]</strong>. Selezionare l’RMA creato e autorizzarlo.</li>
<li>Verifica che il cliente abbia ricevuto l’e-mail di conferma dell’autorizzazione RMA.</li>
<li>Verificare che il rimborso sia stato aggiunto alle transazioni e alla cronologia degli ordini.</li>
</ul>
</td>
</tr>
</table>


### Autorizzazioni per l&#39;app per l&#39;evasione dell&#39;archivio

Questa sezione del piano di test riguarda la gestione dell&#39;account per gli utenti delle app che eseguono lo store.

- Conferma che un associato dello store può eseguire l&#39;autenticazione con un nuovo account utente creato dall&#39;amministratore di Adobe Commerce.
- Conferma che gli aggiornamenti agli account esistenti siano stati applicati correttamente.

**Area funzionale:** Amministratore Adobe Commerce</br>
**Ruolo:** Amministratore, archivia associato</br>
**Tipo di prova:** Tutto positivo

<table style="table-layout:auto">
<tr>
<th>Funzione</th>
<th>Scenario</th>
<th>Risultati attesi</th>
</tr>
<tr>
<td><strong>Gestione account utente - Crea account</strong></br></br>
</td>
<td>
<ol>
<li><strong>Amministratore</strong> — Accedi all'amministratore di Adobe Commerce</li>
<li>Vai a <strong>[!UICONTROL System] &gt; Memorizza autorizzazioni app conformi &gt; Tutti gli utenti dell'app che esegue l'evasione dell'archivio</strong></li>
<li><strong>Aggiungi nuovo utente.</strong></li>
</ol>
<td>
<ul>
<li>Creazione account completata.</li>
<li>Il nuovo account utente viene visualizzato nel [!UICONTROL Store Fulfillment Users] dashboard.</li>
<li><strong>Associato store</strong> accedi all'app Store Assist con un nuovo account utente.</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Gestione account utente - Aggiorna account utente esistente</strong>
</td>
<td>
<ol>
<li>Accedi all’amministratore di Adobe Commerce con l’account utente Admin.</li>
<li>Vai a <strong>[!UICONTROL System] &gt; Memorizza autorizzazioni app conformi &gt; Tutti gli utenti dell'app che esegue l'evasione dell'archivio</strong>.</li>
<li>Nell'elenco Account utente, apri un account utente attivo esistente selezionando <strong>[!UICONTROL Edit]</strong>.
<li>Disattiva l'account modificando <strong>[!UICONTROL Is Active]</strong> a <strong>No</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Sulla <strong>[!UICONTROL Store Fulfillment App Users]</strong> dashboard, lo stato dell’account aggiornato è stato modificato in <strong>[!UICONTROL Inactive]</strong>.</li>
<li>Store Associate non può accedere all'app Store Assist con le credenziali account inattive.</li>
</ul>
</td>
</tr>
</table>

## Tipi di prodotti Adobe Commerce

Gli scenari di test per i tipi di prodotto Adobe Commerce verificano che i clienti visualizzino le informazioni corrette sul prodotto, sulle scorte e sui metodi di consegna per diversi tipi di prodotto:

- [!UICONTROL Configurable]
- [!UICONTROL Grouped]
- [!UICONTROL Virtual]
- [!UICONTROL Bundle products] nella vetrina Adobe Commerce.

**Area funzionale:** Adobe Commerce Frontend</br>
**Ruolo:** Utente app di assistenza store (associato store)</br>
**Tipo di prova:** Tutto positivo

<table style="table-layout:auto">
<tr>
<th>Funzione</th>
<th>Scenario</th>
<th>Commenti</th>
</tr>
<tr>
<td><strong>Prodotti configurabili</strong>
</td>
<td>
<ul>
<li>Verifica che l'utente possa vedere solo le opzioni configurabili, quale origine è abilitata, le risorse sono assegnate e che ci siano alcuni elementi in magazzino - controlla i prodotti secondari.</li>
<li>Verifica che quando selezioni un archivio diverso, le opzioni non disponibili siano visualizzate come incrociate.</li>
<li>Verifica che se l'utente seleziona un archivio diverso, le opzioni configurabili non siano selezionate.</li>
<li>Verifica che se un prodotto configurabile è già nel carrello e un utente seleziona un negozio diverso, il prodotto mostra come esaurito.</li>
</ul>
</td>
<td></td>
</td>
</tr>
<tr>
<td><strong>Prodotti raggruppati</strong>
</td>
<td>
<ul>
<li>Verifica che i metodi di consegna e [!UICONTROL Add to cart] sono disattivati per il cliente quando tutti i prodotti figlio hanno
<code>qty</code> impostato su <code>0</code>.</li>
<li>Verifica che i metodi di consegna siano abilitati per il cliente quando almeno uno dei prodotti secondari ha <code>qty</code> impostato su <code>0.</code></li>
<li>Verifica che [!UICONTROL Store Pickup Delivery] il metodo è visibile e attivo solo per i prodotti che hanno [!UICONTROL Available for Store Pickup] abilitato. (Controllare il prodotto figlio.)</li>
</ul>
</td>
<td></td>
</tr>
<tr>
<td><strong>Prodotti virtuali</strong>
</td>
<td>
Verifica che i prodotti virtuali non offrano  [!UICONTROL In-store Pickup] metodo di consegna.
<td></td>
</td>
</tr>
<tr>
<td><strong>Bundle prodotti</strong>
</td>
<td>
<ul>
<li>Verifica se almeno un prodotto figlio ha [!UICONTROL Available for Store Pickup] disabilitata, l’opzione di consegna del ritiro dal negozio non è disponibile per il cliente.</li>
<li>Verifica se almeno un prodotto figlio ha [!UICONTROL Available for Home Delivery] disabilitata, l’opzione Consegna iniziale non è disponibile per il cliente.</li>
<li>Verifica che almeno uno dei prodotti secondari in un bundle sia esaurito, che il bundle (prodotto principale) sia visualizzato come [!UICONTROL Out of stock].</li>
</ul>
</td>
<td></td>
</tr>
<tbody>
</table>

## Esperienza di check-in

Questa sezione del piano di test copre l’esperienza di archiviazione per gli ordini di pagamento del Negozio per le seguenti funzionalità:

- Contatto di ritiro alternativo: verifica il flusso di lavoro per l’aggiunta di un [!UICONTROL Alternate Pickup Contact] e selezionando una [!UICONTROL Preferred Contact] su ordini di ritiro dal negozio.

- Modulo di archiviazione - Verifica il flusso di lavoro per l&#39;invio di una richiesta di archiviazione per gli ordini di ritiro dal negozio.

**Aree funzionali:** Pagamento carrello, Modulo di pagamento per ordini di ritiro dal negozio</br>
**Ruolo:** Amministratore, cliente, associato store</br>
**Tipo di prova:** Tutto positivo

### Contatto di prelievo alternativo


**Area funzionale:** Pagamento carrello</br>
**Ruolo:** Cliente</br>
**Tipo di prova:** Tutto positivo

<table style="table-layout:auto">
<tr>
<th>Funzione</th>
<th>Scenario</th>
<th>Risultati attesi</th>
</tr>
<tr>
<td><strong>Contatto di prelievo alternativo</br>
Consegna</br><strong>
</td>
<td>
Un cliente invia un ordine con l’opzione In-Store Pickup.</td>
<td>Durante il processo di pagamento, il cliente visualizza il [!UICONTROL Alternate Pickup Contact] l’opzione relativa al passaggio Spedizione.
</td>
</tr>
<tr>
<td><strong>Contatto preferito alternativo di prelievo, archiviazione</strong>
<td>
Un cliente invia un ordine con l’opzione In-Store Pickup. Durante il pagamento, il cliente aggiunge un [!UICONTROL Alternate Pickup Contact].</td>
<td>Durante il processo di pagamento, il cliente visualizza il [!UICONTROL Preferred Contact] opzione sulla fase di spedizione.</td>
</td>
</tr>
<tr>
<td><strong>Contatto alternativo di recupero, Check-in</strong>
</td>
<td>
Un cliente invia un ordine con l’opzione In-Store Pickup. Durante il pagamento, il cliente seleziona [!UICONTROL Alternate Pickup Contact] nella fase di spedizione.
</td>
<td>Il cliente visualizza le opzioni di input per inserire i dettagli del contatto: [!UICONTROL First name], [!UICONTROL Last name], [!UICONTROL Phone]e [!UICONTROL Email].</td>
</tr>
<tr>
<td><strong>Ritiro alternativo, archiviazione e-mail</strong>
</td>
<td>Un cliente invia un ordine con l’opzione In-Store Pickup. Durante il pagamento, il cliente seleziona [!UICONTROL Alternate Pickup Contact] nella fase di spedizione, aggiunge i dettagli del contatto e invia l'ordine.</td>
<td>Sia il cliente che il contatto alternativo ricevono un'e-mail di check-in per l'ordine.</td>
</tr>
<td><strong>Pickup alternativo, dettaglio dell’ordine</strong></td>
<td>Un cliente invia un ordine con l’opzione In-Store Pickup. Durante il pagamento, il cliente seleziona [!UICONTROL Alternate Pickup Contact] nella fase di spedizione, aggiunge i dettagli del contatto e invia l'ordine.</td>
<td>L’amministratore visualizza le informazioni di contatto aggiuntive sull’ordine salvato.</td>
</tr>
<tr>
<td><strong>Contatto di prelievo alternativo, archivia visualizzazione ordine associato</strong>
</td>
<td>Un cliente invia un ordine con l’opzione In-Store Pickup. Durante il pagamento, il cliente seleziona [!UICONTROL Alternate Pickup Contact] nella fase di spedizione, aggiunge i dettagli del contatto e invia l'ordine.</td>
<td>L'Associazione Store può vedere le informazioni di contatto aggiuntive sull'ordine in FaaS/ChaaS.</td>
</td>
</tr>
</tbody>
</table>

### Modulo di check-in


**Area funzionale:** Modulo di archiviazione</br>
**Ruolo:** Cliente</br>
**Tipo di prova:** Tutto positivo

<table style="table-layout:auto">
<tr>
<th>Funzione</th>
<th>Scenario</th>
<th>Risultati attesi</th>
</tr>
<tr>
<td><strong>Azione Check-in - Invia richiesta</strong>
</td>
<td>Nel modulo di archiviazione, un cliente completa tutti i campi obbligatori e invia la richiesta.</td>
<td>Il cliente riceve una risposta di successo.</td>
</tr>
<tr>
<td><strong>Azione Check-in: visualizza i dettagli della richiesta</strong></td>
<td>Invio di una richiesta di archiviazione completato da un cliente.</td>
<td>Lo stato dell'ordine viene aggiornato nel sistema FaaS e Store Associate può vedere i dettagli della richiesta di check-in nei FaaS.
</td>
</tr>
<tr>
<td><strong>Azione di archiviazione: invia la richiesta una sola volta</strong></td>
<td>Dopo aver inviato una richiesta di archiviazione per un ordine, un cliente seleziona il collegamento per effettuare il check-in una seconda volta.</td>
<td>Nel modulo di Check-In, il cliente non vede un’opzione per modificare o inviare nuovamente il modulo.</td>
</tr>
<tr>
<td><strong>Check-in Action - Conferma arrivo</strong></td>
<td>Un ordine di ritiro in negozio è contrassegnato pronto per il ritiro nei FaaS. Il cliente riceve un messaggio e-mail pronto per il ritiro e seleziona [!UICONTROL Confirm Arrival].</td>
<td>Il cliente visualizza il modulo di Check-In per l'ordine.</td>
</tr>
</tbody>
</table>

## App Store Assist

Questa sezione del piano di test tratta gli scenari per testare i flussi di lavoro relativi a ordine, prelievo e consegna nell’app Store Assist.

**Area funzionale:** App Store Assist</br>
**Ruolo:** Associato store</br>
**Tipo di prova:** Tutto positivo

<table style="table-layout:auto">
<tr>
<th>Funzione</th>
<th>Scenario</th>
<th>Risultati attesi</th>
</tr>
<tr>
<td>
<strong>Selezione ordine singolo: percorso felice, ritiro curbside</strong></td>
<td>Scegliere articoli singoli e multipli. Nessun nilpicks, e pick-up a bordo del marciapiede (con staging).
</td>
<td>
</td>
</tr>
<tr>
<td><strong>Selezione multi ordine: percorso felice, ritiro curbside</strong></td>
<td>Articoli singoli e multipli. Nessun nilpicks, e pick-up a bordo nudo (con staging)</td>
<td></td>
</tr>
<tr>
<td><strong>Selezione ordine singolo: percorso felice in negozio pick-up</strong></td>
<td>Articoli singoli e multipli. Nessun nilpicks, e l'installazione di pick-up (con staging)</td>
<td>
</td>
</tr>
<tr>
<td><strong>Selezione multi ordine: percorso felice, ritiro in negozio</strong></td>
<td>Scegliere articoli singoli e multipli. Nessun nilpicks, e pick-up a bordo del marciapiede (con staging).</td>
<td></td>
</tr>
<tr>
<td><strong>Selezione ordine singolo - percorso non felice, ritiro in negozio</strong></td>
<td>Scegli articoli singoli e multipli con prelievo parziale e nilpick e istore (con staging)</td>
</td>
<td></td>
</tr>
<td><strong>Raccolta ordini multipli - non felice ritiro percorso-curbside</strong></td>
<td>Scegli articoli singoli e multipli con prelievo parziale e nilpick e istore (con staging)</td>
<td></td>
</tr>
<td><strong>Selezione ordine singolo - percorso non felice, ritiro curbside</strong></td>
<td>Scegli articoli singoli e multipli con prelievo parziale e nilpick e curbside (con staging)</strong></td>
</td>
<td></td>
</tr>
<tr><td><strong>Ordine inserito - annullato prima del prelievo</strong></td>
<td></td>
<td></td>
</tr>
<tr>
<td><strong>Ordine inserito - annullato prima della consegna</strong></td>
<td></td>
<td></td>
</tr>
<tr>
<td><strong>Ordine inserito - ricerca nel modulo ordine</strong></td>
<td></td>
<td></td>
</tr>
<tr><td><strong>Ordine inserito - ricerca e check-in manuale per la consegna</strong></td>
<td></td>
<td></td>
</tr>
<tr><td><strong>Ordine inserito - tutti gli elementi selezionati o non disponibili contrassegnati dal selettore</strong></td>
<td></td>
<td></td></tr>
<tr><td><strong>Ordine inserito con elementi bundle - prelievo e consegna</strong></td>
<td></td>
<td></td></tr>
<tr><td><strong>Ordine posto - Consegna con rigetto</strong></td>
<td></td>
<td></td></tr>
<tr><td><strong>Ordine posto - Consegna con rifiuto di tutti gli articoli</strong></td>
<td></td>
<td></td></tr>
</tbody>
</table>

## Distribuzione

Dopo aver verificato che la soluzione sia stata configurata e testata in base alle specifiche, puoi distribuirla dalla fase di staging alla produzione.

L&#39;implementazione e il test variano a seconda dell&#39;infrastruttura e delle funzionalità.

>[!TIP]
>
>Per le linee guida per la distribuzione, le liste di controllo e le best practice per Adobe Commerce sui progetti di infrastruttura cloud, consulta [Distribuzione dello store](https://devdocs.magento.com/cloud/live/stage-prod-live.html) nella documentazione per sviluppatori di Adobe Commerce.
