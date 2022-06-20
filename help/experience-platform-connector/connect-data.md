---
title: Connettere dati Commerce a Adobe Experience Platform
description: Scopri come collegare i dati Commerce a Adobe Experience Platform.
source-git-commit: 9b5f2da08167e22bbba504009bccc87d0ab02c48
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---

# Connettere dati Commerce a Adobe Experience Platform {#connectaep}

Prima di collegare i dati di Adobe Commerce a Adobe Experience Platform, devi accedere al tuo account di Adobe in [Connettore Commerce Services](../landing/saas.md#organizationid). Dopo aver effettuato l&#39;accesso e aver selezionato l&#39;ID organizzazione, puoi quindi specificare l&#39;ID ambito e datastream sul **Connettore Experience Platform** in Admin.

1. Nell&#39;Admin, vai a **Sistema** > Servizi > **Connettore Experience Platform**.

1. In **Ambito** a discesa, seleziona il contesto o l&#39;&quot;ambito&quot; della visualizzazione archivio.

   L&#39;ID organizzazione è globale. Per ogni istanza di Adobe Commerce è possibile associare un solo ID organizzazione.

1. In **Organizzazione IMS** , viene visualizzato l’ID associato al tuo account Adobe Experience Platform, come configurato nel [Connettore Commerce Services](../landing/saas.md#organizationid).

1. In **ID Datastream** incolla l’ID del flusso di dati che utilizzi [creato](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html) in Adobe Experience Platform.

## Relazione dell’ID Datastream e della visualizzazione dell’istanza Commerce

L&#39;ID Datastream consente l&#39;inoltro degli eventi da Adobe Experience Platform ad altri prodotti Adobe DX e può essere associato a una visualizzazione di archiviazione specifica all&#39;interno della tua istanza Adobe Commerce specifica. È inoltre possibile associare più vetrine allo stesso ID Datastream. Dipende da ciò che ha più senso per il vostro business.

## Descrizioni dei campi

| Campo | Descrizione |
|--- |--- |
| Ambito | Anteprima specifica in cui applicare le impostazioni di configurazione. |
| Organizzazione IMS (globale) | ID appartenente all’organizzazione che ha acquistato il prodotto Adobe DX. Questo ID collega la tua istanza Adobe Commerce a Adobe Experience Platform. |
| ID Datastream (Storeview) | ID che consente il flusso dei dati da Adobe Experience Platform ad altri prodotti DX di Adobe. Questo ID può essere associato a uno specifico storeView all&#39;interno della tua istanza Adobe Commerce specifica. |

Con l’estensione del connettore di Experience Platform installata, viene creato il collegamento tra Adobe Commerce e Adobe Experience Platform e viene specificato l’ID del ream di dati, [!DNL Commerce] i dati iniziano a scorrere fino al server Edge Adobe Experience Platform e ad altri prodotti DX Adobe.

## Dati di Commerce a margine

Quando i dati Commerce vengono inviati al server Edge di Adobe Experience Platform, puoi generare rapporti come segue:

![Dati di Commerce in Adobe Experience Manager](assets/aem-data-1.png)
_Dati di Commerce in Adobe Experience Manager_
