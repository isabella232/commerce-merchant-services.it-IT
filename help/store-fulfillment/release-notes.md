---
title: '[!DNL Store Fulfillment by Walmart Commerce Technologies] Note sulla versione'
description: "Consulta le note sulla versione per informazioni su tutti [!DNL Store Fulfillment by Walmart Commerce Technologies] versioni."
role: Admin, User, Leader
feature: Shipping/Delivery, Release Notes
exl-id: 04dcec10-fff8-483d-a2c1-4b58e063e0f0
source-git-commit: 78b09113e72382053b01d6016276bae3aa545fa3
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 2%

---

# Note sulla versione

Queste note sulla versione descrivono la versione iniziale di [!DNL Store Fulfillment Services by Walmart Commerce Technologies] e includono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Problema risolto](../assets/fix.svg) Correzioni e miglioramenti
![Problema noto](../assets/bug.svg) Problemi noti

## v1.5.0

*3 agosto 2023*

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}[Adobe Commerce da 2.4.4 a 2.4.6](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html), incluse le versioni delle patch di sicurezza 2.4.6-p1, 2.4.5-p3 e 2.4.4-p4.

Questa versione contiene i seguenti aggiornamenti:

![Nuovo](../assets/fix.svg) Aggiornamento dell&#39;estensione per supportare [Versioni delle patch di sicurezza di Adobe Commerce](https://experienceleague.adobe.com/docs/commerce-operations/release/notes/security-patches/overview.html) 2.4.6-p1, 2.4.5-p3 e 2.4.4-p4.

![Nuovo](../assets/new.svg)<!-- WMTP-918 --> È stato aggiunto il supporto per [Invio asincrono](sales-emails.md) opzione di configurazione per e-mail di vendita. I commercianti che eseguono l’aggiornamento alla versione 1.5.0 possono inviare le e-mail immediatamente (impostazione predefinita) o in modo asincrono.

![Nuovo](../assets/new.svg)<!-- WMTP-916--> È stato aggiornato il [Configurazione origini](merchant-store-configuration.md) per supportare i formati dei numeri telefonici internazionali.

![Nuovo](../assets/new.svg) È stata aggiunta una logica per evitare che gli importi dei rimborsi superino l&#39;importo rimanente o fatturato.

![Nuovo](../assets/new.svg)<!-- WMTP-882 --> Sostituito `google.map.LatLng` oggetto con valori letterali JSON per supportare la compatibilità con versioni precedenti di [!DNL Google Maps].

![Problema risolto](../assets/fix.svg)<!-- WMTP- --> È stato aggiornato lo script che crea `[!DNL Available for Store Pickup]` e `[!DNL Available for Home Delivery]` attributi di prodotto per evitare conflitti di categorie di attributi.

![Problema risolto](../assets/fix.svg)<!-- WMTP-915 --> È stato risolto un problema di compatibilità che causava un ciclo infinito durante il caricamento e il salvataggio di alcune entità.

![Problema risolto](../assets/fix.svg)<!-- WMTP-921 --> È stato risolto un problema che impediva [!DNL Ship to Store] la convalida delle offerte viene attivata quando un articolo viene aggiunto al carrello da una pagina dei dettagli del prodotto (PDP).

![Problema risolto](../assets/fix.svg)<!-- WMTP- 932 --> È stato risolto un problema di pagamento che consentiva ai clienti di selezionare il metodo di consegna a domicilio per gli articoli non idonei per la consegna a domicilio.

![Problema risolto](../assets/fix.svg) Aggiornamenti all&#39;installazione:

- <!-- WMTP-880--> È stato risolto un problema che causava la restituzione di un codice sito Web errato durante l&#39;installazione di [!DNL Store Fulfillment] estensione.

- <!-- WMTP-878--> È stato risolto un problema relativo ai valori SKU integer che richiedeva il cast del tipo di dati al tipo stringa durante l’installazione.

![Problema risolto](../assets/fix.svg)<!-- WMTP-915--> È stato corretto un errore causato da un codice di errore di archiviazione mancante.

![Problema risolto](../assets/fix.svg)<!-- WMTP-932 --> È stato corretto un bug relativo al rifiuto parziale durante le operazioni di dispensazione.

![Nuovo](../assets/new.svg)<!-- WMTP-953 --> L’endpoint API Cancel è stato aggiornato per utilizzare il parametro di stato come oggetto facoltativo.

![Nuovo](../assets/new.svg)<!-- WMTP-960 --> Sono stati migliorati i dettagli di registrazione per l’endpoint API Dispense.

## v1.4.0

*13 aprile 2023*

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/fix.svg) [!DNL Store Fulfillment] è ora [compatibile con [!DNL Adobe Commerce] Da 2.4.4 a 2.4.6](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).


## v1.3.0

*27 febbraio 2023*

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

Questa versione contiene i seguenti aggiornamenti:

![Nuovo](../assets/fix.svg)<!-- WMTP-795 --> È stata aggiunta la possibilità di disabilitare la soluzione Store Fulfillment per un sito specifico modificando l’ambito predefinito per l’impostazione Configurazione di sistema da sito web a globale.

## v1.2.0

*27 settembre 2022*

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

Questa versione contiene i seguenti aggiornamenti:

![Nuovo](../assets/fix.svg) [!DNL Store Fulfillment] è ora [compatibile con [!DNL Adobe Commerce] Da 2.4.4 a 2.4.5](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).


## v1.1.0

*15 luglio 2022*

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

Stabilità: disponibilità generale

![Nuovo](../assets/fix.svg)<!-- WMTP-731 --> Semplificato il [Configurazione dell’esperienza di archiviazione](check-in-experience-setup.md) per l’app Store Assist, aggiungendo le selezioni predefinite per marca e modello dell’auto. Nella versione precedente, i commercianti dovevano configurare manualmente le selezioni di marca e modello dell&#39;auto.

## v1.0.0

*4 marzo 2022*

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

Stabilità: disponibilità generale

## App Store Assist

Per informazioni sulle nuove versioni dell&#39;app Store Assist, vedi le informazioni sull&#39;app in [Apple App Store](https://apps.apple.com/us/app/store-assist-by-walmart/id1609281539){target="_blank"} or [Google Play store](https://play.google.com/store/apps/details?id=com.walmart.faas.storeassist){target="_blank"}.
