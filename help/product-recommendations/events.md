---
title: Raccogliere dati
description: Scopri come gli eventi raccolgono i dati per i consigli sui prodotti.
exl-id: b827d88c-327f-4986-8239-8f1921d8383c
source-git-commit: 78f226465b9d84707612596a5aa4622aa7869ee1
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Raccogliere dati

Quando installi e configuri funzioni Adobe Commerce basate su SaaS, come [Recommendations di prodotto](install-configure.md) o [Live Search](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/onboard/install.html), i moduli distribuiscono la raccolta di dati comportamentali alla vetrina. Questo meccanismo raccoglie dati comportamentali anonimi dai tuoi acquirenti e potenzia le raccomandazioni sui prodotti. Ad esempio, il `view` viene utilizzato per calcolare il `Viewed this, viewed that` tipo di raccomandazione e `place-order` viene utilizzato per calcolare il `Bought this, bought that` tipo di raccomandazione.

>[!NOTE]
>
>La raccolta dei dati ai fini delle raccomandazioni sui prodotti non include informazioni personali identificabili (PII). Tutti gli identificatori utente, come gli ID cookie e gli indirizzi IP, sono rigorosamente anonimi. [Ulteriori informazioni](https://www.adobe.com/privacy/experience-cloud.html).

I seguenti eventi non sono specifici per Product Recommendations, ma sono necessari per restituire i risultati:

- `view`
- `add-to-cart`
- `place-order`

La [Raccoglitore eventi Adobe Commerce Storefront](https://developer.adobe.com/commerce/services/shared-services/storefront-events/collector/#quick-start) elenca tutti gli eventi distribuiti nella vetrina. Da tale elenco, tuttavia, esiste un sottoinsieme di eventi specifici per Product Recommendations. Questi eventi raccolgono i dati quando gli acquirenti interagiscono con le unità dei consigli sulla vetrina e alimentano le metriche utilizzate per analizzare le prestazioni dei consigli.

| Evento | Descrizione | [Utilizzato per le metriche?](workspace.md) |
| --- | --- | --- |
| `impression-render` | Viene eseguito il rendering dell&#39;unità raccomandazione sulla pagina. | Sì |
| `rec-add-to-cart-click` | Il cliente fa clic sul pulsante **Aggiungi al carrello** per un elemento nell&#39;unità di raccomandazione. | Sì, quando un **Aggiungi al carrello** Questo pulsante è presente nel modello di consigli . |
| `rec-click` | Il cliente fa clic su un prodotto nell&#39;unità di raccomandazione. | Sì |
| `view` | L&#39;unità di raccomandazione diventa visualizzabile sulla pagina, ad esempio scorrendo nella visualizzazione. | Sì |

Se la vetrina è implementata con PWA Studi, consulta [Documentazione di PWA](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/). Se utilizzi una tecnologia front-end personalizzata come React o Vue JS, consulta la guida utente per scoprire come integrare Product Recommendations in una [senza testa](headless.md) ambiente.

Gli Ad Blocker e le impostazioni di privacy possono impedire `magento/product-recommendations` modulo dall&#39;acquisizione di eventi e potrebbe causare coinvolgimento e ricavi [metriche](workspace.md) da non segnalare.

>[!NOTE]
>
>Se [Modalità di restrizione dei cookie](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) è abilitato e Adobe Commerce non raccoglie dati comportamentali finché l’acquirente non acconsente all’utilizzo dei cookie. Se la modalità di restrizione dei cookie è disabilitata, Adobe Commerce raccoglie i dati comportamentali per impostazione predefinita.
