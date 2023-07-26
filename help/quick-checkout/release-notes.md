---
title: '''[!DNL Quick Checkout] Note sulla versione'
description: Consulta le note sulla versione per informazioni su tutte [!DNL Quick Checkout] versioni.
exl-id: 511be2fc-d24d-4323-a47a-d376e38a5c47
feature: Release Notes, Services, Checkout
source-git-commit: 0c8d9498ea7a30a99f834694ef8a865ad24466ab
workflow-type: tm+mt
source-wordcount: '1422'
ht-degree: 0%

---

# Note sulla versione

Queste note sulla versione descrivono la versione iniziale di [!DNL Quick Checkout] e includono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Problema risolto](../assets/fix.svg) Correzioni e miglioramenti
![Problema noto](../assets/bug.svg) Problemi noti

Consulta [Prossime versioni](https://devdocs.magento.com/release/) per informazioni sulle pianificazioni delle versioni e sul supporto.

Consulta [Disponibilità](https://devdocs.magento.com/release/availability.html) nella documentazione per gli sviluppatori per informazioni sulla compatibilità dei prodotti.

## Aggiornamenti del pannello di amministrazione

Queste note sulla versione descrivono le modifiche e le correzioni apportate alle funzioni e che sono state rilasciate al di fuori delle normali versioni del pannello Amministratore.

+++Aggiornamenti del pannello di amministrazione

23 maggio 2023_

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-489 --> Ora, il **Nuovi account** componente in [!DNL Quick Checkout] La pagina di reporting include Spectrum [Icone flusso di lavoro](https://react-spectrum.adobe.com/react-spectrum/workflow-icons.html){target=_blank}.

_25 aprile 2023_

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-452 --> Il [!DNL Quick Checkout] **Presentazione** ora, quando ci si passa sopra con il mouse, viene visualizzato un cursore mano cliccabile.

_19 aprile 2023_

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-596 --> Il [!DNL Quick Checkout] La pagina Rapporti ora mostra correttamente il grafico Nuovi conti durante l’analisi delle date nel formato ISO 8601.

_14 dicembre 2022_

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-524 --> Il [!DNL Quick Checkout] Il pannello Amministratore ora mostra gli ordini totali corretti e le informazioni di reporting aggiornate.

_30 novembre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-502 --> Ora, il [reportistica](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html) ha un nuovo predefinito per &quot;Ultimo anno&quot;.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-471 --> Miglioramenti dell’esperienza utente in [!DNL Quick Checkout] Il pannello di amministrazione mostra ulteriori informazioni in [Descrizione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html).

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-514 --> Miglioramenti dell’esperienza utente in [!DNL Quick Checkout] Il pannello di amministrazione mostra i numeri degli ordini totali corretti, la coerenza dei colori e le legende corrette per tutti i grafici.

_2 novembre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-293 --> Ora, il [reportistica](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html) scheda in [!DNL Quick Checkout] Il pannello di amministrazione mostra i grafici e le informazioni di reporting delle statistiche sull’esperienza di pagamento del tuo negozio.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-422 --> Il [_Panoramica_](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html#reports-overview) Nella sezione dell&#39;argomento Rapporti vengono visualizzate informazioni dettagliate sulle prestazioni di estrazione del tuo negozio, inclusi il tempo medio di estrazione, i nuovi account creati durante l&#39;estrazione e l&#39;abbandono dell&#39;estrazione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-423 --> Il [_Tendenze_](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html#reports-trends) La sezione della scheda Rapporti mostra le tendenze dell’esperienza di estrazione filtrate per tipo di account e i nuovi account creati durante l’estrazione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-439 --> Il **Rapporti** visualizzazioni scheda [predefiniti per filtri](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html#filter-data) che possono essere utilizzate per mostrare intervalli di dati specifici.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-433 --> Ora puoi vedere un _Nessun dato disponibile_ avvertenza per un grafico quando una richiesta non restituisce dati.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-473 --> Miglioramenti dell’esperienza utente da [!DNL Quick Checkout] Il pannello di amministrazione include la possibilità di abilitare [tracciamento pagamento](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/settings-quick-checkout.html#service-settings) che consente ad Adobe Commerce di condividere le informazioni di reporting con Bolt.

_5 ottobre 2022_

![Nuovo](../assets/new.svg)<!-- Issue BOLT-379 --> Ora, quando un nuovo commerciante accede al [!DNL Quick Checkout] Pannello di amministrazione per la prima volta [tour di funzionalità con tecnologia Gainsight](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html) viene visualizzato.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-377 --> Il **Rapporti** scheda in [!DNL Quick Checkout] Il pannello Amministratore mostra i grafici e le analisi di reporting.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-377 --> Il **Rapporti** scheda in [!DNL Quick Checkout] Il pannello di amministrazione mostra l’intervallo di date e i predefiniti di filtro per i grafici e le analisi di reporting.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-369 --> Ora, il [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) visualizza la versione dell’app nel piè di pagina.

+++

## v1.8.0

_24 febbraio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg)<!-- Issue BOLT-520 --> Versione con disponibilità generale:[[!DNL Quick Checkout]](https://commercemarketplace.adobe.com/magento-quick-checkout.html) è ora preinstallato in Adobe Commerce Cloud versione 2.4.6 e successive.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-592 --> Miglioramenti nell’esperienza utente durante l’inserimento di un ordine in [Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/create-order-admin.html) utilizzo [Braintree](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/payments/stored-payment-methods.html) come metodo di pagamento. Questa funzionalità consente ai clienti di effettuare un ordine con Braintree come metodo di pagamento durante il pagamento quando [!DNL Quick Checkout] è abilitato.

## v1.7.0

_22 febbraio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Problema risolto](../assets/fix.svg)<!-- Issue AC-8002 --> Miglioramenti dell’esperienza utente durante il posizionamento di un ordine utilizzando una [Multishipping](https://experienceleague.adobe.com/docs/commerce-admin/config/sales/multishipping-settings.html) metodo. Questa funzionalità consente la visualizzazione dei metodi di pagamento durante il pagamento [!DNL Quick Checkout] è abilitato.

## v1.6.0

_9 febbraio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-567 --> Miglioramenti dell’esperienza utente quando [effettuazione di un ordine](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html) utilizzando [Consegna in-store](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/delivery/basic-methods/shipping-in-store-delivery.html) metodo con [!DNL Quick Checkout] disattivato.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-569 --> Miglioramenti nella funzionalità di logout che consente agli acquirenti di [disconnessione dalla rete bullone](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/user-session-lifetime.html).

## v1.5.0

_18 gennaio 2023_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg)<!-- Issue BOLT-522 --> È possibile abilitare/disabilitare una nuova configurazione per rilevare se [acquirenti](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/manage-checkout/checkout-options/checkout-adobe-commerce.html) può essere registrato automaticamente in Bullone.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-523 --> È possibile abilitare/disabilitare una nuova configurazione che consente ai commercianti di specificare se gli acquirenti possono accedere automaticamente a entrambe le reti o solo alla rete Bolt.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-542 --> Miglioramenti dell’esperienza utente quando [salvataggio di una carta o di un indirizzo in un account Bolt](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html) quando un acquirente fornisce e-mail.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-550 --> Miglioramenti all’esperienza utente in [accesso automatico](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#configure-service-settings) quando un utente Bolt fornisce un’e-mail.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-544 --> Miglioramenti della compatibilità per [URL di callback](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#check-shopper-valid-account) con [più siti](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/multi-sites/ms-overview.html) in Bullone.

## v1.4.0

_30 novembre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg)<!-- Issue BOLT-513 --> Ora, quando un cliente di Adobe Commerce viene registrato nel negozio durante il processo di pagamento e dispone di un account Bolt, viene visualizzata un’opzione per accedere all’account Bolt dell’acquirente.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-512 --> Una nuova configurazione rileva automaticamente se gli acquirenti connessi possono anche essere registrati in Bullone.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-480 --> Una nuova configurazione in [!DNL Quick Checkout] Il pannello di amministrazione consente di modificare il flusso di navigazione predefinito in **Spedizione** una volta che un cliente Bolt effettua l’accesso. Per impostazione predefinita, è configurato per **Pagamenti** pagina.

## v1.3.0

_2 novembre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg)<!-- Issue BOLT-293 --> Ora, [!DNL Quick Checkout] include la possibilità di abilitare [tracciamento pagamento](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/settings-quick-checkout.html#service-settings) che consente ad Adobe Commerce di condividere le informazioni di reporting con Bolt.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-461 --> Ora puoi visualizzare un messaggio di avviso nel tuo [!DNL Quick Checkout] Pannello di amministrazione se [tracciamento pagamento](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-reporting/reports.html) la configurazione è disabilitata.

## v1.2.0

_8 settembre 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg)<!-- Issue BOLT-341 --> Versione con disponibilità generale:[[!DNL Quick Checkout]](https://commercemarketplace.adobe.com/magento-quick-checkout.html) è ora compatibile con Adobe Commerce versione 2.4.5.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-328 --> [!DNL Quick Checkout] per Adobe Commerce e Magento Open Source fornisce un [Visualizzazione del pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) con tutte le informazioni necessarie per configurare e utilizzare l’estensione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-364 --> Un utente amministratore [può impostare ruoli utente e autorizzazioni](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/user-roles-setup.html) per consentire ad altri utenti di visualizzare [!DNL Quick Checkout] Pannello di amministrazione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-377 --> [!DNL Quick Checkout] Il pannello Amministratore ora contiene un’intestazione di pagina che include sezioni specifiche come **Panoramica**, **Rapporti**, e **Impostazioni**.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-379 --> Quando un nuovo commerciante accede al [!DNL Quick Checkout] Pannello di amministrazione per la prima volta viene visualizzato un widget di benvenuto con una presentazione delle funzioni.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-378 --> [!DNL Quick Checkout] [Visualizzazione del pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) incorpora un **Configurazione** passaggio che viene visualizzato quando l’API e le chiavi pubblicabili non sono fornite in [Impostazioni](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) visualizzazione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-380 --> [!DNL Quick Checkout] [Visualizzazione del pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) incorpora un **Risorse** che varia a seconda della fase di onboarding.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-381 --> [!DNL Quick Checkout] [Visualizzazione del pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/quick-checkout-admin-panel/admin-panel.html) include un **Guida e supporto** sezione.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-369 --> Il [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) ora visualizza la versione dell’estensione nel piè di pagina.

## v1.1.0

_12 agosto 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-375 --> Miglioramenti all’esperienza utente in [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) ora includi solo i parametri visibili e convalidati quando l&#39;estensione è abilitata.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-349 --> Miglioramenti di compatibilità per gli indirizzi di spedizione esistenti con il wallet Bolt.

## v1.0.0

_9 agosto 2022_

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg)<!-- Issue BOLT-341 --> Versione con disponibilità generale:[[!DNL Quick Checkout]](https://commercemarketplace.adobe.com/magento-quick-checkout.html) è ora compatibile con Adobe Commerce versioni da 2.4.1 a 2.4.4.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-340 --> Il [!DNL Quick Checkout] per Adobe Commerce può essere installato sia per Adobe Commerce [sull’infrastruttura cloud](install.md#adobe-commerce-on-cloud-infrastructure) o [on-premise](install.md#on-premises) istanze. Questi metodi richiedono l&#39;utilizzo di un&#39;interfaccia della riga di comando.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> Il [!DNL Quick Checkout] per Adobe Commerce offre una vetrina ottimizzata che consente di [esperienza di pagamento con un solo clic](overview.md) senza campi di riempimento necessari per i consumatori.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> Il [!DNL Quick Checkout] per Adobe Commerce riconosce automaticamente ogni acquirente nella propria rete per [acquisti con un solo clic](checkout-flow.md) direttamente sul sito.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> Il [!DNL Quick Checkout] per Adobe Commerce consente a un acquirente di essere contemporaneamente [ha effettuato l’accesso sia alle reti Adobe Commerce che Bolt](checkout-flow.md/#quick-checkout-use-cases) per offrire una migliore `one-click checkout` esperienza.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-218 --> [!DNL Quick Checkout] per Adobe Commerce supporta [account sandbox](testing.md#testing-in-sandbox) che consente agli esercenti di valutare l’estensione in modalità di test.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-780 --> Gli acquirenti possono effettuare il check-out tramite il [[!DNL Quick Checkout]](checkout-page.md) o tramite un [creazione manuale degli ordini](create-order-admin.md).

![Nuovo](../assets/new.svg)<!-- Issue BOLT-666 --> Gli esercenti possono configurare [!DNL Quick Checkout] con azioni di pagamento di base, come [`Authorize and Capture` o `Authorize`](onboarding.md#complete-admin-configuration), o il passaggio tra ambienti sandbox e di produzione.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-288 --> Personalizzato [durata della sessione utente](user-session-lifetime.md) per [!DNL Quick Checkout] per Adobe Commerce.

![Problema risolto](../assets/fix.svg)<!-- Issue BOLT-375 --> Miglioramenti all’esperienza utente in [[!DNL Quick Checkout] Pannello di amministrazione](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/getting-started/onboarding.html#enable-extension) consente di salvare la configurazione quando vengono forniti tutti i parametri richiesti.

![Problema noto](../assets/bug.svg)<!-- Issue BOLT-342 --> Comune [risoluzione dei problemi](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/quick-checkout-issues.html) problemi durante l&#39;installazione di [!DNL Quick Checkout].
