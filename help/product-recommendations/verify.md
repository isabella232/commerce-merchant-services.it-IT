---
title: Verifica raccolta eventi
description: Scopri come verificare che i dati comportamentali vengano inviati ad Adobe Commerce.
exl-id: c8c34db4-9d87-4012-b8f0-e9b1da214305
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Verifica raccolta eventi

Dopo [installare e configurare](install-configure.md) la `magento/product-recommendations` modulo , puoi verificare che i dati comportamentali vengano inviati ad Adobe Commerce. Puoi utilizzare gli strumenti per sviluppatori disponibili in Chrome o installare l’estensione Snowplow Chrome. Se hai bisogno di ulteriore aiuto, consulta [Risolvere i problemi [!DNL Product Recommendations] modulo](https://support.magento.com/hc/en-us/articles/360042224851) nella Knowledge Base del supporto.

## Verificare con gli strumenti per sviluppatori in Chrome

Per garantire che il file JS dell&#39;agente di raccolta eventi sia in fase di caricamento su tutte le pagine del sito:

1. In Chrome, scegli **Personalizzare e controllare Google Chrome** quindi seleziona **Altri strumenti** > **Strumenti per gli sviluppatori**.
1. Scegli la **Rete** quindi seleziona la **JS** digitare.
1. Filtro per `ds.`
1. Ricarica la pagina.
1. Dovresti vedere `ds.js` o `ds.min.js` in **Nome** colonna.

![Raccoglitore eventi JS](assets/filter-ds.png)
_Raccoglitore eventi JS_

Per garantire che gli eventi vengano attivati sulle pagine del sito (home page, product, checkout e così via):

1. Assicurati di disabilitare gli ad blocker sul tuo browser e di accettare i cookie sul sito.
1. In Chrome, scegli **Personalizzare e controllare Google Chrome** (i tre punti verticali nell&#39;angolo in alto a destra del browser), quindi seleziona **Altri strumenti** > **Strumenti per gli sviluppatori**.
1. Scegli la **Rete** scheda e filtro per `tp2`.
1. Ricarica la pagina.
1. Dovresti visualizzare le chiamate in `tp2` in **Nome** colonna.

![Eventi di attivazione](assets/filter-tp2.png)
_Verifica che gli eventi siano attivati_

## Verifica tramite estensione Snowplow Chrome

Installa il [Estensione Snowplow Analytics Debugger per Chrome](https://chrome.google.com/webstore/detail/snowplow-analytics-debugg/jbnlcgeengmijcghameodeaenefieedm). Questa estensione visualizza gli eventi raccolti e inviati ad Adobe Commerce.

1. Assicurati di disabilitare gli ad blocker sul tuo browser e di accettare i cookie sul sito.

1. In Chrome, scegli **Personalizzare e controllare Google Chrome** (i tre punti verticali nell&#39;angolo in alto a destra del browser), quindi seleziona **Altri strumenti** > **Strumenti per gli sviluppatori**.

1. Scegli la **Debugger di Analytics Snowplow** scheda .

1. Sotto la **Evento** colonna, seleziona **Evento strutturato**.

1. Scorri verso il basso fino a visualizzare **Dati contestuali _n_**. Cerca l&#39;istanza di vetrina nel **Schema**.

1. Verifica che [ID spazio dati SaaS](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) è impostato correttamente.

![Filtro Snowplow](assets/snowplow-filter.png)
_Filtro per arcobaleno_

>[!NOTE]
>
> Un valore di `Data validity : NOT FOUND` nel debugger indica uno schema interno. Il plug-in Snowplow Chrome non può convalidare gli eventi con uno schema interno. Questo non ha alcun impatto sulla funzionalità effettiva.

## Verifica che gli eventi si attivino correttamente

Per verificare che gli eventi utilizzati per le metriche si attivino correttamente, cerca il `impression-render`, `view`e `rec-click` eventi in Snowplow Analytics Debugger. Consulta la sezione [elenco completo degli eventi](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/events.html).

>[!NOTE]
>
> Se [Modalità di restrizione dei cookie](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) è abilitato e Adobe Commerce non raccoglie dati comportamentali finché l’acquirente non acconsente. Se la modalità di restrizione dei cookie è disabilitata, i dati comportamentali vengono raccolti per impostazione predefinita.
