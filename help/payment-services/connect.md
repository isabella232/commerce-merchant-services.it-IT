---
title: Collegare l'istanza
description: Collega la tua istanza Commerce utilizzando una chiave API e una chiave privata e specifica lo spazio dati nella configurazione.
exl-id: 5038fd31-bac5-419e-a172-66919a9b5272
source-git-commit: 9596815e31402f23b399b223f3221074331c1773
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Collegare l&#39;istanza

[!DNL Payment Services] è alimentato da Commerce Services e implementato come SaaS (software as a service). Collega la tua istanza Commerce utilizzando una chiave API e una chiave privata e specifica lo spazio dati nella configurazione. Questa connessione viene impostata una sola volta.

Vedi [Connettore Commerce Services](https://docs.magento.com/user-guide/system/saas.html){target=&quot;_blank&quot;} nella guida utente principale per informazioni dettagliate su questo servizio.

## Ottenere le credenziali API

Per utilizzare un servizio Commerce SaaS, devi utilizzare le chiavi API della tua istanza, che vengono create e gestite nel tuo [Dashboard del mio account](https://account.magento.com/customer/account/login){target=&quot;_blank&quot;}. È possibile creare due coppie di chiavi API diverse per un account Commerce, una per sandbox e una per la produzione (pagamenti live), anche se è possibile utilizzare attivamente una sola coppia alla volta.

>[!NOTE]
>
>Hai bisogno di aiuto per accedere al tuo [!UICONTROL My Account] dashboard? Vedi [Creare un account Commerce](https://docs.magento.com/user-guide/magento/magento-account-create.html){target=&quot;_blank&quot;} nella guida utente principale.

Una determinata coppia di chiavi API è valida per tutti i Commerce Services in un ambiente, quindi se hai già configurato Commerce Services per la tua istanza Commerce la tua coppia di chiavi API è già presente nell’amministratore. Se la chiave API privata viene persa, è necessario generare una nuova coppia di chiavi API da applicare alla configurazione Commerce Services nell’amministratore.

Per informazioni su come generare una chiave API per gli ambienti sandbox o di produzione, consulta [Connettore Commerce Services](https://docs.magento.com/user-guide/system/saas.html){target=&quot;_blank&quot;} nella guida utente principale.

>[!IMPORTANT]
>
>Se rigeneri una coppia di chiavi API e modifichi l’identificatore SaaS, tutti i Commerce Services utilizzati da questa istanza si connettono a un archivio dati diverso e l’accesso (inclusi i dati memorizzati in precedenza) viene perso. Si consiglia di non generare una coppia di chiavi API e di modificare l’identificatore SaaS su un’istanza di produzione attiva.

### Chiave API Commerce e chiave privata

Alcuni [!DNL Adobe Commerce] e [!DNL Magento Open Source] Le funzioni sono distribuite come SaaS (software as a service), noto come Commerce Services. Per utilizzare questi servizi, devi collegare la tua istanza Commerce a questi servizi utilizzando una chiave API e una chiave privata e specificare lo spazio dati desiderato nel [configurazione](https://docs.magento.com/user-guide/configuration/services/saas.html){target=&quot;_blank&quot;}.

Quando crei un account Commerce identificato da un MageID, puoi generare una chiave API Commerce e una chiave privata. Per utilizzare Commerce Services, ad esempio [!DNL Payment Services], [!DNL Product Recommendations]oppure [!DNL Live Search], il titolare della licenza deve generare tali chiavi per superare la convalida dell&#39;adesione. Queste chiavi possono quindi essere passate al team di integrazione dei sistemi o di sviluppo che gestisce i progetti e gli ambienti per conto del titolare della licenza. Se sei un integratore di soluzioni, hai anche il diritto di utilizzare questi servizi per le tue esigenze. In tal caso, il firmatario del contratto con il partner Commerce dovrebbe generare le chiavi.

### Generare una chiave API e una chiave privata

1. Accedi al tuo account Commerce all&#39;indirizzo [https://account.magento.com/customer/account/login](https://account.magento.com/customer/account/login).
1. Sotto la **[!UICONTROL Magento]** scheda , seleziona **[!UICONTROL API Portal]** sulla barra laterale.
1. Da _[!UICONTROL Environment]_menu, seleziona **[!UICONTROL Sandbox]**, quindi **[!UICONTROL Production]**.

   >[!IMPORTANT]
   >
   >Le chiavi API sono necessarie per entrambi gli ambienti.

1. Immetti un nome nella _[!UICONTROL API Keys]_e fai clic su **[!UICONTROL Add New]**.

   Questa azione apre una finestra di dialogo per scaricare la nuova chiave.

   >[!IMPORTANT]
   >
   >Questa finestra di dialogo è l’unica opportunità per copiare o scaricare la chiave.

1. Fai clic su **[!UICONTROL Download]** quindi fai clic su **[!UICONTROL Cancel]**.

   La _[!UICONTROL API Keys]_visualizza la chiave API.

1. Copia sia la chiave API che la chiave privata quando selezioni o crei un progetto SaaS.

   Vedi [SaaS](https://docs.magento.com/user-guide/system/saas.html){target=&quot;_blank&quot;} nella guida utente principale per informazioni più dettagliate.

La stessa chiave API può essere utilizzata tra le istanze, ma ogni istanza deve avere un proprio spazio dati SaaS.

Quando crei un progetto SaaS, Commerce genera uno o più spazi dati SaaS a seconda della licenza Commerce:

* [!DNL Adobe Commerce] - uno spazio dati di produzione; due aree dati di prova
* [!DNL Magento Open Source] - uno spazio dati di produzione; nessuna verifica degli spazi dati

### Configurare il progetto SaaS

>[!NOTE]
>
>Se non visualizzi il _[!UICONTROL Commerce Services Connector]_Nella sezione Configurazione Commerce , devi installare i moduli Commerce per il servizio Commerce desiderato, ad esempio [[!DNL Payment Services]](install.md).

Per selezionare o creare un progetto SaaS, richiede la chiave API Commerce al titolare della licenza Commerce per il tuo negozio.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Nel pannello a sinistra, espandi **[!UICONTROL Services]** e scegli **[!UICONTROL Commerce Services Connector]**.
1. In _[!UICONTROL API Keys]_incolla i valori chiave.

   >[!IMPORTANT]
   >
   >Aggiungi valori chiave per entrambi **[!UICONTROL sandbox]** e **[!UICONTROL production]** ambienti.

1. Clic **[!UICONTROL Save Config]**.

   Quando salvi, se sono presenti progetti SaaS associati alla chiave API, tali progetti vengono visualizzati nella _[!UICONTROL SaaS Project]_nel campo_[!UICONTROL SaaS Identifier]_ sezione .

1. Se non esistono progetti SaaS, fai clic su **[!UICONTROL Create Project]**. Quindi inserisci un nome per il progetto SaaS nel **[!UICONTROL Project Name]** campo .
1. Per utilizzare per la configurazione corrente del tuo Negozio Commerce, seleziona la **[!UICONTROL SaaS Data Space]**.

>[!IMPORTANT]
>
>Se rigeneri le chiavi nella sezione Portale API del mio account, aggiorna immediatamente le chiavi API nella configurazione Amministratore. Se generi nuove chiavi e non le aggiorni nell’amministratore, le estensioni SaaS non funzioneranno più e perderai dati preziosi.

Per modificare i nomi, fai clic sul pulsante **[!UICONTROL Rename this Project]** o **[!UICONTROL Rename Data Space]** rispettivamente.

## Configurare Commerce Services

Il primo passo nell&#39;onboarding [!DNL Payment Services] è per configurare Commerce Services nell’amministratore.

1. Sulla _Amministratore_ barra laterale, vai a **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]**.
1. Clic **[!UICONTROL Configure Commerce Services]**.

   Questa opzione è visibile se non hai ancora configurato Commerce Services per il tuo account.

   Sei indirizzato all’area di configurazione in Admin, **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**>**[!UICONTROL Commerce Services Connector]**, per configurare il connettore Commerce Services.

1. Per configurare Commerce Services, segui i passaggi descritti in [Commerce Services](https://docs.magento.com/user-guide/system/saas.html#createsaasenv){target=&quot;_blank&quot;}.
