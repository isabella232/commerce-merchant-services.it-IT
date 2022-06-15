---
title: Panoramica sull'onboarding per i servizi di evasione dello store
description: '"[!DNL Live Search] flusso di onboarding, requisiti di sistema, limiti e limitazioni."'
role: User, Admin
level: Intermediate
source-git-commit: 42b0118b427b1e04186793b4a57c058bc1cabdd4
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---

# Panoramica sull&#39;onboarding per la distribuzione nello store

Introduzione a [!DNL Store Fulfillment for Adobe Commerce by Walmart Commerce Technologies] configurando, configurando e abilitando i seguenti componenti:

- **Estensione Store Fulfillation**- Installa e configura questa estensione di terze parti nella tua istanza Adobe Commerce. Dopo l’installazione, puoi configurare e gestire la soluzione Store Fulfillment dall’amministratore per supportare [!DNL buy online, pickup in store] (BOPIS) scenari nella vetrina Commerce.

   ![[!DNL Store Fulfillment Service] configurazione in Admin view](assets/store-fulfillment-admin-home.png)

- **Archivia account di evasione**- Durante il processo di abilitazione, un Account Manager crea il tuo account Store Fulfillment e ti fornisce le informazioni e le credenziali dell&#39;account. Queste credenziali sono necessarie per abilitare la connessione tra Adobe Commerce e la soluzione Store Fulfillment.

- **App Store Assist**- Fornisce ai collaboratori dello store un flusso di lavoro end-to-end per la gestione degli ordini BOPIS da dispositivi mobili. Store Associates può scaricare e installare Walmart [!DNL Store Assist] per dispositivi iOS e Android. Il processo di onboarding delle app è gestito dal Walmart Commerce Technology Client Center come processo separato. Tuttavia, [alcune impostazioni di configurazione dell&#39;app](user-setup.md) sono stati completati dall’amministratore di Adobe Commerce.

   | App Store Assist - Introduzione | App Store Assist — Visualizzazione Moduli |
   |-------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
   | ![[!DNL Store Assist App Getting Started] visualizzazione su dispositivi mobili](assets/store-assist-get-started-small.png) | ![[!DNL Store Assist App Orders view] su dispositivi mobili](assets/store-assist-orders-small.png) |

## Passaggi di provisioning

- **Iscriviti a[!DNL Store Fulfillment for Adobe Commerce by Walmart Commerce Technologies]**- Completa il modulo di registrazione su [business.adobe.com](https://business.adobe.com/resources/store-fulfillment.html)oppure contatta il tuo Adobe Commerce Account Manager per assistenza.

- **Avvia la richiesta di provisioning per Store Fulfillment**- Completare il modulo di assunzione fornito dal vostro Account Manager per fornire le informazioni necessarie per avviare il processo di provisioning.

- **Ottieni le credenziali del tuo account Store Fulfillment**- Dopo la creazione dell&#39;account Store Fulfillment, riceverai le credenziali necessarie per integrare la soluzione Store Fulfillment con Adobe Commerce.

- **[Scarica il codice sorgente per installare il [!DNL Store Fulfillment] estensione](install.md)**

## Passaggi di onboarding

1. [Installare l’estensione Store Fulfillment per Adobe Commerce](install.md).

1. Dall’amministratore, [abilitare la soluzione](enable-general.md).

1. [Configurare l’estensione Store Fulfillment dall’amministratore di Adobe Commerce](service-config-settings-overview.md).

1. [Collega [!DNL Store Fulfillment] servizio utilizzando le credenziali Store Fulfillment fornite all&#39;utente](connect-set-up-service.md).

1. [Creare utenti e ruoli per l’app Store Assist](user-setup.md).

1. [Scarica Walmart’s [!DNL Store Assist] app per il dispositivo desiderato. L&#39;app è disponibile sia nell&#39;app store (iOS) che in Play Store (Android)](app-setup.md).

Dopo aver installato, configurato, completato l&#39;onboarding e aver accesso al [!DNL Store Assist] app, puoi [iniziare a creare ordini e test](test-and-deploy.md).

