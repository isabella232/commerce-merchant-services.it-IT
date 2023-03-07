---
title: Onboarding
description: Scopri i requisiti e le piattaforme supportate in [!DNL Product Recommendations].
exl-id: ad47ac39-8f6f-4765-84ad-9e3d104385db
source-git-commit: 484319fc1df6c29c972b57c13bd0ed711e374e99
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# Onboarding

Il processo di onboarding per [!DNL Product Recommendations] richiede l&#39;accesso alla riga di comando del server ed è costituito dai passaggi seguenti. Se non hai familiarità con l’utilizzo della riga di comando, chiedi aiuto a uno sviluppatore o a un integratore di sistemi.

- [Flusso di lavoro di implementazione](implementation-workflow.md)
- [Installazione e configurazione](install-configure.md)
- [Impostazioni](settings.md)
- [Verifica](verify.md)
- [Ambiente di staging](staging-environment.md)

## Requisiti

- Adobe Commerce 2.3.x, 2.4.4+
- PHP 8.1, 8.2
- Compositore 2

### Piattaforme supportate

- Adobe Commerce on-premise (EE) : 2.4.4+
- Adobe Commerce on Cloud (ECE) : 2.4.4+

### Supporto di Page Builder

[!DNL Product Recommendations] possono essere aggiunte a una pagina come tipo di contenuto Page Builder. Per aggiungere il supporto di Page Builder al Product Recommendations, fare riferimento a [Installazione e configurazione](install-configure.md).

Consulta [[!DNL Page Builder] Integrazione](page-builder.md) per istruzioni su come aggiungere [!DNL Product Recommendations] in [!DNL Page Builder] contenuto.

### Supporto B2B {#b2bsupport}

I punti vendita B2B spesso richiedono una logica complessa che determina la visibilità dei prodotti e i prezzi per ogni acquirente o gruppo di clienti. [!DNL Product Recommendations] now [supporto](release-notes.md) questa funzionalità rispettando [autorizzazioni categoria](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/category-permissions.html), [cataloghi condivisi](https://experienceleague.adobe.com/docs/commerce-admin/b2b/shared-catalogs/catalog-shared.html), e [prezzo specifico del gruppo di clienti](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/pricing-advanced.html). Ad esempio, se hai nascosto alcune categorie dal segmento dei clienti al dettaglio, a un acquirente in quel segmento non verranno mostrati i consigli per i prodotti in quelle categorie. Inoltre, quando definisci un catalogo condiviso per gruppi di clienti e aziende specifici, questi acquirenti visualizzano i consigli solo per i prodotti a cui possono accedere. Tutti i prodotti consigliati riflettono il prezzo corretto specifico per il gruppo di clienti in base al gruppo di clienti di ciascun acquirente.
