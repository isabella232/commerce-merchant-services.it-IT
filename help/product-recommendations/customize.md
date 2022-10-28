---
title: Personalizza
description: Scopri come personalizzare i consigli sui prodotti.
source-git-commit: 478c5bf7d7830d971c576ce50ff0bf3ffd4fe9e5
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# Personalizza

Quando installi il modulo Recommendations per il prodotto, Adobe Commerce crea il `ProductRecommendationsLayout` directory. Questa directory contiene file di modelli personalizzabili per modificare la modalità di visualizzazione dei consigli sulla vetrina. In particolare, puoi modificare o sostituire il seguente modello:

`<your theme>/Magento_ProductRecommendationsLayout/web/template/recommendations.html`

Per ulteriori informazioni sulla modifica dei file modello, consulta [Personalizzazione dei modelli](https://developer.adobe.com/commerce/frontend-core/guide/templates/walkthrough/) nella Guida per gli sviluppatori di Frontend.

Se modifichi la `recommendations.html` per garantire che Adobe Commerce possa raccogliere le metriche dei consigli dalla vetrina, è necessario conservare i seguenti tag nel file :

| Tag | Utilizzo |
|---|---|
| `<div data-bind="attr : {'data-unit-id' : unitId }"...</div>` | Raccoglie eventi di visualizzazione. |
| `<a data-bind="attr : {'data-sku' : sku, 'data-unit-id'}"...</a>` | Raccoglie eventi di clic. <br/>**Nota:** Se aggiungi dei tag di ancoraggio, devi includere questi attributi. |

Oltre al `recommendations.html` file, `ProductRecommendationsLayout` la directory contiene le sottodirectory seguenti:

| Directory | Finalità |
|---|---|
| `layout` | Contiene `*.xml` file per ogni tipo di pagina |
| `templates` | Contiene i file che chiamano gli script di recupero e rendering |
| `web/js` | Contiene i file JavaScript che recuperano ed eseguono il rendering dei consigli per il tuo archivio |
| `web/template` | Contiene il modello per `magento/product-recommendations` modulo |

## Posizionamento dell&#39;unità di raccomandazione

Quando [creare](create.md) una raccomandazione, specificate la [posizione](placement.md) nella pagina. Un’unità di raccomandazione può essere posizionata nella parte superiore o inferiore del contenitore di contenuto principale. Tuttavia, puoi personalizzare questo posizionamento. Se create un tipo di contenuto per i consigli di Page Builder, utilizzate gli strumenti di Page Builder per posizionare l&#39;unità di raccomandazione sulla pagina. Per tutti gli altri tipi di pagina, modifica il `*.xml` file generati al momento della creazione della raccomandazione.

1. Cambia in `layout` directory:

   ```bash
   cd `<your theme>/Magento_ProductRecommendationsLayout/layout`
   ```

   Nella tabella seguente sono elencati i file XML presenti in questa directory:

   | Nome file | Pagina |
   |---|---|
   | `catalog_category_view.xml` | Categoria |
   | `catalog_product_view.xml` | Dettagli del prodotto |
   | `checkout_cart_index.xml` | Carrello |
   | `checkout_onepage_success.xml` | Pagamento |
   | `cms_index_index.xml` | Pagina principale |

   >[!NOTE]
   >
   >I nomi dei file nel `layout` potrebbe essere diversa se l&#39;archivio utilizza estensioni di terze parti.

1. Modifichiamo il `catalog_product_view.xml` in modo che l&#39;unità di raccomandazione venga visualizzata dopo l&#39;immagine del prodotto nella pagina dei dettagli del prodotto. Prima di personalizzare questo file XML, diamo un&#39;occhiata al file e comprendiamo le sezioni da modificare:

   ```xml
   <?xml version="1.0"?>
   <page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
       <referenceBlock name="page.wrapper">
           <block class="Magento\Framework\View\Element\Template" before="-" name="product_recommendations_fetcher" template="Magento_ProductRecommendationsStorefront::fetcher.phtml" />
       </referenceBlock>
       <body>
           <referenceBlock name="main.content">
               <block class="Magento\ProductRecommendationsStorefront\Block\Renderer" after="-" name="product_recommendations_product_below_content" template="Magento_ProductRecommendationsStorefront::renderer.phtml">
                   <arguments>
                       <argument name="pagePlacement" xsi:type="string">below-main-content</argument>
                   </arguments>
               </block>
           </referenceBlock>
       </body>
   </page>
   ```

   Nello snippet di codice riportato sopra, il `main.content` Il blocco di riferimento indica che l&#39;unità di raccomandazione verrà posizionata in un punto qualsiasi rispetto a tale elemento. La `block` contiene `after="-"` attributo , che specifica che l&#39;unità di raccomandazione verrà visualizzata sulla pagina dopo il blocco di contenuto principale.

1. Modifichiamo questo file specificando un diverso blocco di contenuto.

   Verrà modificato il blocco di riferimento `name` da `main.content` a `product.info.media`.

   ```xml
   <?xml version="1.0"?>
   <page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
       <referenceBlock name="page.wrapper">
           <block class="Magento\Framework\View\Element\Template" before="-" name="product_recommendations_fetcher" template="Magento_ProductRecommendationsStorefront::fetcher.phtml" />
       </referenceBlock>
       <body>
           <referenceBlock name="product.info.media">
               <block class="Magento\ProductRecommendationsStorefront\Block\Renderer" after="-" name="product_recommendations_product_below_content" template="Magento_ProductRecommendationsStorefront::renderer.phtml">
                   <arguments>
                       <argument name="pagePlacement" xsi:type="string">below-main-content</argument>
                   </arguments>
               </block>
           </referenceBlock>
       </body>
   </page>
   ```

   Questa modifica determina la visualizzazione dell&#39;unità di raccomandazione dopo l&#39;immagine del prodotto nella pagina dei dettagli del prodotto. Se desiderate che l&#39;unità di raccomandazione venga visualizzata prima della `product.info.media`, modifica `after="-"` attributo a `before="-"`. La `pagePlacement` argomento interno che non deve essere modificato.

Fai riferimento a [panoramica del layout](https://developer.adobe.com/commerce/frontend-core/guide/layouts/) per ulteriori informazioni sui tipi di blocchi nella pagina.

## Attributi di prodotto personalizzati

Gli sviluppatori devono spesso accedere ai valori degli attributi di prodotto personalizzati nelle unità di consigli su vetrine, in modo da poter aggiungere trattamenti visivi ai prodotti in base a tali attributi.

Ad esempio, se il tuo negozio vende alcuni prodotti biologici, potresti avere un attributo personalizzato su tali prodotti che li designa come `Organic = Yes`. Potrebbe essere necessario accedere a questo valore di attributo nella vetrina in modo da poter fornire a questi prodotti un trattamento visivo speciale quando compaiono in Recommendations. Analogamente, l’accesso a questi valori di attributi di prodotto personalizzati consente di applicare un badge ai prodotti o di indirizzare la logica personalizzata nel livello di presentazione del sito.

![Aggiungi badge](assets/unit.png)

Per assicurarti che sia disponibile un attributo di prodotto personalizzato quando esegui il rendering dell&#39;unità di raccomandazione sulla pagina, imposta la variabile `Used in Product Listing` proprietà di `Yes` in [Attributi del prodotto](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/create/attribute-product-create.html) in Admin.

Quando questa proprietà viene impostata, il payload JSON include un `attributes` oggetto che contiene una matrice di codici e valori attributo. Puoi quindi applicare uno stile personalizzato per la vetrina in base a questi valori di attributo, ad esempio l’aggiunta di trattamenti speciali o badge come indicato in precedenza.

>[!NOTE]
>
>La visualizzazione delle modifiche agli attributi del prodotto nel payload JSON può richiedere fino a un’ora.
