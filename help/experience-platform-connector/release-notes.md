---
title: Note sulla versione
description: Informazioni aggiornate sulla versione del connettore Adobe Experience Platform da Adobe Commerce.
exl-id: 7636664b-488a-46f7-8d19-a9faac126aec
source-git-commit: 22823b662eefa953fcca6ae78f6c37ee8abff3d1
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# Note sulla versione

Queste note sulla versione contengono aggiornamenti al connettore Experience Platform e includono:

* ![Nuovo](../assets/new.svg) - Nuove funzioni
* ![Correzione](../assets/fix.svg) - Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) - Problemi noti

Per modifiche e correzioni di funzionalità relative alle estensioni utilizzate dal connettore Experience Platform, vedi **Aggiornamenti dei servizi supportati**.

Consulta [Prossime versioni](https://experienceleague.adobe.com/docs/commerce-operations/release/planning/schedule.html) per informazioni sulle pianificazioni delle versioni e sul supporto.

Consulta la documentazione per gli sviluppatori per [informazioni sulla compatibilità dei prodotti](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).

## Aggiornamenti dei servizi supportati

Queste note sulla versione descrivono modifiche e correzioni di funzioni relative alle estensioni utilizzate dal connettore Experience Platform.

+++Aggiornamenti dei servizi supportati

_30 marzo 2023_

* ![Nuovo](../assets/new.svg) - Aggiunta di una nuova estensione denominata `data-services-b2b` che include [eventi elenco richieste di acquisto](events.md#b2b-events) per gli esercenti B2B
* ![Nuovo](../assets/new.svg) - Aggiunto il `uniqueIdentifier` campo a [ricerca](events.md#search-events) eventi. Questo nuovo campo consente ai commercianti di fare riferimento incrociato alle richieste di ricerca corrispondenti alle risposte di ricerca.

_12 ottobre 2022_

* ![Nuovo](../assets/new.svg) - Aggiunti due [eventi vetrina](events.md): `openCart` e `removeFromCart` all’SDK e all’agente di raccolta degli eventi Adobe Commerce Storefront
* ![Nuovo](../assets/new.svg) - Aggiunta del supporto per [Vetrina AEM](overview.md#aem-support)

+++

## 2.2.0

_30 marzo 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Il pacchetto `commerce-data-export` e `saas-export` dipendenze con `experience-platform-connector` estensione. In precedenza, era necessario installare queste dipendenze separatamente. Queste dipendenze, insieme alla configurazione dell’esercente, consentono l’elaborazione lato server di [eventi di back office](events.md#back-office-events).
* ![Nuovo](../assets/new.svg) - È stato aggiunto un nuovo evento back office denominato [`orderShipmentCompleted`](events.md#ordershipmentcompleted).

## 2.1.1

_28 febbraio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Supporto di PHP 8.2 per tutti i moduli di connettori di Experience Platform

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

* ![Nuovo](../assets/new.svg) - Aggiunta la possibilità di specificare il proprio Web SDK AEP quando [connessione](connect-data.md) la tua istanza di Adobe Commerce all’Experience Platform
* ![Correzione](../assets/fix.svg) - È stato aggiornato il requisito dell’ambito dello stream di dati in modo che gli ID dello stream di dati debbano essere inclusi nell’ambito del sito web anziché della visualizzazione archivio

## 1.0.0

_9 agosto 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Versione di disponibilità generale
