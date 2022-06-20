---
title: Panoramica della guida
description: Connettore Adobe Experience Platform per Adobe Commerce [!DNL Commerce] ad altri prodotti Adobe Experience Cloud.
source-git-commit: 9b5f2da08167e22bbba504009bccc87d0ab02c48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Panoramica del connettore di Experience Platform

L’estensione del connettore Experience Platform consente agli esercenti Adobe Commerce di inviare dati al server Edge di Adobe Experience Platform in modo che altri prodotti Adobe Experience Cloud, come Adobe Analytics e Adobe Target, possano utilizzarli [!DNL Commerce] dati. Collegando il [!DNL Commerce] dati ad altri prodotti in Adobe Experience Cloud, puoi eseguire attività quali l’analisi del comportamento degli utenti sul sito, l’esecuzione di test AB e la creazione di campagne personalizzate.

Gli eventi Storefront acquisiscono le interazioni dell&#39;acquirente, ad esempio `View Page`, `View Product`, `Add to Cart`e così via. I dati acquisiti non includono informazioni personali identificabili (PII). Tutti gli identificatori utente, come gli ID cookie e gli indirizzi IP, sono rigorosamente anonimi. [Ulteriori informazioni](https://www.adobe.com/privacy/experience-cloud.html). Vedi l&#39;elenco completo degli eventi di vetrina verso la fine di questa pagina.

## Prerequisiti per l’utilizzo del connettore Experience Platform {#prereqs}

Per utilizzare il connettore di Experience Platform, devi prima:

- Compila quanto segue [modulo](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4VH_dtG9hJVAk_TqGkZC2DxUM1FSWkdJOE41UVpUWUw0M1JWV0RKS1VXQi4u) e Adobe ti fornirà l’accesso a Datastreams e Adobe Experience Platform (se necessario).

Quando l&#39;accesso è concesso:

1. [Accedere](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) al tuo account Adobe.
1. Guarda il tuo [organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en#concept_EA8AEE5B02CF46ACBDAD6A8508646255). L&#39;ID organizzazione è l&#39;ID associato all&#39;azienda con provisioning di Experience Cloud. Questo ID è una stringa alfanumerica composta da 24 caratteri, seguita da (e deve includere) @AdobeOrg.
1. Accedere all’area di lavoro del datastream e [creare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en).

L&#39;ID organizzazione e il datastream vengono utilizzati quando si collega l&#39;istanza Adobe Commerce a Adobe Experience Platform.

## Passaggi successivi

- Installa il [Estensione del connettore di Experience Platform](install.md).

   L’estensione del connettore di Experience Platform viene installata dalla riga di comando del server e si connette all’installazione di Adobe Commerce come [servizio](../landing/saas.md). Al termine del processo, il connettore di Experience Platform viene visualizzato sul **Sistema** menu sotto **Servizi** in [!DNL Commerce] _Amministratore_.

## Pubblico

Questa guida è progettata per il commerciante Adobe Commerce che deve collegare i propri dati della vetrina Adobe Commerce ad altri prodotti Adobe DX.

## Problemi noti

Attualmente, il connettore Experience Platform presenta i seguenti problemi noti:

- Gli eventi di ricerca non sono supportati in Adobe Commerce Enterprise Edition con il modulo B2B installato.
- I dati di Storefront richiedono alcune ore per passare da Commerce alle varie destinazioni dopo la connessione al server Edge di Adobe Experience Platform.

## Supporto

Se hai bisogno di informazioni o hai domande che non sono incluse in questa guida, invia al seguente canale di Slack:

- `#beacon-ama`
