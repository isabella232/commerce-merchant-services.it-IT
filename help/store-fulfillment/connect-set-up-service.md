---
title: Collegare la soluzione Store Fulfillment
description: Stabilisci le connessioni tra Adobe Commerce e la soluzione Store Fulfillment creando e autorizzando un'integrazione Adobe Commerce e aggiungendo le credenziali dell'account Store Fulfillment alla configurazione del servizio Adobe Commerce.
role: User, Admin
level: Intermediate
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Collegare la soluzione Store Fulfillment

Stabilisci la connessione tra Adobe Commerce e i servizi Store Fulfillment configurando le credenziali di autenticazione e i dati di connessione richiesti dall&#39;amministratore.

- **[Configura [!DNL Commerce integration settings]](#create-the-commerce-integration)**- Crea un’integrazione Adobe Commerce per i servizi Store Fulfillment e genera i token di accesso per autenticare le richieste in arrivo dai server Store Fulfillment.

- **[Configurare le credenziali dell&#39;account per i servizi di evasione dell&#39;archivio](#configure-store-fulfillment-account-credentials)**- Aggiungi le tue credenziali per collegare Adobe Commerce al tuo account Store Fulfillment.

>[!NOTE]
>
>Completare la configurazione della connessione e convalidarla prima di iniziare il test.

## Creare un’integrazione Adobe Commerce

Per integrare Adobe Commerce con i servizi Store Fulfillment, crea un’integrazione Commerce e genera token di accesso che possono essere utilizzati per autenticare le richieste dai server Store Fulfillment.

1. Dall’amministratore, crea l’integrazione per l’esecuzione dello store.

   - Denomina l&#39;estensione
   - Inserisci il tuo indirizzo e-mail
   - Immetti la password dell&#39;account amministratore

1. Configura [!UICONTROL API Resource Access permissions] per l’integrazione, seleziona `[!UICONTROL All]`

1. Genera i token di accesso per l’autenticazione salvando e attivando l’integrazione.

1. Copia e salva i token di accesso in una posizione protetta e crittografata.

1. Collabora con il tuo Account Manager per completare la configurazione sul lato Store Fulfillment e autorizzare l&#39;integrazione.


>[!NOTE]
>
>Per istruzioni dettagliate, vedi [Integrazioni](https://docs.magento.com/user-guide/system/integrations.html) in _Guida utente di Adobe Commerce_.

## Configurare le credenziali dell’account di evasione dell’archivio

Dopo aver completato il modulo di assunzione, viene creato per voi un account Walmart Store Fulfillment. Quando saranno disponibili, riceverai le seguenti credenziali:

- [!DNL Merchant I]D
- [!DNL Consumer ID]
- [!DNL Consumer Secret]
- [!DNL API Server URL]
- [!DNL Token Auth Server URL] (solitamente la stessa configurazione di cui sopra)

Queste credenziali sono necessarie per configurare e utilizzare Store Fulfillment.

>[!NOTE]
>
>Il completamento del processo di creazione dell’account può richiedere del tempo. In attesa delle credenziali, [rivedere e configurare altre impostazioni per la soluzione Store Fulfillment](service-config-settings-overview.md).

### Aggiungi le credenziali per la connessione all&#39;evasione dell&#39;archivio

1. Configura [credenziali account](enable-general.md) per gli ambienti Production e Sandbox.

1. Dall’amministratore, vai a **[!UICONTROL Stores > Configuration > Services > Store Fulfillment by Walmart Commerce Technologies]**

1. Immetti le credenziali account fornite per la **[!UICONTROL Production environment]**. Tutti i campi sono obbligatori.

1. Seleziona **[!UICONTROL Save Config]**.

1. Verificare la connessione selezionando **[!UICONTROL Validate Credentials]**.

>[!NOTE]
>
>Se le credenziali non sono valide, verifica di aver immesso i valori corretti per ogni ambiente e riconvalida. Contatta il rappresentante commerciale di riferimento per eventuali problemi di connessione.








