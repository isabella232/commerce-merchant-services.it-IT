---
title: Senza testa
description: Scopri come integrare [!DNL Product Recommendations] in una vetrina senza testa.
exl-id: 316d0b0c-5938-4e2f-9d0d-747746cf6056
source-git-commit: ce437d7a991affd2665c86c9e91bb7f39ec626c0
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Senza testa

È possibile integrare [!DNL Product Recommendations] in una vetrina headless utilizzando [PWA Studi](https://developer.adobe.com/commerce/pwa-studio/) o una tecnologia front-end personalizzata, ad esempio React o Vue JS.

[!DNL Product Recommendations] richiedere [dati comportamentali e di catalogo](https://devdocs.magento.com/recommendations/product-recs.html#typesofdata) funzionare. Il processo di sincronizzazione dei dati del catalogo rimane invariato in un’implementazione headless, ma sono necessarie modifiche per la raccolta dei dati comportamentali.

Per integrare [!DNL Product Recommendations] in una vetrina senza testa, devi:

1. Invia dati comportamentali ad Adobe Sensei per analizzare e calcolare i risultati delle raccomandazioni sui prodotti. Puoi anche inviare dati aggiuntivi per abilitare la raccomandazione di prodotto [reporting delle metriche](workspace.md).

1. Recupera i risultati dei consigli di prodotto ed esegui il rendering di tali risultati sulla pagina.

Puoi eseguire entrambe queste azioni utilizzando gli SDK disponibili, come descritto nel flusso di lavoro seguente.

1. [Installa](install-configure.md) la [!DNL Product Recommendations] modulo .

1. Installa e utilizza il [SDK evento Adobe Commerce Storefront](https://devdocs.magento.com/shared-services/storefront-events-sdk.html) per attivare [eventi comportamentali](https://devdocs.magento.com/recommendations/events.html).

   Eventi minimi richiesti da restituire [!DNL Product Recommendations] risultati:

   | Evento | Categoria |
   |--- | ---|
   | `view` | prodotto |
   | `add-to-cart` | prodotto |
   | `place-order` | pagamento |

   Per abilitare [reporting delle metriche](workspace.md), sono necessari i seguenti eventi aggiuntivi:

   | Evento | Categoria |
   |--- | ---|
   | `impression-render` | unità di raccomandazione |
   | `view` | unità di raccomandazione |
   | `rec-click` | unità di raccomandazione |
   | `rec-add-to-cart-click` | recommendation-unit (se nel modello di consigli è presente un pulsante add to cart ) |

1. Quando gli eventi vengono attivati, utilizza la variabile [Raccoglitore eventi Adobe Commerce Storefront](https://devdocs.magento.com/shared-services/storefront-event-collector.html) per gestire gli eventi e inviarli ad Adobe Sensei.

1. Una volta raccolti i dati comportamentali, puoi [creare](create.md) [!DNL Product Recommendations] nell&#39;amministratore.

1. Utilizza la [SDK per Recommendations](https://devdocs.magento.com/recommendations/recs-api.html) per recuperare le unità dei consigli sulla vetrina. L&#39;SDK restituisce i dati di prodotto necessari per eseguire il rendering delle unità di raccomandazione su una pagina.
