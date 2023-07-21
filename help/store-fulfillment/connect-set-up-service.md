---
title: Collegare la soluzione di distribuzione del punto vendita
description: Stabilire le connessioni tra Adobe Commerce e la soluzione di Store Fulfillment. Crea e autorizza un’integrazione Adobe Commerce e aggiungi le credenziali dell’account Store Fulfillment alla configurazione del servizio Adobe Commerce.
role: Admin, Developer
level: Intermediate
feature: Shipping/Delivery, Install, Configuration, User Account, Tools and External Services
exl-id: 74c71c43-305a-4ea7-84f8-95f3ce0a9482
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Collegare la soluzione di distribuzione del punto vendita

Connettere Store Fulfillment Services ad Adobe Commerce aggiungendo all’amministratore di Adobe Commerce le credenziali di autenticazione e i dati di connessione richiesti.

- **[Configura [!DNL Commerce integration settings]](#create-an-adobe-commerce-integration)**: crea un’integrazione Adobe Commerce per i servizi di Store Fulfillment e genera i token di accesso per autenticare le richieste in ingresso dai server Store Fulfillment.

- **[Configura le credenziali dell&#39;account per Store Fulfillment Services](#configure-store-fulfillment-account-credentials)**-Aggiungi le credenziali per collegare Adobe Commerce al tuo account Store Fulfillment.

>[!NOTE]
>
>Completa la configurazione della connessione e convalidala correttamente prima di iniziare il test.

## Creare un’integrazione Adobe Commerce

Per integrare Adobe Commerce con i servizi di Store Fulfillment, puoi creare un’integrazione Commerce e generare token di accesso che possono essere utilizzati per autenticare le richieste dai server di Store Fulfillment. È inoltre necessario aggiornare Adobe Commerce [!UICONTROL Consumer Settings] opzioni per impedire `The consumer isn't authorized to access %resources.` errori di risposta nelle richieste da Adobe Commerce a [!DNL Store Fulfillment] servizi.

1. Dall’amministratore, crea l’integrazione per l’evasione del punto vendita.

   - Denomina l&#39;estensione
   - Inserisci il tuo indirizzo e-mail
   - Immetti la password dell&#39;account amministratore

1. Configura le autorizzazioni di accesso alle risorse API per l’integrazione con quanto segue:

   - Vendite > Aggiornamento ordine BOPIS
   - Sistema > Autorizzazioni app di esecuzione store

1. Genera i token di accesso per l’autenticazione salvando e attivando l’integrazione.

1. Copiare e salvare i token di accesso in una posizione sicura e crittografata.

1. Collabora con il tuo Account Manager per completare la configurazione sul lato Store Fulfillment e per autorizzare l’integrazione.

1. Abilita Adobe Commerce [!UICONTROL Consumer Settings] opzione per [!UICONTROL Allow OAuth Access Tokens to be used as standalone Bearer tokens].

   - Dall’amministratore, vai a **[!UICONTROL Stores]** >  [!UICONTROL Configuration] > **[!UICONTROL Services]** >  **[!UICONTROL OAuth]** > **[!UICONTROL Consumer Settings]**

   - Imposta il [!UICONTROL Allow OAuth Access Tokens to be used as standalone Bearer tokens] opzione per **[!UICONTROL Yes]**.

>[!IMPORTANT]
>
> Il token di integrazione è specifico per l’ambiente. Se si ripristina il database per un ambiente con i dati di origine provenienti da un ambiente diverso, ad esempio il ripristino dei dati di produzione da un ambiente di staging, escludere `oauth_token` nell’esportazione del database, in modo che i dettagli del token di integrazione non vengano sovrascritti durante l’operazione di ripristino.


## Configura credenziali account di evasione archivio

Dopo aver completato il modulo di accettazione, viene creato un account di evasione del negozio Walmart. Riceverai le seguenti credenziali quando saranno disponibili:

- [!DNL Merchant ID]
- [!DNL Consumer ID]
- [!DNL Consumer Secret]
- [!DNL API Server URL]
- [!DNL Token Auth Server URL] (in genere corrisponde alla configurazione precedente)

Queste credenziali sono necessarie per configurare e utilizzare Store Fulfillment.

>[!NOTE]
>
>Il completamento del processo di creazione dell’account può richiedere del tempo. Mentre attendi le credenziali, [rivedere e configurare altre impostazioni per la soluzione Store Fulfillment](service-config-settings-overview.md).

### Aggiungi credenziali per la connessione a Store Fulfillment

1. Configura [credenziali account](enable-general.md) per gli ambienti di produzione e sandbox.

1. Dall’amministratore, vai a **[!UICONTROL Stores > Configuration > Services > Store Fulfillment by Walmart Commerce Technologies]**

1. Immetti le credenziali account fornite per **[!UICONTROL Production environment]**. Tutti i campi sono obbligatori.

1. Seleziona **[!UICONTROL Save Config]**.

1. Verifica la connessione selezionando **[!UICONTROL Validate Credentials]**.

>[!NOTE]
>
>Se le credenziali non sono valide, verifica di aver immesso i valori corretti per ogni ambiente e riconvalida. Se riscontri ancora problemi durante la connessione, contatta il rappresentante del tuo account.
