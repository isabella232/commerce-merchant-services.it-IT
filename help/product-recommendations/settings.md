---
title: Impostazioni
description: Scopri come modificare l’origine del [!DNL Product Recommendations] e come abilitare i consigli visivi.
exl-id: 8c074e11-e0cb-4d55-b646-30279c79bbc2
source-git-commit: 75ff893bf5867ededa49807835676ddf9b19adc9
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Impostazioni

Quando [configurare uno spazio dati SaaS](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) per Recommendations, lo spazio dati SaaS raccoglie dati di catalogo e dati comportamentali di vetrina. [Adobe Sensei](https://www.adobe.com/sensei.html) analizza i dati e calcola le associazioni di prodotto utilizzate per fornire Recommendations di prodotto.

Gli ambienti non di produzione per il test o la gestione temporanea di solito non dispongono della quantità o della qualità dei dati comportamentali della vetrina per fornire consigli di prodotto realistici. Il comportamento effettivo degli acquirenti su larga scala può essere acquisito solo in un ambiente di produzione. Per risolvere questo problema, Adobe Commerce consente di utilizzare i consigli di prodotto dell’ambiente di produzione con altri spazi di dati SaaS non di produzione. L’utilizzo di dati vetrina reali in un ambiente non di produzione consente di visualizzare in anteprima i consigli visualizzati dagli acquirenti e di sperimentarli con diversi tipi di consigli e posizioni di posizionamento. Gli acquirenti possono visualizzare in anteprima i Recommendations provenienti da uno spazio dati SaaS diverso, ma non fare clic su di essi.

Gli ordini di gestione temporanea vengono registrati utilizzando la gestione temporanea `environmentId`. Non influisce sui dati di produzione. I dati di produzione vengono recuperati utilizzando `alternateEnvironmentId`.

>[!NOTE]
>
>Quando si utilizza Product Recommendations tramite REST, il `alternateEnvironmentId` Il parametro può essere utilizzato per specificare altri spazi di dati. Quando si utilizza Product Recommendations tramite GraphQL, questo parametro non è disponibile.

## Scegli l’origine dei consigli

Per modificare l’origine dei dati dei consigli di prodotto, scegli lo spazio dati SaaS con i dati comportamentali che desideri utilizzare. Prima di iniziare, assicurati che:

- La raccolta dati Storefront deve essere [configurato e abilitato](install-configure.md) per l&#39;ambiente di produzione e [verificato](verify.md) che i dati comportamentali vengono inviati ad Adobe Commerce.
- Il catalogo dell’ambiente non di produzione deve essere essenzialmente lo stesso del catalogo di produzione. L’utilizzo di cataloghi simili garantisce che le unità di consigli sui prodotti restituite rispecchino fedelmente quelle in produzione.

1. Accedi all’amministratore dell’ambiente Adobe Commerce non di produzione.

1. Il giorno _Amministratore_ barra laterale, vai a **Marketing** > _Promozioni_ > **Recommendations del prodotto**.

1. Clic **Impostazioni**.

   ![impostazioni per consigli di prodotto](assets/settings.png)
   _Impostazioni_

1. In _Origine Recommendations_ , abilita **Recuperare i consigli da un diverso spazio di dati SaaS** opzione. Il _Origine Recommendations_ viene visualizzata solo in un ambiente non di produzione.

   Un elenco di _Spazi dati SaaS disponibili_ viene visualizzato.

   ![impostazioni per consigli di prodotto](assets/settings-select-saas.png)
   _Impostazioni_

1. Selezionare lo spazio dati SaaS contenente i dati dell&#39;acquirente che si desidera utilizzare.

1. Clic **Salva modifiche**.

   Adobe Commerce ora recupera i consigli dallo spazio dati selezionato.

   >[!NOTE]
   >
   > Anche se è possibile visualizzare i consigli recuperati da un altro spazio dati SaaS nella vetrina non di produzione, non è possibile fare clic sui consigli.

### Configurare un nuovo spazio dati SaaS

1. Nella sezione Origine di Recommendations, fai clic su **Modifica configurazione**.

1. Segui le istruzioni per configurare una nuova [[!DNL Commerce] servizio](/help/landing/saas.md).

## Abilita consigli visivi

Se il [Visual Product Recommendations](install-configure.md) è installato, è necessario abilitare Visual Recommendations per utilizzare il [Somiglianza visiva](type.md#visualsim) tipo di consiglio.

In _Visual Recommendations_ sezione, set **Abilita Visual Recommendations** alla posizione attiva.
