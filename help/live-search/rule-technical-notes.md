---
title: Note tecniche sulla regola
description: Note tecniche sull’utilizzo delle regole di Live Search.
exl-id: 24ff6a19-f7cd-42f7-b466-fc18f9091504
source-git-commit: 7402e97f53b71e488d860215487f4809572b7e6f
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%

---

# Note tecniche sulla regola

[!DNL Live Search] le regole attivano le azioni in base a una varietà di condizioni di query e danno agli esercenti la possibilità di modellare l’esperienza di ricerca per vari scenari.

L&#39;attuale versione di [!DNL Live Search] Le regole si basano sulla stringa di query immessa dall&#39;acquirente, anziché sul set di risultati restituiti. Una stringa di query può includere caratteri alfanumerici e la maiuscola viene ignorata. Come per i facet e i sinonimi, le regole sono memorizzate in `protobuf dynamo`. Al momento della query, il servizio di ricerca recupera le regole attraverso `grpc` chiama a `search-admin-service`.
