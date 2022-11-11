---
title: Panoramica della guida
description: Scopri come integrare i dati di Adobe Commerce con Adobe Experience Platform utilizzando il connettore di Experience Platform.
exl-id: a8362e71-e21c-4b1d-8e3f-336e748e1018
source-git-commit: a316b92f75cb227d0c58af07482f9d37568af7ca
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# Panoramica del connettore di Experience Platform

L’estensione del connettore di Experience Platform consente agli esercenti Adobe Commerce di inviare dati al server Edge di Adobe Experience Platform in modo che altri prodotti Adobe Experience Cloud, come Adobe Analytics e Adobe Target, possano utilizzare tali dati Commerce. Collegando i dati Commerce ad altri prodotti in Adobe Experience Cloud, puoi eseguire attività quali l’analisi del comportamento degli utenti sul sito, l’esecuzione di test AB e la creazione di campagne personalizzate.

[Eventi Storefront](events.md) acquisire interazioni con gli acquirenti, ad esempio `View Page`, `View Product`, `Add to Cart`e così via. I dati acquisiti non includono informazioni personali identificabili (PII). Tutti gli identificatori utente, come gli ID cookie e gli indirizzi IP, sono rigorosamente anonimi. [Ulteriori informazioni](https://www.adobe.com/privacy/experience-cloud.html).

Il connettore di Experience Platform viene visualizzato in Commerce Admin in **Sistema** > Servizi > **Connettore Experience Platform**.

![Estensione del connettore di Experience Platform Vista amministratore](assets/epc-adminui.png)

## Prerequisiti {#prereqs}

Per utilizzare il connettore di Experience Platform, è necessario disporre dei seguenti elementi:

- Adobe Commerce 2.4.3 o successivo
- Adobe ID e ID organizzazione
- Diritti ad altri prodotti DX di Adobi

## Passaggi di onboarding

1. [Installa](install.md) estensione del connettore di Experience Platform.
1. [Accedere](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) al tuo account Adobe e [visualizzare](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en#concept_EA8AEE5B02CF46ACBDAD6A8508646255) l&#39;ID organizzazione. L&#39;ID organizzazione è l&#39;ID associato all&#39;azienda con provisioning di Experience Cloud. Questo ID è una stringa alfanumerica composta da 24 caratteri, seguita da (e deve includere) `@AdobeOrg`.
1. [Connetti](connect-data.md) la tua istanza di Adobe Commerce in Adobe Experience Platform.
1. [Crea o aggiorna](update-xdm.md) schema XDM con gruppi di campi specifici per Commerce.
1. [Creare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en) e selezionare lo schema XDM che contiene i gruppi di campi specifici per Commerce.
1. (Facoltativo) [Caricare profili cliente](profile.md) a Adobe Experience Platform in modo che i dati della vetrina possano essere attribuiti a clienti specifici per migliorare la loro esperienza di acquisto.

## Pubblico

Questa guida è progettata per il commerciante Adobe Commerce che desidera collegare i propri dati della vetrina Adobe Commerce ad altri prodotti Adobe DX.

### Supporto PWA Studi

Consulta la sezione [PWA Studi](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/) documentazione per informazioni su come utilizzare il connettore Experience Platform in una vetrina PWA Studi.

### Supporto AEM {#aem-support}

Consulta la sezione [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/aep.html) documentazione per scoprire come inviare i dati dell’evento storefront da una pagina di prodotto di cui è stato eseguito il rendering AEM all’Experience Platform utilizzando CIF - Experience Platform Connector.

Se hai bisogno di informazioni o hai domande che non sono incluse in questa guida, utilizza le risorse seguenti:

- [Centro assistenza](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html){target=&quot;_blank&quot;}
- [Biglietti di supporto](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket){target=&quot;_blank&quot;} - Invia un ticket per ricevere ulteriore assistenza.
