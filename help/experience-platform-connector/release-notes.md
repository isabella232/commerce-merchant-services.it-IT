---
title: Note sulla versione
description: Informazioni aggiornate sulla versione del connettore Adobe Experience Platform di Adobe Commerce.
exl-id: 7636664b-488a-46f7-8d19-a9faac126aec
source-git-commit: 22823b662eefa953fcca6ae78f6c37ee8abff3d1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Note sulla versione

Queste note sulla versione contengono aggiornamenti al connettore Experience Platform e includono:

* ![Nuovo](../assets/new.svg) - Nuove funzioni
* ![Correzione](../assets/fix.svg) - Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) - Problemi noti

Per le modifiche alle funzioni e le correzioni relative alle estensioni utilizzate dal connettore Experience Platform, vedi **Aggiornamenti del servizio supportati**.

Vedi [Versioni future](https://experienceleague.adobe.com/docs/commerce-operations/release/planning/schedule.html) per informazioni sulle pianificazioni e sul supporto delle versioni.

Consulta la documentazione per gli sviluppatori su [informazioni sulla compatibilità dei prodotti](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).

## Aggiornamenti del servizio supportati

Queste note sulla versione descrivono le modifiche alle funzioni e le correzioni relative alle estensioni utilizzate dal connettore di Experience Platform.

+++Aggiornamenti al servizio supportati

_30 marzo 2023_

* ![Nuovo](../assets/new.svg) - Aggiunta di una nuova estensione denominata `data-services-b2b` che include [eventi elenco richieste](events.md#b2b-events) per i commercianti B2B
* ![Nuovo](../assets/new.svg) - Aggiunto il `uniqueIdentifier` campo a [ricerca](events.md#search-events) eventi. Questo nuovo campo consente agli esercenti di fare riferimento incrociato alle richieste di ricerca corrispondenti alle risposte di ricerca.

_12 ottobre 2022_

* ![Nuovo](../assets/new.svg) - Aggiunte due [eventi di vetrina](events.md): `openCart` e `removeFromCart` all’SDK e al Collector per Adobe Commerce Storefront Events
* ![Nuovo](../assets/new.svg) - È stato aggiunto il supporto per un [AEM vetrina](overview.md#aem-support)

+++

## 2.2.0

_30 marzo 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Bundle del `commerce-data-export` e `saas-export` dipendenze con `experience-platform-connector` estensione. In precedenza era necessario installare queste dipendenze separatamente. Queste dipendenze, insieme alla configurazione del merchant, consentono l&#39;elaborazione lato server di [eventi back office](events.md#back-office-events).
* ![Nuovo](../assets/new.svg) - Aggiunta di un nuovo evento back office chiamato [`orderShipmentCompleted`](events.md#ordershipmentcompleted).

## 2.1.1

_28 febbraio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - È stato aggiunto il supporto per PHP 8.2 per tutti i moduli di connettore Experience Platform

## 2.1.0

_17 gennaio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Aggiornamento del [Amministratore del connettore Experience Platform](connect-data.md) in modo da poter specificare un proprio AEP Web SDK (lega).
* ![Correzione](../assets/fix.svg) È stato modificato in utilizzando `identityMap` anziché `personID` quando si imposta l’identità principale per tutti i dati inviati al bordo.

## 2.0.1

_10 novembre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Problema risolto](../assets/fix.svg) - Ora il contesto Adobe Experience Platform viene impostato solo dopo il corretto caricamento di Storefront Event Collector e Storefront Event SDK.

## 2.0.0

_12 ottobre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Aggiunta la possibilità di specificare il proprio SDK web AEP quando [collegamento](connect-data.md) l’istanza Adobe Commerce all’Experience Platform
* ![Correzione](../assets/fix.svg) - È stato aggiornato il requisito dell’ambito del datastream in modo che gli ID del datastream debbano essere indirizzati al sito web anziché a storeview

## 1.0.0

_9 agosto 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

* ![Nuovo](../assets/new.svg) - Versione generale di disponibilità
