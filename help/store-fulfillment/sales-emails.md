---
title: E-mail di vendita
description: Configura le impostazioni per i modelli e-mail transazionali per comunicare con i clienti e gli amministratori degli archivi durante il processo di ordine e evasione.
role: User, Admin
level: Intermediate
exl-id: 688732e3-06f0-4613-a589-2d465597eb28
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 0%

---

# E-mail di vendita

Store Fulfillment offre un set esteso di modelli e-mail transazionali per supportare i flussi di lavoro di ordine e di evasione. Offrono comunicazioni e messaggi coerenti e automatizzati su tutti i canali, informando gli amministratori di clienti e negozi circa le modifiche dello stato dell&#39;ordine, le istruzioni per gli ordini di ritiro in negozio e altro ancora.

I modelli e-mail di evasione archivio sono configurati con messaggi e impostazioni predefiniti. Gli amministratori merchant in Adobe Commerce possono gestire e modificare le configurazioni e selezionare i modelli e-mail per comunicare con i clienti in scenari diversi. Gli amministratori possono configurare e personalizzare anche i modelli.

Configura i modelli e-mail di vendita dall’amministratore: **[!UICONTROL Stores > Configuration > Sales > Sales Emails]**.

## E-mail - Impostazioni generali

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
<td><strong>Invio asincrono</strong></td>
<td>Disattiva questa funzione. L’invio di e-mail asincrone non è supportato. Per il tempo di comunicazione e risposta più veloce per Store Pickup, invia immediatamente le e-mail invece di fare il batch. </td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>

## Ordine pronto per il ritiro nel negozio

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
<td><strong>Abilitato</strong></td>
<td>Questa e-mail viene inviata al cliente quando il dipendente del negozio ha completato il prelievo dell'ordine. Imposta su "No" per disabilitare la notifica e-mail. Se il modello e-mail è disabilitato, non impedisce che un ordine venga scelto dall'associazione store.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Ordine Pronto Per Il Mittente E-Mail Di Ritiro</strong></td>
<td>L’identità del mittente utilizzata per l’invio della notifica e-mail.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Modello E-Mail Per Ordine Pronto Per Il Recupero</strong></td>
<td>Il modello di messaggio e-mail utilizzato per avvisare i clienti registrati. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<td><strong>Modello e-mail pronto per il prelievo per il cliente</strong></td>
<td>Modello di messaggio e-mail utilizzato per avvisare i clienti ospiti. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Modello e-mail pronto per il prelievo per il contatto alternativo di prelievo</strong></td>
<td>Il modello di messaggio e-mail utilizzato per inviare una notifica ai contatti aggiuntivi denominati nell’ordine. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Invia ordine pronto per la copia dell'e-mail di recupero in</strong></td>
<td>Un elenco di indirizzi e-mail delimitati da virgole per inviare una copia di ogni notifica.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Invia ordine pronto per il metodo di copia dell'e-mail di recupero</strong></td>
<td>Il metodo dell'email "copia di carbonio" invia all'uso.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>


## L&#39;ordine è stato prelevato nel Negozio

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
<td><strong>Abilitato</strong></td>
<td>Questa e-mail viene inviata al cliente quando per confermare che ha ritirato il proprio ordine dal negozio. Imposta su "No" per disabilitare la notifica e-mail. Se il modello e-mail è disabilitato, non impedisce che un ordine venga prelevato dal cliente.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>L’Ordine È Stato Ritirato Dal Mittente E-Mail</strong></td>
<td>L’identità del mittente utilizzata per l’invio della notifica e-mail.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Ordine Selezionato Modello E-Mail</strong></td>
<td>Il modello di messaggio e-mail utilizzato per avvisare i clienti registrati. L’integrazione fornisce un modello predefinito</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<td><strong>Ordine selezionato Modello e-mail per guest</strong></td>
<td>Modello di messaggio e-mail utilizzato per avvisare i clienti ospiti. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Invia È Stata Selezionata Copia E-Mail In</strong></td>
<td>Un elenco di indirizzi e-mail delimitati da virgole per inviare una copia di ogni notifica.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Invia È Stato Ritirato Metodo Di Copia E-Mail</strong></td>
<td>Il metodo dell'email "copia di carbonio" inviare per utilizzare.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>

