---
title: '"[!DNL Quick Checkout] Note sulla versione"'
description: Consulta le note sulla versione per informazioni su tutti [!DNL Quick Checkout] versioni.
source-git-commit: dc13c1e38c92341cfd3221a72e6568220b44690a
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 2%

---

# Note sulla versione

Queste note sulla versione descrivono la versione iniziale di [!DNL Quick Checkout] e comprendono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Problema risolto](../assets/fix.svg) Correzioni e miglioramenti
![Problema noto](../assets/bug.svg) Problemi noti

Vedi [Versioni future](https://devdocs.magento.com/release/) per informazioni sulle pianificazioni e sul supporto delle versioni.

Vedi [Disponibilità](https://devdocs.magento.com/release/availability.html) per informazioni sulla compatibilità del prodotto, consulta la documentazione per gli sviluppatori .

## v1.0.0

![Nuovo](../assets/new.svg)<!-- Issue BOLT-341 --> Versione generale di disponibilità—[[!DNL Quick Checkout]](https://marketplace.magento.com/magento-quick-checkout.html) è ora compatibile con le versioni da 2.4.1 a 2.4.4 di Adobe Commerce.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-340 --> La [!DNL Quick Checkout] per Adobe Commerce può essere installato sia per Adobe Commerce [sull&#39;infrastruttura cloud](install.md#adobe-commerce-on-cloud-infrastructure) o [locale](install.md#on-premises) istanze. Questi metodi richiedono l&#39;utilizzo di un&#39;interfaccia a riga di comando.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> La [!DNL Quick Checkout] per Adobe Commerce porta una vetrina ottimizzata che consente un [esperienza di pagamento con un solo clic](overview.md) senza campi di riempimento necessari per i consumatori.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-1 --> La [!DNL Quick Checkout] per Adobe Commerce riconosce automaticamente ogni acquirente nella propria rete per [acquisti con un clic](checkout-flow.md) direttamente sul sito.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-218 --> [!DNL Quick Checkout] per Adobe Commerce supporta un [account sandbox](testing.md#testing-in-sandbox) che consente ai commercianti di valutare l&#39;estensione in modalità di test.

![Nuovo](../assets/new.svg)<!-- Issue BOLT-780 --> Gli acquirenti possono effettuare il check-out tramite [[!DNL Quick Checkout]](checkout-page.md) o tramite [creazione manuale degli ordini](create-order-admin.md).

![Nuovo](../assets/new.svg)<!-- Issue BOLT-666 --> I merchants possono configurare le [!DNL Quick Checkout] con azioni di pagamento di base, quali [`Authorize and Capture` o `Authorize` ](onboarding.md#complete-admin-configuration)oppure passare da un ambiente sandbox all’altro.

![Problema noto](../assets/bug.svg)<!-- Issue BOLT-342 --> Utilizzo [chiavi Composer errate](https://support.magento.com/hc/en-us/articles/6909450342541) durante l&#39;installazione del [!DNL Quick Checkout] impedisce all&#39;utente di [autenticazione](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) con la `MAGEID`.
