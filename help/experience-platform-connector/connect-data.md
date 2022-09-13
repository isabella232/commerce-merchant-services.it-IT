---
title: Connettere dati Commerce a Adobe Experience Platform
description: Scopri come collegare i dati Commerce a Adobe Experience Platform.
exl-id: 87898283-545c-4324-b1ab-eec5e26a303a
source-git-commit: c7344efead97b0562a146f096123dd84f998fd5e
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Connettere dati Commerce a Adobe Experience Platform {#connectaep}

Per collegare l’istanza Adobe Commerce a Adobe Experience Platform, devi fornire un ID organizzazione e un ID datastream.

![Configurazione del connettore di Experience Platform](assets/epc-config.png)

1. Accedi al tuo account di Adobe nel [Connettore Commerce Services](../landing/saas.md#organizationid) e seleziona l&#39;ID organizzazione.

1. Nell&#39;Admin, vai a **Sistema** > Servizi > **Connettore Experience Platform**.

1. In **Ambito** a discesa, seleziona il contesto o l&#39;&quot;ambito&quot; della visualizzazione archivio.

1. In **ID organizzazione** , viene visualizzato l’ID associato al tuo account Adobe Experience Platform, come configurato nel [Connettore Commerce Services](../landing/saas.md#organizationid). L&#39;ID organizzazione è globale. Per ogni istanza di Adobe Commerce è possibile associare un solo ID organizzazione.

1. In **ID Datastream** incolla l’ID del datastream che stai impostando [creato](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) in Adobe Experience Platform.

## Relazione tra l’ID del datastream e la visualizzazione della store dell’istanza Commerce

L&#39;ID del datastream consente l&#39;inoltro degli eventi da Adobe Experience Platform ad altri prodotti Adobe DX e può essere associato a una visualizzazione store specifica all&#39;interno della tua istanza Adobe Commerce specifica. Puoi anche associare più viste store allo stesso ID Datastream. Dipende da ciò che ha più senso per il vostro business. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en#event-forwarding-settings) informazioni sull&#39;inoltro eventi.

## Descrizioni dei campi

| Campo | Descrizione |
|--- |--- |
| Ambito | Visualizzazione archivio specifica in cui si desidera applicare le impostazioni di configurazione. |
| ID organizzazione (globale) | ID appartenente all’organizzazione che ha acquistato il prodotto Adobe DX. Questo ID collega la tua istanza Adobe Commerce a Adobe Experience Platform. |
| ID Datastream (visualizzazione Store) | ID che consente il flusso dei dati da Adobe Experience Platform ad altri prodotti DX di Adobe. Questo ID può essere associato a una visualizzazione archivio specifica all&#39;interno della tua istanza Adobe Commerce specifica. |

Con l’estensione del connettore di Experience Platform installata, il collegamento tra Adobe Commerce e Adobe Experience Platform creato e l’ID del Datastream specificato, i dati Commerce iniziano a scorrere fino al bordo di Adobe Experience Platform e ad altri prodotti DX di Adobe.

>[!NOTE]
>
> Il tempo necessario per il flusso dei dati dal bordo ad altri prodotti Adobe DX può variare.

## Dati di Commerce a margine

Quando i dati Commerce vengono inviati al server Edge di Adobe Experience Platform, puoi generare rapporti come segue:

![Dati di Commerce in Adobe Experience Manager](assets/aem-data-1.png)
_Dati di Commerce in Adobe Experience Manager_