## Ordine ritardato

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
<td><strong>Abilitato</strong></td>
<td>Questo messaggio e-mail viene inviato al cliente per informarlo di un ritardo nell'elaborazione o nel prelievo dell'ordine presso il negozio commerciale. Imposta su "No" per disabilitare la notifica e-mail. Se il modello e-mail è disabilitato, la funzione non impedisce il ritardo di un ordine.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Mittente e-mail ritardata ordine
</strong></td>
<td>L’identità del mittente utilizzata per l’invio della notifica e-mail.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Modello e-mail ritardato ordine</strong></td>
<td>Il modello di messaggio e-mail utilizzato per avvisare i clienti registrati. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<td><strong>Modello e-mail ritardata ordine per ospite</strong></td>
<td>Modello di messaggio e-mail utilizzato per avvisare i clienti ospiti. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Invia una copia ritardata dell’e-mail a</strong></td>
<td>Un elenco di indirizzi e-mail delimitati da virgole per inviare una copia di ogni notifica.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Metodo di copia ritardata dell'ordine di invio</strong></td>
<td>Il metodo dell'email "copia di carbonio" inviare per utilizzare.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>



## Ordine annullato

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
<td><strong>Abilitato</strong></td>
<td>Questa e-mail viene inviata al cliente per avvisarlo che il loro ordine è stato annullato al negozio commerciale. Imposta su <code>No</code> per disattivare la notifica e-mail. Se il modello e-mail è disabilitato, la funzione non impedisce l’annullamento di un ordine.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Mittente e-mail annullato ordine
</strong></td>
<td>L’identità del mittente utilizzata per l’invio della notifica e-mail.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Modello e-mail annullato ordine</strong></td>
<td>Il modello di messaggio e-mail utilizzato per avvisare i clienti registrati. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<td><strong>Ordine annullato per ospite</strong></td>
<td>Modello di messaggio e-mail utilizzato per avvisare i clienti ospiti. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Invia copia e-mail annullata a</strong></td>
<td>Un elenco di indirizzi e-mail delimitati da virgole per inviare una copia di ogni notifica.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Metodo di copia annullato dell'ordine di invio</strong></td>
<td>Il metodo dell'email "copia di carbonio" inviare per utilizzare.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>


## Ordine parzialmente annullato

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
<td><strong>Abilitato</strong></td>
<td>Questa e-mail viene inviata al cliente per avvisarlo che parte del loro ordine è stato annullato al negozio commerciale. Imposta su <code>No</code> per disattivare la notifica e-mail. Se il modello e-mail è disabilitato, non impedisce che un ordine venga parzialmente annullato.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Ordine del mittente e-mail parzialmente annullato
</strong></td>
<td>L’identità del mittente utilizzata per l’invio della notifica e-mail.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Modello e-mail parzialmente annullato</strong></td>
<td>Il modello di messaggio e-mail utilizzato per avvisare i clienti registrati. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<td><strong>Ordine Modello e-mail parzialmente annullato per contattaci alternativo</strong></td>
<td>Il modello di messaggio e-mail utilizzato per inviare una notifica ai contatti aggiuntivi denominati nell’ordine. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Ordine parzialmente annullato per ospite</strong></td>
<td>Modello di messaggio e-mail utilizzato per avvisare i clienti ospiti. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Invia copia e-mail parzialmente annullata a</strong></td>
<td>Un elenco di indirizzi e-mail delimitati da virgole per inviare una copia di ogni notifica.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Metodo di copia parzialmente annullato dell'ordine di invio</strong></td>
<td>Il metodo dell'email "copia di carbonio" inviare per utilizzare.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>

## Spedisci al negozio

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
<td><strong>L'ordine ha spedito per memorizzare i prodotti Mittente e-mail</strong></td>
<td>Invia e-mail a personale commerciale specificato come rapporto aggregato di tutti gli ordini aperti che non possono essere raccolti in un negozio commerciale fino a quando il loro inventario non è disponibile. </br></br> I commercianti possono utilizzare questo rapporto per avviare e gestire trasferimenti di inventario da negozio a negozio o rifornimento. </br></br>Questa notifica si applica solo quando [!DNL Ship-to-Store] le funzioni sono abilitate.
</br></br>Questa etichetta non influisce sul vettore di spedizione selezionato o sulle relative etichette del metodo di spedizione disponibili.</br></br></td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Destinatari e-mail di spedizione</strong></td>
<td>Un elenco di indirizzi e-mail delimitati da virgole per inviare una copia di ogni notifica.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
<tr>
<td><strong>Modello e-mail</strong></td>
<td>Modello di messaggio e-mail utilizzato per inviare notifiche ai destinatari. L’integrazione fornisce un modello predefinito.</td>
<td>Visualizzazione store</td>
<td>No</td>
</tr>
</tbody></table>

>[!NOTE]
>
>Se consenti ordini arretrati, devi fornire un indirizzo e-mail amministratore per ricevere notifiche su questi ordini. Aggiungi l’indirizzo alle seguenti impostazioni di configurazione: **[!UICONTROL Send Order Delayed Email Copy To]** in [Ritardo ordine](#order-delayed) modello e [!UICONTROL Ship To Store Email Recipients] in [Spedisci al negozio](#ship-to-store) modello.



