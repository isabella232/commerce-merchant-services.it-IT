---
title: Panoramica della guida
description: Scopri come integrare i dati di Adobe Commerce con Adobe Experience Platform utilizzando il connettore di Experience Platform.
exl-id: a8362e71-e21c-4b1d-8e3f-336e748e1018
source-git-commit: 0d5bbe7d4e2070173930df66c4f159d65c7383ea
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Panoramica del connettore di Experience Platform

L’estensione del connettore Experience Platform consente agli esercenti Adobe Commerce di inviare [vetrina](events.md#storefront-events) e [ufficio postale](events.md#back-office-events) i dati al server Edge di Adobe Experience Platform in modo che altri prodotti Adobe Experience Cloud, come Adobe Analytics e Adobe Target, possano utilizzare tali dati Commerce. Collegando i dati Commerce ad altri prodotti in Adobe Experience Cloud, puoi eseguire attività quali l’analisi del comportamento degli utenti sul sito, l’esecuzione di test AB e la creazione di campagne personalizzate.

[Eventi Storefront](events.md#storefront-events) acquisire interazioni con gli acquirenti, ad esempio `View Page`, `View Product`, `Add to Cart`e [elenco richieste](events.md#b2b-events) informazioni (per i commercianti B2B). [Back Office](events.md#back-office-events) gli eventi acquisiscono informazioni sullo stato di un ordine, ad esempio se un ordine è stato effettuato, annullato, rimborsato, spedito o completato. I dati acquisiti non includono informazioni personali identificabili (PII). Tutti gli identificatori utente, come gli ID cookie e gli indirizzi IP, sono rigorosamente anonimi. [Ulteriori informazioni](https://www.adobe.com/privacy/experience-cloud.html).

Il connettore di Experience Platform viene visualizzato in Commerce Admin in **Sistema** > Servizi > **Connettore Experience Platform**.

![Estensione del connettore di Experience Platform Vista amministratore](assets/epc-adminui.png)

## Prerequisiti {#prereqs}

Per utilizzare il connettore di Experience Platform, è necessario disporre dei seguenti elementi:

- Adobe Commerce 2.4.3 o successivo
- Adobe ID e ID organizzazione
- [Livello dati client Adobe (ACDL)](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/client-data-layer/overview.html). L&#39;ACDL è necessario per raccogliere i dati dell&#39;evento di vetrina.
- Diritti ad altri prodotti DX di Adobi

## Passaggi di onboarding

1. [Installa](install.md) estensione del connettore di Experience Platform.
1. [Accedere](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) al tuo account Adobe e [visualizza conferma](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255) l&#39;ID organizzazione. L&#39;ID organizzazione è l&#39;ID associato all&#39;azienda con provisioning di Experience Cloud. Questo ID è una stringa alfanumerica composta da 24 caratteri, seguita da (e deve includere) `@AdobeOrg`.
1. [Crea o aggiorna](update-xdm.md) schema XDM con gruppi di campi specifici per Commerce.
1. [Creare un set di dati](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) in base allo schema creato o aggiornato. Questo set di dati conterrà i dati Commerce inviati.
1. [Creare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) e selezionare lo schema XDM che contiene i gruppi di campi specifici per Commerce.
1. [Connessione a Commerce Services](../landing/saas.md).
1. [Connessione a Adobe Experience Platform](connect-data.md).

## Pubblico

Questa guida è progettata per l’addetto al marketing Adobe Commerce che desidera collegare i propri dati Adobe Commerce ad altri prodotti DX di Adobe.

### Supporto PWA Studi

Consulta la sezione [PWA Studi](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/) documentazione per informazioni su come utilizzare il connettore Experience Platform in una vetrina PWA Studi.

### Supporto AEM {#aem-support}

Consulta la sezione [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/aep.html) documentazione per scoprire come inviare i dati dell’evento storefront da una pagina di prodotto di cui è stato eseguito il rendering AEM all’Experience Platform utilizzando CIF - Experience Platform Connector.

Se hai bisogno di informazioni o hai domande che non sono incluse in questa guida, utilizza le risorse seguenti:

- [Centro assistenza](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html){target="_blank"}
- [Biglietti di supporto](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket){target="_blank"}- Invia un ticket per ricevere ulteriore assistenza.
