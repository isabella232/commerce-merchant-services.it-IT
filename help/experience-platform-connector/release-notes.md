---
title: Note sulla versione
description: Informazioni aggiornate sulla versione del connettore Adobe Experience Platform da Adobe Commerce.
exl-id: 7636664b-488a-46f7-8d19-a9faac126aec
feature: Personalization, Integration, Release Notes
source-git-commit: 1d8609a607e0bcb74fdef47fb8e4e582085836e2
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 2%

---

# Note sulla versione

Queste note sulla versione contengono aggiornamenti al connettore Experienci Platform e includono:

* ![Nuovo](../assets/new.svg) - Nuove funzioni
* ![Correzione](../assets/fix.svg) - Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) - Problemi noti

Per modifiche e correzioni di funzionalità relative alle estensioni utilizzate dal connettore Experienci Platform, vedi **Aggiornamenti dei servizi supportati**.

Consulta [Prossime versioni](https://experienceleague.adobe.com/docs/commerce-operations/release/planning/schedule.html) per informazioni sulle pianificazioni delle versioni e sul supporto.

Consulta la documentazione per gli sviluppatori per [informazioni sulla compatibilità dei prodotti](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).

## Aggiornamenti dei servizi supportati

Queste note sulla versione descrivono modifiche e correzioni di funzioni relative alle estensioni utilizzate dal connettore Experienci Platform.

+++Aggiornamenti dei servizi supportati

_10 giugno 2023_

* ![Correzione](../assets/fix.svg) - È stato risolto un problema che si verificava quando `orderId` non passava nel contesto a causa di prefissi nell’identificatore dell’ordine Commerce.
* ![Correzione](../assets/fix.svg) - Configurazioni criteri per la sicurezza dei contenuti aggiornate.

_30 marzo 2023_

* ![Nuovo](../assets/new.svg) - Aggiunta di una nuova estensione denominata `data-services-b2b` che include [eventi elenco richieste di acquisto](events.md#b2b-events) per gli esercenti B2B.
* ![Nuovo](../assets/new.svg) - Aggiunto il `uniqueIdentifier` campo a [ricerca](events.md#search-events) eventi. Questo nuovo campo consente ai commercianti di fare riferimento incrociato alle richieste di ricerca corrispondenti alle risposte di ricerca.

_12 ottobre 2022_

* ![Nuovo](../assets/new.svg) - Aggiunti due [eventi vetrina](events.md): `openCart` e `removeFromCart` all’SDK e all’agente di raccolta degli eventi Adobe Commerce Storefront.
* ![Nuovo](../assets/new.svg) - Aggiunta del supporto per [Vetrina AEM](overview.md#aem-support).

+++

## 2.3.0

_27 giugno 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Aggiunta la possibilità di [disattivare l&#39;invio di eventi storefront](connect-data.md#data-collection) all&#39;Experience Platform.
* ![Correzione](../assets/fix.svg) - Configurazioni criteri per la sicurezza dei contenuti aggiornate.
* ![Correzione](../assets/fix.svg) - È stato corretto il supporto per gli eventi di back office nella versione 2.4.7 di Commerce.
* ![Nuovo](../assets/new.svg) - È stato aggiunto un messaggio di notifica sull’annullamento della validità della cache quando si salvano le modifiche apportate al modulo del connettore Experienci Platform.


## 3.0.0-beta1 (solo interno)

_13 giugno 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - (Beta) Aggiunta la possibilità di [invia ordine storico](connect-data.md#beta-send-historical-order-data) dati e stato dell’Experience Platform. Questa funzione è disponibile solo per gli utenti beta. Per partecipare alla versione beta, invia un’e-mail al seguente indirizzo: [dataconnection@adobe.com](mailto:dataconnection@adobe.com).

## 2.2.0

_30 marzo 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Il pacchetto `commerce-data-export` e `saas-export` dipendenze con `experience-platform-connector` estensione. In precedenza, era necessario installare queste dipendenze separatamente. Queste dipendenze, insieme alla configurazione dell’esercente, consentono l’elaborazione lato server di [eventi di back office](events.md#back-office-events).
* ![Nuovo](../assets/new.svg) - È stato aggiunto un nuovo evento back office denominato [`orderShipmentCompleted`](events.md#ordershipmentcompleted).

## 2.1.1

_28 febbraio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Aggiunta del supporto per PHP 8.2 per tutte le estensioni del connettore di Experience Platform.

## 2.1.0

_17 gennaio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Aggiornato il [Amministratore connettore di Experience Platform](connect-data.md) in modo da poter specificare il proprio AEP Web SDK (alloy).
* ![Correzione](../assets/fix.svg) È stato modificato in utilizzando `identityMap` invece di `personID` quando si imposta l’identità primaria per tutti i dati inviati al server Edge di.

## 2.0.1

_10 novembre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Problema risolto](../assets/fix.svg) - Ora il contesto Adobe Experience Platform viene impostato solo dopo il caricamento di Storefront Event Collector e Storefront Event SDK.

## 2.0.0

_12 ottobre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Aggiunta la possibilità di specificare il proprio Web SDK AEP quando [connessione](connect-data.md) la tua istanza di Adobe Commerce all’Experience Platform.
* ![Correzione](../assets/fix.svg) : è stato aggiornato il requisito dell’ambito dello stream di dati in modo che gli ID dello stream di dati debbano avere l’ambito del sito web anziché della visualizzazione archivio.

## 1.0.0

_9 agosto 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Versione di disponibilità generale.
