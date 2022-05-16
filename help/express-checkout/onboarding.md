---
title: A bordo [!DNL Express Checkout] per estensione Adobe Commerce
description: Scopri come [!DNL Express Checkout] potrebbe trarre vantaggio dalla tua istanza di Adobe Commerce e da come effettuare l'onboarding e la configurazione dell'estensione.
exl-id: 8caf746c-e31b-4331-8b0d-ea0f1e545bdd
source-git-commit: bd9541c5e4810085ab85206b2ecca21e66800a2f
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# [!DNL Express Checkout] onboarding

>[!IMPORTANT]
>
> Questa funzione è disponibile solo per gli utenti del programma Early Adopter (EAP) e non è ancora accessibile per tutti i clienti. Attualmente limitato ai clienti statunitensi. Per assistenza e domande, contatta il supporto Adobe Commerce.

Per iniziare a utilizzare [!DNL Express Checkout] per l’estensione Adobe Commerce devi completare alcuni passaggi onboarding per collegare la tua istanza alla nostra funzionalità di pagamento.

1. [Ottieni estensione](#get-extension).
1. [Crea un account commerciale di produzione o sandbox con [!DNL Bolt]](#create-account-with-bolt). Fornisci tutte le informazioni necessarie per verificare la tua identità.
1. [Fornisci la chiave API univoca e la chiave pubblicabile generate in [!DNL Bolt]](#obtain-api-credentials).
1. [Imposta un provider di pagamento nel [!DNL Bolt] account](#configure-payment-providers).
1. [Imposta il menu a discesa Abilita su Sì](#enable-extension) per attivare l&#39;estensione.
1. [Definire le impostazioni del servizio](#complete-admin-configuration) per configurare [!DNL Express Checkout] estensione.
1. [Fai clic sul pulsante Salva configurazione](#enable-live-express-checkout) per abilitare l&#39;estensione.

>[!NOTE]
>
> Se non si configura il [!DNL Bolt] account (passaggio 2 precedente) non è possibile configurare gli ambienti sandbox o di produzione.

## Prerequisiti

Per utilizzare il [!DNL Express Checkout], è necessario disporre delle seguenti opzioni [!DNL Bolt]:

- Provider di pagamenti supportati
- Conto del commerciante e della produzione in [!DNL Bolt]
- API e chiave pubblicabile generata in [!DNL Bolt]

Fai riferimento a [prerequisiti](../express-checkout/prerequisites.md) per ulteriori informazioni.

Vedi [Credenziali API](#obtain-api-credentials) per scoprire come creare o accedere alle chiavi API della tua istanza.

## Ottieni estensione

Consulta la sezione [installare](../express-checkout/install.md) per informazioni dettagliate su come ottenere l&#39;estensione.

## Crea account con bullone

Prima di configurare la [!DNL Express Checkout] nell’amministratore di Adobe Commerce è necessario creare un [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} e [produzione](https://merchant.bolt.com/register){target=&quot;_blank&quot;} account commerciale in [!DNL Bolt]. Fornisci tutti i dettagli richiesti per creare un account in [!DNL Bolt].

Fai riferimento a [verificare e convalidare](../express-checkout/testing.md) per ulteriori informazioni.

## Ottenere le credenziali API

Per utilizzare [!DNL Express Checkout] richiede [!DNL Bolt] chiavi univoche. Per ottenere le seguenti chiavi API, vai a **Sviluppatori** > **API** > **Chiavi** in **Bolt Dashboard Merchant**.

- Chiave API: Una chiave privata utilizzata dal back end per interagire con [!DNL Bolt] API.
- Chiave pubblicabile: Chiave utilizzata dal front-end per interagire con [!DNL Bolt] API.

Consulta la sezione [[!DNL Bolt] dettagli dell&#39;ambiente](https://help.bolt.com/developers/references/environment-details/#about-keys)Pagina {target=&quot;_blank&quot;} per informazioni sulle chiavi API e pubblicabili per [!DNL Express Checkout] estensione.

>[!CAUTION]
>
> Devi creare chiavi API per gli ambienti sandbox e di produzione.

## Configurare i provider di pagamento

Per collegare il provider di servizi di pagamento segui i passaggi descritti nel [configurazione del processore](https://help.bolt.com/integrations/adobe-express-checkout/set-up/)Sviluppatore {target=&quot;_blank&quot;} [!DNL Bolt] pagina.

## Abilita estensione

1. Sulla _Amministratore_ barra laterale, passare a **Negozi** > **Configurazione** > **Pagamento** per accedere alla pagina di configurazione dell’amministratore di checkout .

   ![Pagamento espresso](assets/admin-view.png)

1. In [!DNL Express Checkout] visualizzazione, set **Abilita** a `Yes`.
1. Selezionare il metodo (Sandbox o Production) da utilizzare.

   - Sandbox a scopo di test e sviluppo
   - Produzione per elaborare le transazioni con il processore di pagamento live

1. Convalida le credenziali dopo aver fornito le tue API e chiavi Pubblicabili univoche.

>[!CAUTION]
>
> È necessario fornire API e chiavi pubblicabili univoche prima di abilitare l’estensione. In caso contrario, i clienti visualizzeranno un modulo di pagamento e non saranno in grado di effettuare un ordine.

## Configurazione dell’amministratore completa

1. Sulla _Amministratore_ barra laterale, passare a **Negozi** > **Configurazione** > **Pagamento** per accedere alla pagina di configurazione generale dell’amministratore del checkout.
1. In _Impostazioni del servizio_ fornisci tutti i dettagli necessari per abilitare l’estensione .
1. Imposta _Azione di pagamento_ come:

   - Autorizza: Non acquisire la transazione in modo automatico al momento dell&#39;autorizzazione.
   - Autorizzazione e acquisizione: Cattura automaticamente la transazione su autorizzazione.

Per ulteriori informazioni sulle opzioni di pagamento standard di Adobe Commerce, consulta la sezione [pagamento](https://docs.magento.com/user-guide/configuration/sales/checkout.html) argomento.

## Abilita il pagamento in diretta express

Per abilitare [!DNL Express Checkout] per l&#39;estensione Adobe Commerce:

1. Fai clic su **Salva configurazione**.
1. Passa a **[!UICONTROL System]** > **[!UICONTROL Cache Management]** e fai clic su **[!UICONTROL Flush Cache]** per aggiornare tutte le cache non valide.

## Assistenza

Il processo di onboarding è progettato per guidarti attraverso i passaggi necessari per la configurazione e l&#39;abilitazione del [!DNL Express Checkout] funzionalità. Contatto [!DNL Adobe Commerce] team di progettazione attraverso lo Slack assegnato [Canale dei programmi Adobe Beta](http://adobe-beta-programs.slack.com/) per qualsiasi assistenza.

Fai riferimento a [verificare e convalidare](../express-checkout/testing.md) per ulteriori informazioni.
