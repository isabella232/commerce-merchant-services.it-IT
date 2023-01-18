---
title: Configura le [!DNL Quick Checkout] per estensione Adobe Commerce
description: Scopri le opzioni di configurazione per [!DNL Quick Checkout] e come integrare e configurare correttamente l'estensione.
exl-id: 892e04dc-17d6-45e9-b2ab-c7a0735a75bc
source-git-commit: 1b2847b71e2a6aa843de2e73dfe5f3ad295c7b5f
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# [!DNL Quick Checkout] impostazioni

[!DNL Quick Checkout] per Adobe Commerce e Magenti Open Source fornisce una visualizzazione di configurazione con tutte le informazioni necessarie per configurare l&#39;estensione.

Per accedere alle seguenti impostazioni di configurazione:

1. Sulla _Amministratore_ barra laterale, vai a **Negozi** > _Impostazioni_ > **Configurazione**.
1. Nel pannello a sinistra, espandi **Vendite** e seleziona **Pagamento**.

   ![Pagamento rapido](assets/configuration-view.png)

Fai riferimento a [Onboarding](../quick-checkout/onboarding.md) per ulteriori informazioni su come configurare il [!DNL Quick Checkout] per Adobe Commerce.

## Abilita estensione

![Pagamento rapido](assets/enable-method.png)

| Campo | Ambito | Descrizione |
|---|---|---|
| [!UICONTROL Enable] | sito web | Attiva o disattiva [!DNL Quick Checkout] per il sito web. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Method] | sito web | Imposta il metodo o l&#39;ambiente per il tuo [!DNL Quick Checkout]. Opzioni: [!UICONTROL Sandbox] / [!UICONTROL Production] |

{style=&quot;table-layout:auto&quot;}

## Credenziali account

![Pagamento rapido](assets/account-creds.png)

| Campo | Ambito | Descrizione |
|---|---|---|
| [!UICONTROL API key] | sito web | Una chiave privata utilizzata dal back end per interagire con [!DNL Bolt] API. |
| [!UICONTROL Publishable key] | sito web | Chiave utilizzata dal front-end per interagire con [!DNL Bolt] API. |
| [!UICONTROL Signing secret] | sito web | Utilizzato per la verifica della firma sulle richieste ricevute da [!DNL Bolt]. |

{style=&quot;table-layout:auto&quot;}

## Impostazioni del servizio

![Pagamento rapido](assets/service-settings.png)

| Campo | Ambito | Descrizione |
|---|---|---|
| [!UICONTROL Title] | vista store | Aggiungere il testo da visualizzare come titolo per questa opzione di pagamento nella visualizzazione Metodo di pagamento durante il pagamento. Opzioni: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | sito web | La [azione di pagamento](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} per il metodo di pagamento specificato. Opzioni: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Debug Mode] | sito web | Attiva o disattiva la modalità di debug. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Enable checkout tracking] | sito web | Definisci se Adobe Commerce consente di condividere le informazioni di tracciamento del checkout con Bolt. Abilitato per impostazione predefinita. Se disabilitata, la generazione di rapporti ne risentirà. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Next Stage After Login Mode] | sito web | Modifica il flusso di navigazione dopo l’accesso del cliente. Opzioni: [!UICONTROL Payment] / [!UICONTROL Shipping] |
| [!UICONTROL Automatic Login Enabled] | sito web | Definisci se [!DNL Quick Checkout] consente l&#39;accesso automatico durante il pagamento. Abilitato per impostazione predefinita. Opzioni: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Automatic Login Network] | sito web | Seleziona la rete in cui il cliente accede automaticamente. Per impostazione predefinita, è abilitato il bullone. Opzioni: [!UICONTROL Bolt + Merchant] / [!UICONTROL Bolt] |

{style=&quot;table-layout:auto&quot;}
