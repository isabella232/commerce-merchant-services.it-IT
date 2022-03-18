---
title: '"[!DNL Payment Services] Note sulla versione"'
description: Consulta le note sulla versione per informazioni su tutti [!DNL Payment Services] versioni.
exl-id: 104aa2c7-7735-4ac2-8ed1-a03cd9911273
source-git-commit: eb8fdba65b4b64730d0ad4fa6e0c9b64bdadc7df
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 1%

---

# Note sulla versione

Queste note sulla versione descrivono la versione iniziale di [!DNL Payment Services] e comprendono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Problema risolto](../assets/fix.svg) Correzioni e miglioramenti
![Problema noto](../assets/bug.svg) Problemi noti

## v1.0.0

![Nuovo](../assets/new.svg)<!-- Issue PAY-2127 --> Versione generale di disponibilità. [Servizi di pagamento](https://marketplace.magento.com/magento-payment-services.html) è ora compatibile con Adobe Commerce e con le versioni da 2.4.0 a 2.4.3-p1 di Magenti Open Source.

![Nuovo](../assets/new.svg)<!-- Issue PAY-124 --> La [!DNL Payment Services] l&#39;estensione per Adobe Commerce e Magenti Open Source può essere installata sia per [Adobe Commerce su infrastruttura cloud](install.md#magento-commerce-cloud) o [Presso i locali](install.md#on-premises) istanze. Questi metodi richiedono l’utilizzo di un’interfaccia della riga di comando.

![Nuovo](../assets/new.svg)<!-- Issue PAY-1986 --> [!DNL Payment Services] supporta un [account sandbox](onboard.md#enable-sandbox-testing) che consente ai commercianti di valutare l&#39;estensione in modalità di test.

![Nuovo](../assets/new.svg)<!-- Issue PAY-666 --> I commercianti possono [configurare i servizi di pagamento](configure-admin.md) estensione con comportamenti di pagamento di base (ad esempio acquisizione automatica e passaggio tra sandbox o ambienti di produzione).

![Nuovo](../assets/new.svg)<!-- Issue PAY-780 --> Gli acquirenti possono effettuare il check-out con [!DNL Payment Services] oppure puoi prendere l&#39;ordine al telefono e [creare un intero ordine](create-order.md) nell&#39;amministratore per loro.

![Nuovo](../assets/new.svg)<!-- Issue PAY-1856 --> [!DNL Payment Services] offri ai commercianti rapporti completi in modo da ottenere una visione chiara degli ordini e dei pagamenti dei tuoi store.

![Nuovo](../assets/new.svg)<!-- Issue PAY-311 --> [!DNL Payment Services] sostiene i prezzi a più livelli (basati su TPV) adattati a qualsiasi commerciante.

![Nuovo](../assets/new.svg)<!-- Issue PAY-1443 --> È possibile personalizzare l&#39;aspetto dei pulsanti PayPal e dei campi CC per [Servizi di pagamento](https://devdocs.magento.com/payment-services/customize-buttons-messaging.html) estensione.

![Problema noto](../assets/bug.svg)<!-- Issue PAY-2473 --> Utilizzo [chiavi compositore errate](https://support.magento.com/hc/en-us/articles/4406603542541) durante l&#39;installazione dell&#39;estensione impedisce all&#39;utente di [autenticare](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) con correzione `MAGEID`.

![Problema noto](../assets/bug.svg)<!-- Issue PAY-2474 --> [!DNL Payment Services] [rapporti](https://support.magento.com/hc/en-us/articles/4406114741517) per lo stato di pagamento di Pagamento e Ordine potrebbe non essere sincronizzato immediatamente.

![Problema noto](../assets/bug.svg)<!-- Issue PAY-2475 --> [Conto sandbox PayPal](https://support.magento.com/hc/en-us/articles/4406954952461) per [!DNL Payment Services] non può essere verificato.
