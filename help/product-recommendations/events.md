---
title: Raccogli dati
description: Scopri come gli eventi raccolgono i dati per i consigli di prodotto.
exl-id: b827d88c-327f-4986-8239-8f1921d8383c
source-git-commit: e74bc4aeaa154e751f8d986e0426dd19d55d335e
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Raccogli dati

Quando installi e configuri funzionalità di Adobe Commerce basate su SaaS come [Recommendations del prodotto](install-configure.md) o [Live Search](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/onboard/install.html), i moduli distribuiscono la raccolta di dati comportamentali nella vetrina. Questo meccanismo raccoglie dati comportamentali anonimi dai tuoi acquirenti e potenzia le raccomandazioni sui prodotti. Ad esempio, il `view` viene utilizzato per calcolare il `Viewed this, viewed that` tipo di consiglio e `place-order` viene utilizzato per calcolare il `Bought this, bought that` tipo di consiglio.

>[!NOTE]
>
>La raccolta dei dati ai fini delle raccomandazioni sui prodotti non include informazioni personali identificabili (PII, personally identifiable information). Tutti gli identificatori utente, come gli ID cookie e gli indirizzi IP, sono rigorosamente anonimi. [Ulteriori informazioni](https://www.adobe.com/privacy/experience-cloud.html).

I seguenti eventi non sono specifici per Product Recommendations, ma sono necessari per restituire risultati:

- `view`
- `add-to-cart`
- `place-order`

Il [Raccolta eventi Adobe Commerce Storefront](https://developer.adobe.com/commerce/services/shared-services/storefront-events/collector/#quick-start) elenca tutti gli eventi distribuiti nella vetrina. Da tale elenco, tuttavia, è disponibile un sottoinsieme di eventi specifici per Product Recommendations. Questi eventi raccolgono dati quando gli acquirenti interagiscono con le unità di consigli sulla vetrina e alimentano le metriche utilizzate per aiutarti ad analizzare le prestazioni dei consigli.

| Evento | Descrizione | [Utilizzato per le metriche?](workspace.md) |
| --- | --- | --- |
| `impression-render` | L’unità di consigli viene sottoposta a rendering sulla pagina. | Sì |
| `rec-add-to-cart-click` | Il cliente fa clic su **Aggiungi al carrello** per un articolo nell&#39;unità di consigli. | Sì, quando un **Aggiungi al carrello** presente nel modello di consigli. |
| `rec-click` | Il cliente fa clic su un prodotto nell’unità di consigli. | Sì |
| `view` | L’unità di consigli diventa visualizzabile sulla pagina, ad esempio scorrendo all’interno della visualizzazione. | Sì |

Se la vetrina è implementata con PWA Studi, consulta [Documentazione di PWA](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/). Se utilizzi una tecnologia front-end personalizzata come React o Vue JS, consulta la guida utente per scoprire come integrare Product Recommendations in una [headless](headless.md) ambiente.

## Avvertenze

I blocchi degli annunci e le impostazioni della privacy possono impedire `magento/product-recommendations` dall&#39;acquisizione di eventi e potrebbe causare il coinvolgimento e ricavi [metriche](workspace.md) non deve essere segnalato correttamente.

Eventing non acquisisce ogni transazione che avviene sul sito del commerciante. L&#39;evento ha lo scopo di dare al mercante un&#39;idea generale degli eventi che stanno accadendo sul sito.

Le implementazioni headless devono implementare eventi per alimentare il dashboard di Product Recommendations.

>[!NOTE]
>
>Se [Modalità di restrizione cookie](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) è abilitato, Adobe Commerce non raccoglie i dati comportamentali fino a quando l’acquirente non acconsente all’utilizzo dei cookie. Se la modalità di restrizione dei cookie è disabilitata, Adobe Commerce raccoglie i dati comportamentali per impostazione predefinita.
