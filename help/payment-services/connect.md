---
title: Connetti l'istanza
description: Collega la tua istanza Commerce utilizzando una chiave API e una chiave privata e specifica lo spazio dati nella configurazione.
exl-id: 5038fd31-bac5-419e-a172-66919a9b5272
source-git-commit: 817a01e98876bddf5f41a253501984539b3351cd
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Connetti l&#39;istanza

[!DNL Payment Services] è alimentato da Commerce Services e implementato come SaaS (software as a service). Collega la tua istanza Commerce utilizzando una chiave API e una chiave privata e specifica lo spazio dati nella configurazione utilizzando l’ [Connettore Commerce Services](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html). **Questa connessione viene impostata una sola volta.**

* Se *ha già connesso l&#39;istanza*, ottenendo e utilizzando le credenziali API e configurando Commerce Services, puoi procedere a [configurazione della sandbox di test](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/sandbox.html).
* Se sei ancora *per collegare l’istanza*, consulta le informazioni in questo argomento su [ottenimento delle credenziali API](#obtain-api-credentials) e [configurazione di Commerce Services](#configure-commerce-services).
* Se sei *non assicurati che l&#39;istanza sia connessa*, passa a **Sistema** > Servizi > **Connettore Commerce Services** e visualizzare i valori delle chiavi API pubbliche e private nella [!UICONTROL Sandbox Keys] e [!UICONTROL Production Keys] le sezioni e *Progetto* e *Spazio dei dati* nei campi [!UICONTROL SaaS Identifier] sezione . Se tali valori sono presenti, l’istanza viene connessa.

## Ottenere le credenziali API

Per utilizzare un servizio Commerce SaaS, devi utilizzare le chiavi API della tua istanza (chiave API pubblica Commerce e chiave privata) sia per la sandbox che per la produzione, che vengono create e gestite nel tuo [Dashboard del mio account](https://account.magento.com/customer/account/login). [La coppia di chiavi](https://docs.magento.com/user-guide/configuration/services/saas.html) può essere creato per un account Commerce, uno per sandbox e uno per la produzione, anche se è possibile utilizzare attivamente una sola coppia alla volta.

>[!NOTE]
>
>Hai bisogno di aiuto per accedere al tuo [!UICONTROL My Account] dashboard? Vedi [Creare un account Commerce](https://docs.magento.com/user-guide/magento/magento-account-create.html).

Una volta creata, una chiave API pubblica è sempre disponibile nel dashboard Il mio account. Può essere copiato o eliminato in base alle esigenze. La chiave API privata diventa visibile quando crei una chiave API pubblica per sandbox o produzione; è disponibile solo per la copia o il salvataggio dalla finestra di dialogo successiva e non è possibile accedervi in un secondo momento.

Una determinata coppia di chiavi API è valida per tutti i Commerce Services in un ambiente, quindi se hai già configurato Commerce Services per la tua istanza, la coppia di chiavi API è già presente nel connettore Commerce Services.

Se la chiave API viene persa, è necessario creare una nuova coppia di chiavi API [generato](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/connect.html#generate-an-api-key-and-private-key) e [applicato](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/connect.html#configure-saas-project) alla configurazione Commerce Services Connector nell’amministratore. Se nella configurazione sono configurate le chiavi errate o non ne sono presenti nessuna, in Servizi di pagamento viene visualizzata una finestra di dialogo di errore per la verifica dell&#39;account che informa che l&#39;account non è stato verificato.

Vedi [elenco dei servizi Commerce disponibili che utilizzano API](https://docs.magento.com/user-guide/system/saas.html#available-services).

Per informazioni su come generare una chiave API per gli ambienti sandbox o di produzione, consulta [Credenziali](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html#apikey).

>[!IMPORTANT]
>Si consiglia di non generare una coppia di chiavi API *e* modifica l’identificatore SaaS e/o lo spazio dati in un’istanza di produzione attiva. Se vengono modificati, i dati relativi all’istanza andranno persi.

## Configurare Commerce Services

La stessa chiave API può essere utilizzata tra le istanze, ma ogni istanza deve avere una propria [Spazio dei dati SaaS](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html#saasenv).

Dopo aver ottenuto le credenziali, puoi configurare il progetto SaaS e Saas Data Space.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]**.
1. Fai clic su **[!UICONTROL Configure Commerce Services]**.

   Questa opzione è visibile se non hai ancora configurato Commerce Services per il tuo account.

   Sei indirizzato all’area di configurazione in Admin, **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**>**[!UICONTROL Commerce Services Connector]**, per configurare il connettore Commerce Services.

1. Per configurare Commerce Services, segui i passaggi descritti in [Configurazione SaaS](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html#saasenv).
