---
title: '[!DNL Quick Checkout] Note sulla versione'
description: Consulta le note sulla versione per informazioni su tutti [!DNL Quick Checkout] versioni.
exl-id: 511be2fc-d24d-4323-a47a-d376e38a5c47
source-git-commit: 1f2305df7566cd77a6be161cc9d1265c0291171c
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 0%

---

# Note sulla versione

Queste note sulla versione descrivono la versione iniziale di [!DNL Quick Checkout] e comprendono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Problema risolto](../assets/fix.svg) Correzioni e miglioramenti
![Problema noto](../assets/bug.svg) Problemi noti

Vedi [Versioni future](https://devdocs.magento.com/release/) per informazioni sulle pianificazioni e sul supporto delle versioni.

Vedi [Disponibilità](https://devdocs.magento.com/release/availability.html) per informazioni sulla compatibilità del prodotto, consulta la documentazione per gli sviluppatori .

## Aggiornamenti del pannello Amministratore

Queste note sulla versione descrivono le modifiche e le correzioni apportate alle funzioni e che sono state rilasciate al di fuori delle regolari versioni delle funzioni per il pannello Amministratore.

+++Aggiornamenti del pannello di amministrazione

_30 novembre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-502 --> Ora, la [reporting](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html) tab ha un nuovo predefinito &quot;Ultimo anno&quot;.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-471 --> Miglioramenti dell’esperienza utente nella [!DNL Quick Checkout] Pannello Admin mostra ulteriori informazioni in [Descrizioni comandi](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html).

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-514 --> Miglioramenti dell’esperienza utente nella [!DNL Quick Checkout] Il pannello di amministrazione mostra i numeri degli ordini totali corretti, la coerenza dei colori e le legende corrette per tutti i grafici.

_2 novembre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-293 --> Ora, la [reporting](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html) nella scheda [!DNL Quick Checkout] Il pannello Amministratore mostra grafici e informazioni di reporting sulle statistiche dell’esperienza di pagamento del tuo negozio.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-422 --> La [_Panoramica_](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html#reports-overview) la sezione della sezione dell&#39;argomento Rapporti mostra informazioni dettagliate sulle prestazioni di pagamento del tuo negozio, tra cui il tempo medio di pagamento, i nuovi account creati durante l&#39;estrazione e l&#39;abbandono del pagamento.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-423 --> La [_Tendenze_](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html#reports-trends) la sezione della scheda Rapporti mostra le tendenze dell’esperienza di pagamento filtrate per tipo di account e i nuovi account creati durante l’estrazione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-439 --> La **Rapporti** display a schede [predefiniti filtro](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html#filter-data) che può essere utilizzato per mostrare intervalli di dati specifici.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-433 --> Ora è possibile visualizzare un _Nessun dato disponibile_ avviso per un grafico quando una richiesta non restituisce dati.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-473 --> Miglioramenti dell’esperienza utente [!DNL Quick Checkout] Il pannello di amministrazione include la possibilità di abilitare un [tracciamento dei checkout](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/settings-quick-checkout.html#service-settings) che consente ad Adobe Commerce di condividere le informazioni di reporting con Bolt.

_5 ottobre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-379 --> Ora, quando un nuovo commerciante accede al [!DNL Quick Checkout] Pannello di amministrazione per la prima volta [tour con funzioni guidate da Gainsight](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html) appare.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-377 --> La **Rapporti** nella scheda [!DNL Quick Checkout] Il pannello Amministratore mostra grafici e analisi dei rapporti.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-377 --> La **Rapporti** nella scheda [!DNL Quick Checkout] Il pannello Amministratore mostra l’intervallo di date e i predefiniti filtro per i grafici e le analisi di reporting.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-369 --> Ora, la [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) visualizza la versione dell’app nel piè di pagina.

+++

## v1.4.0

_30 novembre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-513 --> Ora, quando un cliente Adobe Commerce è connesso al negozio durante il processo di pagamento e dispone di un account Bolt, viene visualizzata un’opzione per accedere all’account Bolt del cliente.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-512 --> Una nuova configurazione rileva automaticamente se è possibile effettuare l&#39;accesso a Bolt anche per gli acquirenti registrati.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-480 --> Una nuova configurazione nel [!DNL Quick Checkout] Il pannello di amministrazione consente di modificare il flusso di navigazione predefinito nel **Spedizione** una volta che un cliente Bolt accede. Per impostazione predefinita, è configurato per **Pagamenti** pagina.

## v1.3.0

_2 novembre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-293 --> Ora, [!DNL Quick Checkout] include la possibilità di abilitare un [tracciamento dei checkout](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/settings-quick-checkout.html#service-settings) che consente ad Adobe Commerce di condividere le informazioni di reporting con Bolt.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-461 --> Ora è possibile visualizzare un messaggio di avviso nel [!DNL Quick Checkout] Pannello di amministrazione se [tracciamento dei checkout](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html) configurazione disabilitata.

## v1.2.0

_8 settembre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-341 --> Versione generale di disponibilità—[[!DNL Quick Checkout]](https://marketplace.magento.com/magento-quick-checkout.html) è ora compatibile con Adobe Commerce versione 2.4.5.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-328 --> [!DNL Quick Checkout] per Adobe Commerce e Magenti Open Source fornisce un [Vista del pannello Amministratore](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) con tutte le informazioni necessarie per configurare e utilizzare l&#39;estensione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-364 --> Utente amministratore [può impostare ruoli utente e autorizzazioni](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/user-roles-setup.html) per consentire ad altri utenti di visualizzare il [!DNL Quick Checkout] Pannello Amministratore.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-377 --> [!DNL Quick Checkout] Il pannello di amministrazione ora contiene un’intestazione di pagina che include sezioni specifiche come **Panoramica**, **Rapporti** e **Impostazioni**.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-379 --> Quando un nuovo commerciante accede al [!DNL Quick Checkout] Per la prima volta viene visualizzato un widget di benvenuto che offre una presentazione dettagliata delle funzioni.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-378 --> [!DNL Quick Checkout] [Vista del pannello Amministratore](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) incorpora un **Configurazione** passaggio che viene visualizzato quando l’API e le chiavi pubblicabili non sono fornite nel [Impostazioni](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) visualizza.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-380 --> [!DNL Quick Checkout] [Vista del pannello Amministratore](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) incorpora un **Risorse** sezione che cambia a seconda della fase di onboarding.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-381 --> [!DNL Quick Checkout] [Vista del pannello Amministratore](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) include **Guida e supporto** sezione .

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-369 --> La [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) ora visualizza la versione dell&#39;estensione nel piè di pagina.

## v1.1.0

_12 agosto 2022_

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-375 --> Miglioramenti dell’esperienza utente in [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) ora includi solo i parametri visibili e convalidati quando l’estensione è abilitata.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-349 --> Miglioramenti della compatibilità per gli indirizzi di spedizione esistenti con il wallet Bolt.

## v1.0.0

_9 agosto 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-341 --> Versione generale di disponibilità—[[!DNL Quick Checkout]](https://marketplace.magento.com/magento-quick-checkout.html) è ora compatibile con le versioni da 2.4.1 a 2.4.4 di Adobe Commerce.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-340 --> La [!DNL Quick Checkout] per Adobe Commerce può essere installato sia per Adobe Commerce [sull&#39;infrastruttura cloud](install.md#adobe-commerce-on-cloud-infrastructure) o [locale](install.md#on-premises) istanze. Questi metodi richiedono l&#39;utilizzo di un&#39;interfaccia a riga di comando.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> La [!DNL Quick Checkout] per Adobe Commerce porta una vetrina ottimizzata che consente un [esperienza di pagamento con un solo clic](overview.md) senza campi di riempimento necessari per i consumatori.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> La [!DNL Quick Checkout] per Adobe Commerce riconosce automaticamente ogni acquirente nella propria rete per [acquisti con un clic](checkout-flow.md) direttamente sul sito.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> La [!DNL Quick Checkout] per Adobe Commerce consente a un acquirente di essere simultaneamente [connesso sia alle reti Adobe Commerce che Bolt](checkout-flow.md/#quick-checkout-use-cases) per fornire `one-click checkout` esperienza.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-218 --> [!DNL Quick Checkout] per Adobe Commerce supporta un [account sandbox](testing.md#testing-in-sandbox) che consente ai commercianti di valutare l&#39;estensione in modalità di test.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-780 --> Gli acquirenti possono effettuare il check-out tramite [[!DNL Quick Checkout]](checkout-page.md) o tramite [creazione manuale degli ordini](create-order-admin.md).

![Nuovo](../assets/new.svg)<!-- Issue BOLT-666 --> I merchants possono configurare le [!DNL Quick Checkout] con azioni di pagamento di base, quali [`Authorize and Capture` o `Authorize` ](onboarding.md#complete-admin-configuration)oppure passare da un ambiente sandbox all’altro.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-288 --> Personalizzato [ciclo di vita della sessione utente](user-session-lifetime.md) per [!DNL Quick Checkout] per Adobe Commerce.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-375 --> Miglioramenti dell’esperienza utente in [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) consente di salvare la configurazione quando vengono forniti tutti i parametri richiesti.

![Problema noto](../assets/bug.svg)<!-- Issue BOLT-342 --> Comune [risoluzione](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/quick-checkout-issues.html) problemi durante l&#39;installazione di [!DNL Quick Checkout].
