---
title: Onboarding [!DNL Payment Services]
description: Connettere l’istanza con [!DNL Payment Services] completando alcuni passaggi di onboarding.
role: User
level: Intermediate
exl-id: 1ee8c660-0941-4378-a1d7-ae45de3de211
feature: Payments, Checkout, Integration
source-git-commit: 90bfa7099924feb308397960cff76bdf177bbe49
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---

# Onboarding [!DNL Payment Services]

Per iniziare a utilizzare [!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source], devi completare alcuni passaggi di onboarding per collegare la tua istanza con la funzionalità di pagamento.

## Flusso di onboarding

![Flusso di onboarding](assets/onboarding-diagram.svg)

Questo diagramma di flusso di onboarding illustra il processo generale di onboarding [!DNL Payment Services].

Dopo aver completato l’onboarding per i pagamenti sandbox o live, il reporting finanziario è accessibile da [!DNL Payment Services] in Admin.

Se i pagamenti sandbox e live sono entrambi integrati e abilitati, puoi passare facilmente da una modalità all’altra dalla modalità [!DNL Payment Services] A casa.

## Prerequisiti

Per utilizzare [!DNL Payment Services], per la tua istanza devi disporre dei seguenti elementi:

* Modulo Connettore servizi
* Modulo ID servizi
* Chiavi API

I moduli Connettore servizi e ID servizi vengono installati automaticamente durante [installazione di [!DNL Payment Services]](install.md). Al termine dell’installazione, sarà possibile visualizzare una nuova sezione nelle impostazioni di configurazione (**[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**) quando si espande **[!UICONTROL Services]**—**[!UICONTROL Commerce Services Connector]**.

Per informazioni su come creare o accedere alle chiavi API, consulta [Credenziali API](#obtain-api-credentials).

## Passaggi di onboarding

1. [Installare [!DNL Payment Services] estensione](install.md#get-payment-services).
1. [Ottenere le credenziali API](connect.md#obtain-api-credentials).
1. [Connetti l’istanza](connect.md#configure-commerce-services) in Commerce Services. Questa connessione deve essere completata una sola volta per ogni istanza di Commerce.
1. [Configurare il servizio sandbox](sandbox.md#enable-sandbox-testing) (o, in alternativa, procedere con [abilitazione dei pagamenti live](sandbox.md#enable-live-payments) se hai testato funzionalità in un altro ambiente) con un account di elaborazione pagamento PayPal di prova.
1. [Imposta [!DNL Payment Services] come metodo di pagamento](production.md#set-payment-services-as-payment-method), in modalità sandbox, per iniziare a elaborare i pagamenti di test.
1. [Richiedi pagamento diritto](production.md#request-payments-entitlement-from-adobe) per abilitare l’onboarding live.
1. [Onboarding completo per gli esercenti](production.md#complete-merchant-onboarding) per abilitare i pagamenti live per i siti web Commerce.
1. [Ottieni [!DNL Payment Services] ID esercente](production.md#configure-pricing-tier) e passarlo al reparto Vendite per configurare il piano tariffario corretto.
1. [Abilita [!DNL Payment Services] in modalità live](production.md#enable-live-payments) per iniziare a elaborare i pagamenti live.
1. Pagamenti di prova, in entrambi [sandbox](sandbox.md#test-in-sandbox-environment) e [produzione](production.md#test-in-production) ambienti.

>[!NOTE]
>
>Se non configuri Commerce Services nell’amministratore (passaggio 3), non puoi impostare pagamenti sandbox o live.

## Risoluzione dei problemi

* [Risoluzione dei problemi [!DNL Payment Services] installazione](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-install.html?lang=en)
* [Conto sandbox PayPal non verificato](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-paypal-acct.html)
* [Ritardato [!DNL Payment Services] dati del rapporto](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-report-info-delayed.html)
* [Il test della carta di credito non riesce con PayPal quando si elaborano i pagamenti in un ambiente Sandbox](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-cc-sandbox-failure.html?lang=en)
