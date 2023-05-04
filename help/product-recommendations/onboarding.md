---
title: Onboarding
description: Scopri i requisiti e le piattaforme supportate in [!DNL Product Recommendations].
exl-id: ad47ac39-8f6f-4765-84ad-9e3d104385db
source-git-commit: e74bc4aeaa154e751f8d986e0426dd19d55d335e
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Onboarding

Il processo di onboarding per [!DNL Product Recommendations] richiede l&#39;accesso alla riga di comando del server ed è costituito dai seguenti passaggi. Se non hai familiarità con l’utilizzo della riga di comando, chiedi aiuto a uno sviluppatore o a un integratore di sistema.

- [Flusso di lavoro di implementazione](implementation-workflow.md)
- [Installazione e configurazione](install-configure.md)
- [Impostazioni](settings.md)
- [Verifica](verify.md)
- [Ambiente di staging](staging-environment.md)

## Requisiti

- Adobe Commerce 2.4.4+
- PHP 8.1, 8.2
- Compositore 2

### Piattaforme supportate

- Adobe Commerce on-premise (EE) : 2.4.4+
- Adobe Commerce on Cloud (ECE) : 2.4.4+

### Supporto per Page Builder

[!DNL Product Recommendations] può essere aggiunto a una pagina come tipo di contenuto di Page Builder. Per aggiungere il supporto di Page Builder a Product Recommendations, consulta [Installazione e configurazione](install-configure.md).

Vedi [[!DNL Page Builder] Integrazione](page-builder.md) per istruzioni su come aggiungere [!DNL Product Recommendations] in [!DNL Page Builder] contenuto.

### Indicizzazione dei prezzi SaaS

I clienti delle raccomandazioni sui prodotti possono utilizzare [Indicizzazione dei prezzi SaaS](../price-index/index.md), che offre aggiornamenti più rapidi dei prezzi e tempi di sincronizzazione.

### Supporto B2B {#b2bsupport}

Le vetrine B2B spesso richiedono una logica complessa che determina la visibilità del prodotto e i prezzi per ogni acquirente o gruppo di clienti. [!DNL Product Recommendations] now [supporto](release-notes.md) questa funzionalità onorando [autorizzazioni categoria](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/category-permissions.html), [cataloghi condivisi](https://experienceleague.adobe.com/docs/commerce-admin/b2b/shared-catalogs/catalog-shared.html)e [determinazione dei prezzi per gruppi di clienti](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/pricing-advanced.html). Ad esempio, se hai nascosto alcune categorie dal segmento di clienti al dettaglio, a un acquirente in quel segmento non verranno mostrati consigli per i prodotti in quelle categorie. Inoltre, quando definisci un catalogo condiviso per specifici gruppi di clienti e aziende, questi acquirenti visualizzano i consigli solo per i prodotti a cui possono accedere. Tutti i prodotti consigliati riflettono il prezzo corretto specifico per il gruppo di clienti in base al gruppo di clienti di ciascun acquirente.
