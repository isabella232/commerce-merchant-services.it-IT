---
title: Protezione contro le frodi Signifyd
description: Protezione automatizzata contro le frodi per [!DNL Payment Services] con Signifyd.
role: Admin, User
level: Intermediate
feature: Payments, Checkout, Configuration, Security
source-git-commit: 400d1f8a384fceebcd13e9496f8e218e694d2752
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---


# Protezione contro le frodi significative

È possibile abilitare la protezione automatizzata contro le frodi per [!DNL Payment Services] con [Estensione Signifyd](https://commercemarketplace.adobe.com/signifyd-module-connect.html).

Adobe Commerce supporta Signifyd versioni 5.4.0 e successive. [!DNL Payment Services] supporta i flussi Signifyd pre-autenticazione e post-autenticazione.

Consulta [Documentazione di Signifyd](https://community.signifyd.com/support/s/article/magento-2-extension-install-guide?language=en_US#downloadandinstallingmagento2extension) per informazioni sull&#39;installazione e la configurazione dell&#39;estensione.

## Limitazioni dell’integrazione

Attualmente, le seguenti limitazioni si applicano all’integrazione tra Signifyd e [!DNL Payment Services]:

* Signifyd/[!DNL Payment Services] l’integrazione supporta solo [campi carta di credito](../payment-services/payments-options.md#credit-card-fields) (non i pulsanti PayPal o Apple Pay). [!DNL Payment Services] invia i dati dell&#39;ordine ricevuti tramite i pulsanti di pagamento PayPal e Apple Pay a Signifyd, ma l&#39;integrazione fornisce solo i dettagli per gli ordini effettuati tramite i campi della carta di credito.
* Signifyd non supporta gli ordini di un acquirente immessi nell’amministratore da un commerciante.
* Signifyd non supporta gli ordini effettuati con [carte di credito a pagamento](../payment-services/vaulting.md).

## Onboarding

È necessario comunicare direttamente con Signifyd per integrare l’estensione da utilizzare con [!DNL Payment Services]—non esiste [!DNL Payment Services] configurazione necessaria. Una volta installata, puoi configurare l’estensione Signifyd in Admin. Qualsiasi supporto relativo a questa estensione verrà gestito da Signifyd.

Durante l’onboarding con Signifyd è necessario:

1. Contatta Signifyd per impostare un nuovo account.
1. Per impostazione predefinita, Signifyd è [inserito nell&#39;elenco Consentiti](https://github.com/signifyd/magento2/blob/main/docs/RESTRICT-PAYMENTS.md) affinché Signifyd non venga attivato per altre opzioni di pagamento attualmente non supportate. Se si desidera vietare un particolare metodo di pagamento, è necessario apportare modifiche.
1. Conferma con Signifyd che PayPal non rifiuterà gli ordini che potrebbero essere approvati da Signifyd tramite l&#39;impostazione di protezione dalle frodi del commerciante in Paypal.
1. Abilita l’estensione Signifyd per la compatibilità con [!DNL Payment Services]:
   * Quando si utilizza [!DNL Payment Services] in _Live_ , Signifyd deve essere in modalità Produzione.
   * Quando si utilizza [!DNL Payment Services] in _Sandbox_ Signifyd deve essere in modalità di test.

## Configurazione

Poiché Signifyd esegue alcune azioni sugli ordini, è necessario configurare l’estensione in modo che si comporti in modo appropriato in base all’azione di pagamento impostata per [!DNL Payment Services].

Queste opzioni di configurazione non sono compatibili con Payment Services e l’integrazione Signifyd:

* Quando [!DNL Payment Services] è configurato con `Authorize` azione di pagamento _e_ Signifyd è in `PostAuth` modalità con _[!UICONTROL Decline Guarantees]_opzione impostata su **Crea nota di accredito**.

  Motivo: [!DNL Payment Services] crea una transazione di autorizzazione che Signify tenta quindi di rimborsare.


* [!DNL Payment Services] è configurato con `Authorize and Capture` azione di pagamento _e_ Signifyd è in `PostAuth` modalità con _[!UICONTROL Decline Guarantees]_opzione impostata su **Annulla ordine**.

  Motivo: [!DNL Payment Services] crea una transazione di acquisizione che Signifyd tenta quindi di annullare.


Consulta la documentazione di Signifyd per informazioni su [configurazione dell&#39;estensione](https://community.signifyd.com/support/s/article/magento-2-extension-install-guide?language=en_US#configuringmagento2extension).

Consulta la documentazione di Signifyd per [ulteriori informazioni sui flussi di lavoro degli ordini](https://community.signifyd.com/support/s/article/magento-2-extension-install-guide?language=en_US#howmagento2works).
