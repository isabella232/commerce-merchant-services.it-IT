---
title: Onboard [!DNL Payment Services]
description: Collega l’istanza con [!DNL Payment Services] completando alcuni passaggi di onboarding.
role: User
level: Intermediate
exl-id: 1ee8c660-0941-4378-a1d7-ae45de3de211
source-git-commit: bfb2b6632fe494d6e392c214f5e3f5a11930c0b2
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---

# Onboard [!DNL Payment Services]

Per iniziare a utilizzare [!DNL Payment Services] per Adobe Commerce e Magenti Open Source, devi completare alcuni passaggi di onboarding per collegare la tua istanza alla funzionalità pagamenti.

## Flusso di onboarding

![Flusso di onboarding](assets/onboarding-diagram.svg)

Questo diagramma di flusso onboarding mostra il processo generale di onboarding [!DNL Payment Services].

Dopo aver completato l&#39;onboarding per i pagamenti sandbox o live, il reporting finanziario è accessibile da [!DNL Payment Services] nell&#39;amministratore.

Se i pagamenti sandbox e live sono entrambi onboarded e abilitati, puoi facilmente passare da una modalità all’altra [!DNL Payment Services] a casa.

## Prerequisiti

Per utilizzare [!DNL Payment Services], devi avere a disposizione quanto segue per la tua istanza:

* Modulo di connessione servizi
* Modulo ID servizi
* Chiavi API

I moduli Connettore servizi e ID servizi vengono installati automaticamente durante il [installazione [!DNL Payment Services]](install.md). Al termine dell&#39;installazione, è possibile visualizzare una nuova sezione nelle impostazioni di configurazione (**[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**) quando espandi **[!UICONTROL Services]**—**[!UICONTROL Commerce Services Connector]**.

Per informazioni su come creare o accedere alle chiavi API, vedi [Credenziali API](#obtain-api-credentials).

## Passaggi di onboarding

1. [Installa il [!DNL Payment Services] estensione](install.md#get-payment-services).
1. [Ottenere le credenziali API](connect.md#obtain-api-credentials).
1. [Collegare l&#39;istanza](connect.md#configure-commerce-services) a Commerce Services. Questa connessione deve essere completata una sola volta per ogni istanza Commerce.
1. [Configurazione del servizio sandbox](sandbox.md#enable-sandbox-testing) (oppure, in alternativa, procedere a [attivazione dei pagamenti in tempo reale](sandbox.md#enable-live-payments) se hai testato funzionalità in un altro ambiente) con un account di elaborazione del pagamento PayPal di prova.
1. [Imposta [!DNL Payment Services] come metodo di pagamento](production.md#set-payment-services-as-payment-method), in modalità sandbox, per iniziare a elaborare i pagamenti dei test.
1. [Richiesta di pagamento](production.md#request-payments-entitlement-from-adobe) per abilitare l’onboarding live.
1. [Onboarding completo](production.md#complete-merchant-onboarding) per abilitare i pagamenti live per i siti web Commerce.
1. [Ottieni il tuo [!DNL Payment Services] ID commerciante](production.md#configure-pricing-tier) e consegnarlo a Vendite per configurare il livello di prezzo corretto.
1. [Abilita [!DNL Payment Services] in modalità live](production.md#enable-live-payments) per iniziare a elaborare i pagamenti live.
1. Test dei pagamenti, in entrambi [sandbox](sandbox.md#test-in-sandbox-environment) e [produzione](production.md#test-in-production) ambienti.

>[!NOTE]
>
>Se non configuri Commerce Services nell’amministratore (passaggio 3), non puoi impostare sandbox o pagamenti live.

## Risoluzione dei problemi

* [Risolvere i problemi [!DNL Payment Services] installazione](https://support.magento.com/hc/en-us/articles/4406603542541)
* [Account sandbox PayPal non verificato](https://support.magento.com/hc/en-us/articles/4406954952461)
* [Ritardato [!DNL Payment Services] dati del report](https://support.magento.com/hc/en-us/articles/4406114741517)
* [Il test della carta di credito non riesce con PayPal durante l&#39;elaborazione dei pagamenti in un ambiente Sandbox](https://support.magento.com/hc/en-us/articles/5201041963917)
