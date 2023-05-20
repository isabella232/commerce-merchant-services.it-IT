---
title: Verifica raccolta eventi
description: Scopri come verificare che i dati comportamentali vengano inviati ad Adobe Commerce.
exl-id: c8c34db4-9d87-4012-b8f0-e9b1da214305
source-git-commit: d8be88f47f103c5d632540dae743ede398a9b7ad
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# Verifica raccolta eventi

Dopo di te [installare e configurare](install-configure.md) il `magento/product-recommendations` modulo, puoi verificare che i dati comportamentali vengano inviati ad Adobe Commerce. Puoi utilizzare gli strumenti per sviluppatori disponibili in Chrome o installare l’estensione Snowplow Chrome. Se hai bisogno di ulteriore assistenza, consulta [Risoluzione dei problemi [!DNL Product Recommendations] modulo](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/troubleshoot-product-recommendations-module-in-magento-commerce.html) nella Knowledge Base di supporto.

## Verificare l’utilizzo degli strumenti per sviluppatori in Chrome

Per assicurarsi che il file JS dell&#39;agente di raccolta eventi venga caricato su tutte le pagine del sito:

1. In Chrome, scegliere **Personalizzare e controllare Google Chrome** quindi seleziona **Altri strumenti** > **Strumenti per sviluppatori**.
1. Scegli la **Rete** quindi selezionare la scheda **JS** tipo.
1. Filtra per `ds.`
1. Ricarica la pagina.
1. Dovresti vedere `ds.js` o `ds.min.js` nel **Nome** colonna.

![JS agente di raccolta eventi](assets/filter-ds.png)
_JS agente di raccolta eventi_

Per garantire che gli eventi vengano attivati sulle pagine del sito (home, prodotto, pagamento e così via):

1. Assicurati di disabilitare i blocchi degli annunci sul browser e accettare i cookie sul sito.
1. In Chrome, scegliere **Personalizzare e controllare Google Chrome** (i tre punti verticali nell’angolo superiore destro del browser), quindi seleziona **Altri strumenti** > **Strumenti per sviluppatori**.
1. Scegli la **Rete** scheda e filtro per `tp2`.
1. Ricarica la pagina.
1. Dovresti vedere le chiamate in `tp2` nel **Nome** colonna.

![Eventi di attivazione](assets/filter-tp2.png)
_Verificare che gli eventi siano attivi_

## Verifica tramite l’estensione Snowplow Chrome

Installare [Estensione Snowplow Analytics Debugger per Chrome](https://chrome.google.com/webstore/detail/snowplow-analytics-debugg/jbnlcgeengmijcghameodeaenefieedm). Questa estensione visualizza gli eventi raccolti e inviati ad Adobe Commerce.

1. Assicurati di disabilitare i blocchi degli annunci sul browser e accettare i cookie sul sito.

1. In Chrome, scegliere **Personalizzare e controllare Google Chrome** (i tre punti verticali nell’angolo superiore destro del browser), quindi seleziona **Altri strumenti** > **Strumenti per sviluppatori**.

1. Scegli la **Debugger di Snowplow Analytics** scheda.

1. Sotto **Evento** colonna, seleziona **Evento strutturato**.

1. Scorri verso il basso fino a visualizzare **Dati contestuali _n_**. Cerca l’istanza storefront in **Schema**.

1. Verificare che [ID spazio dati SaaS](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) è impostato correttamente.

![Filtro Snowplow](assets/snowplow-filter.png)
_Filtro Snowplow_

>[!NOTE]
>
> Un valore di `Data validity : NOT FOUND` nel debugger indica uno schema interno. Il plug-in Snowplow Chrome non può convalidare gli eventi con uno schema interno. Questo non ha alcun impatto sulle funzionalità effettive.

## Verificare che gli eventi si attivino correttamente

Per verificare che gli eventi utilizzati per le metriche si attivino correttamente, cerca il `impression-render`, `view`, e `rec-click` in Snowplow Analytics Debugger. Consulta la [elenco completo degli eventi](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/events.html).

>[!NOTE]
>
> Se [Modalità di restrizione cookie](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) è abilitato, Adobe Commerce raccoglie i dati comportamentali solo con il consenso dell’acquirente. Se la Modalità di restrizione cookie è disabilitata, i dati comportamentali vengono raccolti per impostazione predefinita.
