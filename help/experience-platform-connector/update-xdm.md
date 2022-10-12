---
title: Aggiungi gruppi di campi allo schema XDM
description: Scopri come aggiungere gruppi di campi specifici per Adobe Commerce a uno schema XDM.
exl-id: 4401bbe7-1ccc-4349-a998-9e9ee9db590f
source-git-commit: f5d1c39fe1b02d2a661b92f971fba5b3e836dd6a
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Aggiungi gruppi di campi allo schema XDM

Uno dei [fasi di onboarding](overview.md#onboarding-steps) per utilizzare il connettore Experience Platform è necessario accedere all’area di lavoro del datastream e [creare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) specifico per Adobe Commerce. Quando crei quel datastream, devi anche selezionare uno schema XDM che rappresenti i dati che intendi acquisire. Questo argomento fornisce i gruppi di campi che lo schema XDM deve includere per raccogliere correttamente i dati forniti dalla vetrina Adobe Commerce [events](events.md).

1. Se non disponi già di uno schema XDM, [creare](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#create) uno. In caso contrario, [modifica](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#edit) lo schema XDM esistente nell’interfaccia utente di Adobe Experience Platform.

1. [Aggiungi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#add-field-groups) i seguenti gruppi di campi specifici per Commerce:

   - Ricerca nel sito
   - Visita pagina web
   - Processo di accesso utente
   - Chiavi di riferimento
   - Dati di contatto personali
   - Dettagli Commerce
   - Adobe Analytics Experience Event Commerce (se desideri inviare dati ad Adobe Analytics)
   - Identificatore persona

   >[!NOTE]
   >
   > Non impostare gruppi di campi specifici per Commerce come `Primary identity`. In questo modo il campo viene identificato come richiesto e l’Experience Platform lo prevede in ogni evento. Se tale campo è assente, l’inserimento dei dati non riesce.

   Lo schema XDM contiene ora gruppi di campi specifici per Commerce, in modo che i dati raccolti dalla vetrina Commerce [events](events.md) è rappresentato in XDM.

1. [Creare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) e selezionare lo schema XDM che contiene i gruppi di campi specifici per Commerce.
