---
title: Panoramica sull’onboarding per i servizi di Store Fulfillment
description: '''[!DNL Live Search] flusso di onboarding, requisiti di sistema, limiti e limitazioni."'
role: User, Admin
level: Intermediate
exl-id: f8e403ac-9bbd-4ea2-b209-9b1a8d1e32a2
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# Panoramica sull’onboarding per il Store Fulfillment

Introduzione a [!DNL Store Fulfillment for Adobe Commerce by Walmart Commerce Technologies] mediante l&#39;impostazione, la configurazione e l&#39;attivazione dei seguenti componenti:

- **Estensione Store Fulfillment**: installa e configura questa estensione di terze parti nell’istanza di Adobe Commerce. Dopo l&#39;installazione, puoi configurare e gestire la soluzione Store Fulfillment dall&#39;amministratore per supportare [!DNL buys online, pickup in store] (BOPIS) nella vetrina Commerce.

   ![[!DNL Store Fulfillment Service] configurazione nella visualizzazione Amministratore](assets/store-fulfillment-admin-home.png)

- **Archivia account di evasione**-Durante il processo di abilitazione, un Account Manager crea l&#39;account Store Fulfillment e fornisce le informazioni e le credenziali dell&#39;account. Queste credenziali sono necessarie per abilitare la connessione tra Adobe Commerce e la soluzione Store Fulfillment.

- **App Store Assist**- Fornisce agli associati al negozio un flusso di lavoro di evasione del negozio end-to-end per gestire gli ordini BOPIS da dispositivi mobili. I soci del negozio possono scaricare e installare Walmart&#39;s [!DNL Store Assist] per dispositivi iOS e Android™. Il processo di onboarding delle app è gestito come processo separato dal Walmart Commerce Technologies Client Center. Tuttavia, [alcune impostazioni di configurazione dell’app](user-setup.md) sono state completate dall’amministratore di Adobe Commerce.

   | App Store Assist - Visualizzazione introduttiva | App Store Assist — Vista moduli |
   |-------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
   | ![[!DNL Store Assist App Getting Started] visualizza su dispositivo mobile](assets/store-assist-get-started-small.png) | ![[!DNL Store Assist App Orders view] su dispositivo mobile](assets/store-assist-orders-small.png) |

## Passaggi di provisioning

- **Registrati a[!DNL Store Fulfillment for Adobe Commerce by Walmart Commerce Technologies]**-Compilare il modulo di iscrizione il [business.adobe.com](https://business.adobe.com/resources/store-fulfillment.html)o contatta il tuo Adobe Commerce Account Manager per assistenza.

- **Avvia la richiesta di provisioning per il completamento dell&#39;archivio**-Completare il modulo di assegnazione fornito dall&#39;Account Manager per fornire le informazioni necessarie per avviare il processo di assegnazione ruoli.

- **Ottieni le credenziali del tuo account Store Fulfillment**- Dopo aver creato l&#39;account Store Fulfillment, riceverai le credenziali necessarie per integrare la soluzione Store Fulfillment con Adobe Commerce.

- **[Scarica il codice sorgente per installare [!DNL Store Fulfillment] estensione](install.md)**

## Passaggi di onboarding

1. [Installare l’estensione Store Fulfillment per Adobe Commerce](install.md).

1. Dall’amministratore, [abilitare la soluzione](enable-general.md).

1. [Configurare l’estensione Store Fulfillment dall’amministratore di Adobe Commerce](service-config-settings-overview.md).

1. [Connetti [!DNL Store Fulfillment] servizio che utilizza le credenziali Store Fulfillment fornite](connect-set-up-service.md).

1. [Creare utenti e ruoli per l’app Store Assist](user-setup.md).

1. [Scarica Walmart [!DNL Store Assist] sul dispositivo desiderato. L’app è disponibile sia sull’app Apple (iOS) che su Google Play (Android™)](app-setup.md) negozi.

Dopo aver installato, configurato, completato l’onboarding e aver accesso al [!DNL Store Assist] app, puoi [inizia a creare ordini e a testare](test-and-deploy.md).
