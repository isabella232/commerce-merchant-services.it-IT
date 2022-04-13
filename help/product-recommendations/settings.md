---
title: Impostazioni
description: Scopri come modificare l’origine del [!DNL Product Recommendations] e come abilitare i consigli visivi.
exl-id: 8c074e11-e0cb-4d55-b646-30279c79bbc2
source-git-commit: 6d0c7c749fe90c7c204afe47446f3483d8668b53
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Impostazioni

Quando [configurare uno spazio dati SaaS](https://docs.magento.com/user-guide/configuration/services/saas.html) per Recommendations, lo spazio dati SaaS raccoglie dati di catalogo e dati comportamentali di vetrina. [Adobe Sensei](https://www.adobe.com/sensei.html) analizza i dati e calcola le associazioni di prodotti utilizzate per distribuire Product Recommendations.

Gli ambienti non di produzione per il test o la gestione temporanea di solito non dispongono della quantità o della qualità dei dati comportamentali di vetrina per fornire consigli di prodotto realistici. Il comportamento effettivo dell&#39;acquirente su scala può essere catturato solo in un ambiente di produzione. Per risolvere questo problema, Adobe Commerce consente di utilizzare i consigli di prodotto dell’ambiente di produzione con altri spazi dati SaaS non di produzione. L’utilizzo dei dati effettivi della vetrina in un ambiente non di produzione consente di visualizzare in anteprima i consigli che gli acquirenti visualizzano e sperimentano con diversi tipi di consigli e posizioni di posizionamento. Recommendations proveniente da un diverso spazio dati SaaS può essere visualizzato in anteprima da acquirenti, ma non cliccato.

## Scegliere l’origine dei consigli

Per modificare l’origine dei dati dei consigli di prodotto, scegli lo spazio dati SaaS con i dati comportamentali che desideri utilizzare. Prima di iniziare, assicurati che:

- La raccolta dati di Storefront deve essere [configurato e abilitato](install-configure.md) per l&#39;ambiente di produzione e [verificato](verify.md) che i dati comportamentali vengono inviati ad Adobe Commerce.
- Il catalogo ambiente non di produzione deve essere essenzialmente lo stesso del catalogo di produzione. L’utilizzo di cataloghi simili assicura che le unità di raccomandazione del prodotto restituiscano una rappresentazione fedele di quelle in produzione.

1. Accedi all’amministratore del tuo ambiente Adobe Commerce non di produzione.

1. Sulla _Amministratore_ barra laterale, vai a **Marketing** > _Promozioni_ > **Recommendations di prodotto**.

1. Fai clic su **Impostazioni**.

   ![impostazioni dei consigli di prodotto](assets/settings.png)
   _Impostazioni_

1. In _Origine Recommendations_ abilitare **Recupera consigli da un diverso spazio dati SaaS** opzione . La _Origine Recommendations_ viene visualizzata solo in un ambiente non di produzione.

   Un elenco di _Spazi dati SaaS disponibili_ appare.

   ![impostazioni dei consigli di prodotto](assets/settings-select-saas.png)
   _Impostazioni_

1. Selezionare lo spazio dati SaaS con i dati dell’acquirente che si desidera utilizzare.

1. Fai clic su **Salva modifiche**.

   Adobe Commerce ora recupera i consigli dallo spazio dati selezionato.

   >[!NOTE]
   >
   > Sebbene sia possibile visualizzare i consigli recuperati da un altro spazio dati SaaS sulla vetrina non di produzione, non è possibile fare clic sui consigli.

### Configurare un nuovo spazio dati SaaS

1. Nella sezione Origine Recommendations, fai clic su **Modifica configurazione**.

1. Segui le istruzioni per configurare un nuovo [[!DNL Commerce] servizio](/help/landing/saas.md).

## Abilitare i consigli visivi

Se la [Recommendations di prodotto visivo](install-configure.md) Il modulo è installato, è necessario abilitare Visual Recommendations per utilizzare [Somiglianza visiva](type.md#visualsim) tipo di raccomandazione.

In _Recommendations visivo_ sezione, set **Abilita Visual Recommendations** alla posizione attiva.
