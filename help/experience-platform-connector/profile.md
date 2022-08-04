---
title: Caricare profili cliente in Adobe Experience Platform
description: Scopri come caricare i profili dell’acquirente in Adobe Experience Platform.
source-git-commit: 93133019f8004437ef85db32ff336bfd0e8c6fc2
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---

# Carica il profilo dell&#39;acquirente in Adobe Experience Platform

Gli esercenti Adobe Commerce possono caricare i dati del profilo cliente in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html), che fa parte di Adobe Experience Platform. Profile consente di consolidare i dati dei clienti in una visualizzazione unificata, con un account utilizzabile e con marca temporale per ogni interazione con il cliente.

>[!NOTE]
>
> I dati del profilo devono includere un indirizzo e-mail, in quanto è così che viene creato il collegamento tra un acquirente e i suoi dati comportamentali di vetrina.

Dopo aver caricato i profili dell&#39;acquirente, i dati dell&#39;evento associati a qualsiasi interazione che l&#39;acquirente può intraprendere sul tuo sito vengono inviati a Profilo tramite il connettore di Experience Platform e collegati al profilo dell&#39;acquirente.

>[!NOTE]
>
> La `createAccount` [evento di vetrina](events.md) non crea automaticamente un profilo cliente in Profilo. Questo è limitato per motivi di sicurezza ed è intenzionale.

In questo argomento viene illustrato come caricare i profili cliente Adobe Commerce nel Profilo cliente in tempo reale, ad Experience Platform.

1. Stabilisci dove memorizzare i dati dei clienti. Per alcuni commercianti, questi dati vengono memorizzati in Adobe Commerce e possono essere [esportato](https://docs.magento.com/user-guide/system/data-export.html) come file CSV. Per altri, potrebbe trovarsi in un sistema CRM (Customer Relationship Management) separato.

1. Dopo aver determinato la posizione in cui vengono archiviati i dati dei clienti, trova la [connettore di origine](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) in base a dove vengono memorizzati i dati dei clienti. Se non viene visualizzato un connettore di origine appropriato, utilizzare la [caricamento file locale](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/local-system/local-file-upload.html) Connetti e importa i profili dell’acquirente da un file CSV.

   >[!NOTE]
   >
   > Se utilizzi il connettore di caricamento file locale, devi abilitare il **Set di dati del profilo** opzione quando [definizione del set di dati](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/local-system/local-file-upload.html#use-an-existing-dataset). Questo identifica il set di dati come dati di profilo.

Dopo aver creato i profili dell’acquirente in Profilo, tutti i dati della vetrina associati a tale acquirente saranno collegati al loro profilo.

## Caricare i profili frequentemente

Per garantire una migliore esperienza di acquisto, importa periodicamente i dati del profilo. Alcuni connettori sorgente consentono di importare i dati del profilo in una pianificazione.
