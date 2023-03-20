---
title: Senza testa
description: Scopri come integrare [!DNL Product Recommendations] in una vetrina senza testa.
exl-id: 316d0b0c-5938-4e2f-9d0d-747746cf6056
source-git-commit: 78f226465b9d84707612596a5aa4622aa7869ee1
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Senza testa

È possibile integrare [!DNL Product Recommendations] in una vetrina headless utilizzando [PWA Studi](https://developer.adobe.com/commerce/pwa-studio/) o una tecnologia front-end personalizzata, ad esempio React o Vue JS.

[!DNL Product Recommendations] richiedere [dati comportamentali e di catalogo](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/development-overview.html) funzionare. Il processo di sincronizzazione dei dati del catalogo rimane invariato in un’implementazione headless, ma sono necessarie modifiche per la raccolta dei dati comportamentali.

Per integrare [!DNL Product Recommendations] in una vetrina senza testa, devi:

1. Invia dati comportamentali ad Adobe Sensei per analizzare e calcolare i risultati delle raccomandazioni sui prodotti. Puoi anche inviare dati aggiuntivi per abilitare la raccomandazione di prodotto [reporting delle metriche](workspace.md).

1. Recupera i risultati dei consigli di prodotto ed esegui il rendering di tali risultati sulla pagina.

Puoi eseguire entrambe queste azioni utilizzando gli SDK disponibili, come descritto nel flusso di lavoro seguente.

1. [Installa](install-configure.md) la [!DNL Product Recommendations] modulo .

1. Installa e utilizza il [SDK evento Adobe Commerce Storefront](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) per attivare [eventi comportamentali](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/events.html).

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
   | `rec-add-to-cart-click` | unità di raccomandazione (se nel modello di consigli è presente un pulsante &quot;Aggiungi al carrello&quot;) |

1. Quando gli eventi vengono attivati, utilizza la variabile [Raccoglitore eventi Adobe Commerce Storefront](https://developer.adobe.com/commerce/services/shared-services/storefront-events/collector/) per gestire gli eventi e inviarli ad Adobe Sensei.

1. Una volta raccolti i dati comportamentali, puoi [creare](create.md) [!DNL Product Recommendations] nell&#39;amministratore.

1. Utilizza la [SDK per Recommendations](https://developer.adobe.com/commerce/services/product-recommendations/) per recuperare le unità dei consigli sulla vetrina. L&#39;SDK restituisce i dati di prodotto necessari per eseguire il rendering delle unità di raccomandazione su una pagina.
