---
title: Note sulla versione
description: Informazioni aggiornate sulla versione del connettore Adobe Experience Platform di Adobe Commerce.
exl-id: 7636664b-488a-46f7-8d19-a9faac126aec
source-git-commit: 975854dbdae32e5e51bb57593cf122627d01571f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 2%

---

# Note sulla versione

Queste note sulla versione contengono aggiornamenti al connettore Experience Platform e includono:

* ![Nuovo](../assets/new.svg) - Nuove funzioni
* ![Correzione](../assets/fix.svg) - Correzioni e miglioramenti
* ![Bug](../assets/bug.svg) - Problemi noti

Per le modifiche alle funzioni e le correzioni relative alle estensioni utilizzate dal connettore Experience Platform, vedi **Aggiornamenti del servizio supportati**.

Vedi [Versioni future](https://experienceleague.adobe.com/docs/commerce-operations/release/schedule.html) per informazioni sulle pianificazioni e sul supporto delle versioni.

Vedi [Disponibilità](https://experienceleague.adobe.com/docs/commerce-operations/release/availability.html) per informazioni sulla compatibilità del prodotto.

## Aggiornamenti del servizio supportati

Queste note sulla versione descrivono le modifiche alle funzioni e le correzioni relative alle estensioni utilizzate dal connettore di Experience Platform.

+++Aggiornamenti al servizio supportati

_12 ottobre 2022_

* ![Nuovo](../assets/new.svg) - Aggiunte due [eventi di vetrina](events.md): `openCart` e `removeFromCart` all’SDK e al Collector per Adobe Commerce Storefront Events
* ![Nuovo](../assets/new.svg) - È stato aggiunto il supporto per un [AEM vetrina](overview.md#aem-support)

+++

## 2.1.0

_17 gennaio 2023_

* ![Nuovo](../assets/new.svg) - Aggiornamento del [Amministratore del connettore Experience Platform](connect-data.md) in modo da poter specificare un proprio AEP Web SDK (lega). Inoltre, è stata aggiunta un&#39;opzione per i commercianti iscritti al nostro programma beta back office per inviare [dati evento back office](connect-data.md#data-collection) sul bordo. Questi eventi contengono [informazioni sullo stato dell&#39;ordine](events.md#beta-order-status-events) su un ordine, ad esempio se un ordine è stato effettuato, annullato, rimborsato o spedito. Se desideri partecipare al programma beta del back office, contatta [drios@adobe.com](mailto:drios@adobe.com).
* ![Correzione](../assets/fix.svg) È stato modificato in utilizzando `identityMap` anziché `personID` quando si imposta l’identità principale per tutti i dati inviati al bordo.

## 2.0.1

_10 novembre 2022_

* ![Problema risolto](../assets/fix.svg) - Ora il contesto Adobe Experience Platform viene impostato solo dopo il corretto caricamento di Storefront Event Collector e Storefront Event SDK.

## 2.0.0

_12 ottobre 2022_

* ![Nuovo](../assets/new.svg) - Aggiunta la possibilità di specificare il proprio SDK web AEP quando [collegamento](connect-data.md) l’istanza Adobe Commerce all’Experience Platform
* ![Correzione](../assets/fix.svg) - È stato aggiornato il requisito dell’ambito del datastream in modo che gli ID del datastream debbano essere indirizzati al sito web anziché a storeview

## 1.0.0

_9 agosto 2022_

* ![Nuovo](../assets/new.svg) - Versione generale di disponibilità

## Documentazione

Per ulteriori informazioni:

* [Documentazione per gli sviluppatori di Adobe Commerce](https://devdocs.magento.com/)
* [Guida utente di Adobe Commerce](https://docs.magento.com/user-guide/)
