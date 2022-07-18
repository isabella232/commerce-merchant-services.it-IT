---
title: Aggiungi gruppi di campi allo schema XDM
description: Scopri come aggiungere gruppi di campi specifici per Adobe Commerce a uno schema XDM.
source-git-commit: 4d6a4cec81dbb1e71718066be2ba13a4d292aea3
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# Aggiungi gruppi di campi allo schema XDM

Uno dei [prerequisiti](overview.md#prereqs) per utilizzare il connettore Experience Platform è necessario accedere all’area di lavoro del datastream e [creare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en) specifico per Adobe Commerce. Quando crei quel datastream, devi anche selezionare uno schema XDM che rappresenti i dati che intendi acquisire. Questo argomento fornisce i gruppi di campi che lo schema XDM deve includere per raccogliere correttamente i dati forniti dalla vetrina Adobe Commerce [events](events.md).

1. Se non disponi già di uno schema XDM, [creare](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=en#create) uno. In caso contrario, [modifica](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=en#edit) lo schema XDM esistente nell’interfaccia utente di Adobe Experience Platform.
1. [Aggiungi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=en#add-field-groups) i seguenti gruppi di campi specifici per Commerce:

   - Commerce
   - Ricerca nel sito
   - Visita pagina web
   - Processo di accesso utente
   - Chiavi di riferimento
   - Dati di contatto personali
   - Dettagli Commerce
   - Adobe Analytics Experience Event Commerce (se desideri inviare dati ad Adobe Analytics)
   - Identificatore persona

   Lo schema XDM contiene ora gruppi di campi specifici per Commerce, in modo che i dati raccolti dalla vetrina Commerce [events](events.md) è rappresentato in XDM.
1. Ora dovresti [creare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en) e selezionare lo schema XDM che contiene i gruppi di campi specifici per Commerce.
