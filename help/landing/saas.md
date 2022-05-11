---
title: Connettore Commerce Services
description: Scopri come integrare l’istanza di Adobe Commerce o Magento Open Source ai servizi utilizzando una chiave API e una chiave privata.
exl-id: 28027a83-449b-4b96-b926-a7bfbfd883d8
source-git-commit: 3035edd14ca6d7b29e7fa6f4c6ed2a66401171c1
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---

# [!DNL Commerce Services Connector]

Alcune funzioni di Adobe Commerce e Magento Open Source sono fornite da [!DNL Commerce Services]  e implementato come SaaS (software come servizio). Per utilizzare questi servizi, è necessario collegare la [!DNL Commerce] , utilizzando una chiave API e una chiave privata, e specifica lo spazio dati nel [configurazione](https://docs.magento.com/user-guide/configuration/services/saas.html). È sufficiente impostare questa configurazione una sola volta.

## Servizi disponibili

Di seguito sono elencati i [!DNL Commerce] funzioni accessibili tramite [!DNL Commerce Services Connector]:

| Servizio | Disponibilità |
| ---|--- |
| [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) con tecnologia Adobe Sensei | Adobe Commerce |
| [[!DNL Live Search]](/help/live-search/overview.md) con tecnologia Adobe Sensei | Adobe Commerce |
| [[!DNL Payment Services]](/help/payment-services/overview.md) | Adobe Commerce e Magento Open Source |

## Architettura

Ad alto livello, [!DNL Commerce Services Connector] è costituito dai seguenti elementi principali:

![Architettura del connettore Commerce Services](assets/saas-config-sync-workflow.png)

Le sezioni seguenti trattano ciascuno di questi elementi in modo più dettagliato.

## Credenziali {#apikey}

La chiave API e la chiave privata sono generate dalla [!DNL Commerce] conto del titolare della licenza, identificato da un [!DNL Commerce] ID (MageID). Per superare la convalida dell&#39;adesione per servizi quali [!DNL Product Recommendations] o [!DNL Live Search], il titolare della licenza dell&#39;organizzazione del commerciante può generare l&#39;insieme di chiavi API purché l&#39;account sia in buona posizione. Le chiavi possono essere condivise in base alla &quot;necessità di sapere&quot; con l&#39;integratore di sistemi o il team di sviluppo che gestisce progetti e ambienti per conto del titolare della licenza. Inoltre, gli integratori di soluzioni possono utilizzare [!DNL Commerce Services]. Se sei un integratore di soluzioni, il firmatario della [!DNL Commerce] il contratto con un partner deve generare le chiavi API.

### Generare una chiave API e una chiave privata {#genapikey}

1. Accedi al tuo [!DNL Commerce] conto a [https://account.magento.com](https://account.magento.com/){:target=&quot;_blank&quot;}.

1. Sotto la **Magento** scheda , seleziona **Portale API** sulla barra laterale.

1. Da _Ambiente_ menu, seleziona **Produzione** o **Sandbox**.

1. Immetti un nome nella _Chiavi API_ e fai clic su **Aggiungi nuovo**.

   Viene visualizzata una finestra di dialogo per il download della nuova chiave.

   ![Scarica chiave privata](assets/download-api-private-key.png)

   >[!WARNING]
   >
   > Questa è l’unica opportunità che hai per copiare o scaricare la tua chiave.

1. Fai clic su **Scarica** quindi fai clic su **Annulla**.

   La **Chiavi API** visualizza la chiave API. È necessaria sia la chiave API che la chiave privata quando si [selezionare o creare un progetto SaaS](#createsaasenv).

## Configurazione SaaS {#saasenv}

[!DNL Commerce] Le istanze devono essere configurate con un progetto SaaS e uno spazio dati SaaS in modo che [!DNL Commerce Services] può inviare i dati alla posizione giusta. Un progetto SaaS raggruppa tutti gli spazi dati SaaS. Gli spazi dati SaaS vengono utilizzati per raccogliere e memorizzare dati che consentono [!DNL Commerce Services] per lavorare. Alcuni di questi dati possono essere esportati dal [!DNL Commerce] istanza e alcuni possono essere raccolti dal comportamento dell&#39;acquirente sulla vetrina. Tali dati vengono quindi mantenuti per proteggere l&#39;archiviazione cloud.

Per [!DNL Product Recommendations], lo spazio dati SaaS contiene dati di catalogo e comportamentali. Puoi puntare a [!DNL Commerce] istanza a uno spazio dati SaaS per [selezionarlo](https://docs.magento.com/user-guide/configuration/services/saas.html) in [!DNL Commerce] configurazione.

>[!WARNING]
>
> Utilizza lo spazio dati SaaS di produzione solo nella produzione [!DNL Commerce] per evitare conflitti tra dati. In caso contrario, si rischia di inquinare i dati del sito di produzione con dati di test, causando ritardi nella distribuzione. Ad esempio, i dati di prodotto di produzione potrebbero essere sovrascritti erroneamente dai dati di staging, come gli URL di staging.

### Selezionare o creare un progetto SaaS {#createsaasenv}

>[!NOTE]
>
> Se non visualizzi il **[!UICONTROL Commerce Services Connector]** nella sezione [!DNL Commerce] configurazione, è necessario installare [!DNL Commerce] moduli per le tue esigenze [!DNL Commerce] servizio, quali [[!DNL Product Recommendations]](/help/product-recommendations/install-configure.md).

Per selezionare o creare un progetto SaaS, richiedi al [!DNL Commerce] Chiave API dalla [!DNL Commerce] titolare della licenza per il tuo negozio.

1. Sulla _Amministratore_ barra laterale, vai a **Negozi** > _Impostazioni_ > **Configurazione**.

1. Nel pannello a sinistra, espandi **Servizi** e scegli **Connettore Commerce Services**.

1. In _Chiavi API_ incolla i valori chiave per **Chiave API di produzione** e **Chiave privata produzione**.

   Le chiavi private devono includere `----BEGIN PRIVATE KEY---` all&#39;inizio della chiave e `----END PRIVATE KEY----` alla fine della chiave privata.

1. Fai clic su **Salva configurazione**.

Eventuali progetti SaaS associati alla chiave API vengono visualizzati nella sezione **Progetto SaaS** campo .

1. Se non esistono progetti SaaS, fai clic su **Crea progetto**. Poi nella **Nome progetto** immettere un nome per il progetto SaaS.

   Quando crei un progetto SaaS, [!DNL Commerce] genera uno o più spazi dati SaaS a seconda del tuo [!DNL Commerce] licenza:
   - Adobe Commerce - Uno spazio dati di produzione; due aree dati di prova
   - Magento Open Source - uno spazio dati di produzione; nessuna verifica degli spazi dati

1. Seleziona la **Spazio dei dati SaaS** da utilizzare per la configurazione corrente del [!DNL Commerce] archiviare.

>[!WARNING]
>
> Se generi nuove chiavi nella sezione Portale API del mio account, aggiorna immediatamente le chiavi API nella configurazione Amministratore. Se generi nuove chiavi e non le aggiorni nell’amministratore, le estensioni SaaS non funzionano più e si perdono dati preziosi.

Per modificare i nomi del progetto SaaS o dello spazio dati, fai clic sul pulsante **Rinomina progetto** o **Rinomina spazio dati** rispettivamente.

## Sincronizzazione catalogo

Quando il [!DNL Commerce] l&#39;istanza si connette correttamente a [!DNL Commerce Services], il processo di sincronizzazione del catalogo esporta i dati di prodotto dal tuo [!DNL Commerce] server a [!DNL Commerce Services]. [Ulteriori informazioni](catalog-sync.md) informazioni sul processo di sincronizzazione del catalogo.
