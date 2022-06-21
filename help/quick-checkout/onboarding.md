---
title: '"A bordo [!DNL Quick Checkout] per estensione Adobe Commerce"'
description: '"Scopri come [!DNL Quick Checkout] potrebbe essere utile per la tua istanza Adobe Commerce e per come effettuare l’onboarding e la configurazione dell’estensione."'
exl-id: 8caf746c-e31b-4331-8b0d-ea0f1e545bdd
source-git-commit: a62c38adeb41812e91089716eb36c375b09595f4
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# [!DNL Quick Checkout] onboarding

Per iniziare a utilizzare [!DNL Quick Checkout] per l’estensione Adobe Commerce devi completare alcuni passaggi onboarding per collegare la tua istanza alla nostra funzionalità di pagamento.

1. [Ottieni estensione](#get-extension).
1. [Crea un account commerciale di produzione o sandbox con [!DNL Bolt]](#create-account-with-bolt). Fornisci tutte le informazioni necessarie per verificare la tua identità.
1. [Fornisci l&#39;univoco [!DNL API Key] e [!DNL Publishable Key] generato in [!DNL Bolt]](#obtain-api-credentials).
1. [Imposta un provider di pagamento nel [!DNL Bolt] account](#configure-payment-providers).
1. [Imposta il menu a discesa Abilita su Sì](#enable-extension) per attivare l&#39;estensione.
1. [Definire le impostazioni del servizio](#complete-admin-configuration) per configurare [!DNL Quick Checkout] estensione.
1. [Fai clic sul pulsante Salva configurazione](#enable-live-quick-checkout) per abilitare l&#39;estensione.

>[!NOTE]
>
> Se non si configura il [!DNL Bolt] account che non è possibile impostare sandbox o ambienti di produzione.

## Prerequisiti

Per utilizzare il [!DNL Quick Checkout], è necessario disporre delle seguenti opzioni [!DNL Bolt]:

- Provider di pagamenti supportati
- Conto del commerciante e della produzione in [!DNL Bolt]
- API e [!DNL Publishable key] generato in [!DNL Bolt]

Fai riferimento a [prerequisiti](../quick-checkout/prerequisites.md) per ulteriori informazioni.

Vedi [Credenziali API](#obtain-api-credentials) per scoprire come creare o accedere al tuo [!DNL API keys] per la tua istanza.

## Ottieni estensione

Consulta la sezione [installare](../quick-checkout/install.md) per informazioni dettagliate su come ottenere l&#39;estensione.

## Crea account con [!DNL Bolt]

Prima di configurare la [!DNL Quick Checkout] nell’amministratore di Adobe Commerce è necessario creare un [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} e [produzione](https://merchant.bolt.com/register){target=&quot;_blank&quot;} account commerciali in [!DNL Bolt]. Fornisci tutti i dettagli richiesti per creare un account in [!DNL Bolt].

Fai riferimento a [verificare e convalidare](../quick-checkout/testing.md) per ulteriori informazioni.

## Ottenere le credenziali API

Per utilizzare [!DNL Quick Checkout] richiede [!DNL Bolt] chiavi univoche. Ottieni quanto segue [!DNL API keys] passando a **Sviluppatori** > **API** > **Chiavi** in **Bolt Dashboard Merchant**.

- [!DNL API key]: Una chiave privata utilizzata dal back end per interagire con [!DNL Bolt] API.
- [!DNL Publishable key]: Chiave utilizzata dal front-end per interagire con [!DNL Bolt] API.

Consulta la sezione [[!DNL Bolt] dettagli dell&#39;ambiente](https://help.bolt.com/developers/references/environment-details/#about-keys)pagina {target=&quot;_blank&quot;} per informazioni su API e [!DNL Publishable keys] per [!DNL Quick Checkout] estensione.

>[!CAUTION]
>
> Devi creare [!DNL API keys] sia per gli ambienti sandbox che di produzione.

## Configurare i provider di pagamento

Per collegare il provider di servizi di pagamento segui i passaggi descritti nel [configurazione del processore](https://help.bolt.com/integrations/adobe-express-checkout/set-up/)Sviluppatore {target=&quot;_blank&quot;} [!DNL Bolt] pagina.

## Abilita estensione

1. Sulla _Amministratore_ barra laterale, vai a **Negozi** > _Impostazioni_ > **Configurazione**.
1. Nel pannello a sinistra, espandi **Vendite** e seleziona **Pagamento**.

   ![Pagamento rapido](assets/admin-view.png)

1. In [!DNL Quick Checkout] visualizzazione, set **Abilita** a `Yes`.
1. Selezionare il metodo (Sandbox o Production) da utilizzare.

   - Sandbox a scopo di test e sviluppo
   - Produzione per elaborare le transazioni con il processore di pagamento live

1. Convalida le credenziali dopo aver fornito l’API univoca e [!DNL Publishable keys].

>[!CAUTION]
>
> Devi fornire un’API univoca e [!DNL Publishable keys] prima di abilitare l’estensione, in caso contrario i clienti visualizzeranno un modulo di pagamento e non saranno in grado di effettuare un ordine.

## Configurazione amministratore completa

1. Sulla _Amministratore_ barra laterale, passare a **Negozi** > **Configurazione** > **Pagamento** per accedere alla pagina di configurazione generale dell’amministratore del checkout.
1. In _Impostazioni del servizio_ fornisci tutti i dettagli necessari per abilitare l’estensione .
1. Imposta _Azione di pagamento_ in una delle due opzioni:

   - `Authorize`: Non acquisire la transazione in modo automatico al momento dell&#39;autorizzazione.
   - `Authorize and Capture`: Cattura automaticamente la transazione su autorizzazione.

Per ulteriori informazioni sulle opzioni di pagamento standard di Adobe Commerce, consulta la sezione [pagamento](https://docs.magento.com/user-guide/configuration/sales/checkout.html) argomento.

## Abilita estrazione rapida in tempo reale

Per abilitare [!DNL Quick Checkout] per l&#39;estensione Adobe Commerce:

1. Controlla che la [!UICONTROL Enable] è impostato su **Sì** per attivare l&#39;estensione.
1. Fai clic su **Salva configurazione**.

## Assistenza

Il processo di onboarding è progettato per guidarti attraverso i passaggi necessari per la configurazione e l&#39;abilitazione del [!DNL Express Checkout] funzionalità. Contatta il team di progettazione Adobe Commerce tramite lo Slack assegnato [Canale dei programmi Adobe Beta](http://adobe-beta-programs.slack.com/) canale di assistenza.

Consulta la sezione [verificare e convalidare](../quick-checkout/testing.md) per ulteriori informazioni.
