---
title: '"[!DNL Payment Services] Note sulla versione"'
description: Consulta le note sulla versione per informazioni su tutti [!DNL Payment Services] versioni.
exl-id: 104aa2c7-7735-4ac2-8ed1-a03cd9911273
source-git-commit: 6fc2db2ff842244af6a3c52b575b26233540931b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Note sulla versione

Queste note sulla versione descrivono la versione iniziale di [!DNL Payment Services] e comprendono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Problema risolto](../assets/fix.svg) Correzioni e miglioramenti
![Problema noto](../assets/bug.svg) Problemi noti

Vedi [Versioni future](https://devdocs.magento.com/release/) per informazioni sulle pianificazioni e sul supporto delle versioni.

Vedi [Disponibilità](https://devdocs.magento.com/release/availability.html) per informazioni sulla compatibilità del prodotto, consulta la documentazione per gli sviluppatori .

## v1.1.0

![Nuovo](../assets/new.svg)<!-- Issue PAY-2127 --> Versione generale di disponibilità—[!DNL Payment Services] è ora [compatibile con [!DNL Adobe Commerce] e [!DNL Magento Open Source] versioni da 2.4.0 a 2.4.4](https://devdocs.magento.com/release/availability.html#compatibility).

![Nuovo](../assets/new.svg)<!-- Issue PAY-2682 --> La [!DNL Payment Services] estensione per [!DNL Adobe Commerce] e [!DNL Magento Open Source] è ora disponibile per i commercianti canadesi. I commercianti possono visualizzare la configurazione dei pagamenti in [Francese](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.md#accepted-credit-cards-and-currencies) o [Inglese](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.md#accepted-credit-cards-and-currencies).

![Nuovo](../assets/new.svg)<!-- Issue PAY-2681 --> [!DNL Payment Services] supporta [Dollaro canadese (CAD)](overview.md#accepted-credit-cards-and-currencies) per le carte di credito e le transazioni PayPal.

![Nuovo](../assets/new.svg)<!-- Issue PAY-2680 --> I commercianti possono [a bordo [!DNL Payment Services]](onboard.md) estensione nelle lingue inglese o francese.

![Nuovo](../assets/new.svg)<!-- Issue PAY-2678 --> Gli esercenti possono ora visualizzare i rapporti finanziari, sia [Stato del pagamento dell&#39;ordine](order-payment-status.md) e [Rapporti sui pagamenti](payouts.md), in dollari canadesi (CAD).

![Problema risolto](../assets/fix.svg)<!-- Issue PAY-2710 --> [!DNL Payment Services] è ora compatibile con [PHP 8.1](https://www.php.net/releases/8.1/en.php).

![Problema risolto](../assets/fix.svg)<!-- Issue PAY-3017 --> È stato migliorato l’avviso in modalità sandbox per visualizzare avvisi corretti con più store.

![Problema risolto](../assets/fix.svg)<!-- Issue PAY-2742 --> È ora possibile abilitare e disabilitare i metodi di pagamento disponibili, ad esempio Venmo, a livello di visualizzazione store. In precedenza era possibile configurare i metodi di pagamento solo per sito web.

![Problema risolto](../assets/fix.svg)<!-- Issue PAY-2277 --> Ora puoi selezionare [abilita o disabilita singoli pulsanti smart PayPal](settings.md#paypal-smart-buttons).

![Problema risolto](../assets/fix.svg)<!-- Issue PAY-2561 --> I prodotti rimossi in precedenza non vengono visualizzati nel carrello della _Ordine di revisione_ pagina.

![Problema noto](../assets/bug.svg)<!-- Issue PAY-2842 --> Verifica transazioni con carta di credito [potrebbe non riuscire con PayPal](https://support.magento.com/hc/en-us/articles/5201041963917) durante l’elaborazione dei pagamenti in un ambiente sandbox.

## v1.0.0

![Nuovo](../assets/new.svg)<!-- Issue PAY-2127 --> Versione generale di disponibilità—[[!DNL Payment Services]](https://marketplace.magento.com/magento-payment-services.html) è ora compatibile con [!DNL Adobe Commerce] e [!DNL Magento Open Source] versioni da 2.4.0 a 2.4.3-p1.

![Nuovo](../assets/new.svg)<!-- Issue PAY-124 --> La [!DNL Payment Services] estensione per [!DNL Adobe Commerce] e [!DNL Magento Open Source] può essere installato per [[!DNL Adobe Commerce] sull&#39;infrastruttura cloud](install.md#adobe-commerce-on-cloud-infrastructure) o [Presso i locali](install.md#on-premises) istanze. Questi metodi richiedono l’utilizzo di un’interfaccia della riga di comando.

![Nuovo](../assets/new.svg)<!-- Issue PAY-1986 --> [!DNL Payment Services] supporta un [account sandbox](sandbox.md) che consente ai commercianti di valutare l&#39;estensione in modalità di test.

![Nuovo](../assets/new.svg)<!-- Issue PAY-666 --> I commercianti possono [configurare i servizi di pagamento](settings.md) estensione con comportamenti di pagamento di base, ad esempio l&#39;utilizzo [`Authorize and Capture`](production.md#set-payment-services-as-payment-method) passaggio da un ambiente sandbox all’altro.

![Nuovo](../assets/new.svg)<!-- Issue PAY-780 --> I tuoi clienti possono effettuare il check-out con [!DNL Payment Services] o tramite [creazione manuale degli ordini](create-order.md).

![Nuovo](../assets/new.svg)<!-- Issue PAY-1856 --> Rapporti completi, tramite [Stato del pagamento dell&#39;ordine](order-payment-status.md) e [Rapporti sui pagamenti](payouts.md), sono disponibili per [!DNL Payment Services] per fornirti una visione chiara degli ordini del tuo negozio e dei relativi pagamenti.

![Nuovo](../assets/new.svg)<!-- Issue PAY-311 --> [!DNL Payment Services] supporta prezzi flessibili su più livelli, basati sul volume totale di lavorazione, adattati a qualsiasi commerciante.

![Nuovo](../assets/new.svg)<!-- Issue PAY-1443 --> Puoi facilmente [personalizzare l&#39;aspetto](payments-options.md) dei pulsanti avanzati PayPal e dei campi della carta di credito per l&#39;estensione Servizi di pagamento.

![Problema noto](../assets/bug.svg)<!-- Issue PAY-2473 --> Utilizzo [chiavi Composer errate](https://support.magento.com/hc/en-us/articles/4406603542541) durante l&#39;installazione dell&#39;estensione impedisce all&#39;utente di [autenticazione](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) con la `MAGEID`.

![Problema noto](../assets/bug.svg)<!-- Issue PAY-2474 --> [!DNL Payment Services] rapporti [potrebbero non sincronizzarsi immediatamente](https://support.magento.com/hc/en-us/articles/4406114741517).

![Problema noto](../assets/bug.svg)<!-- Issue PAY-2475 --> Le [Conto sandbox PayPal](https://support.magento.com/hc/en-us/articles/4406954952461) per [!DNL Payment Services] non è possibile verificare se l’account è stato creato durante l’onboarding.
