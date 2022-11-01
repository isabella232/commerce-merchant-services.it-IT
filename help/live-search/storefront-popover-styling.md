---
title: "Stile [!DNL Popover] Elementi"
description: "Note tecniche sulla personalizzazione del [!DNL Live Search storefront popover]"
exl-id: 033049f2-976e-4299-b026-333ac4b481a3
source-git-commit: ba3d983372eb60d5cb42e503c3c26c693668a01e
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# Stile [!DNL Popover] Elementi

La [[!DNL storefront popover]](storefront-popover.md) visualizza sempre il prodotto `name` e `price`e la selezione dei campi non è configurabile. Tuttavia, [!DNL popover] Gli elementi possono essere formattati utilizzando le classi CSS. Ad esempio, le dichiarazioni seguenti cambiano il colore di sfondo del [!DNL popover] contenitore e piè di pagina.

```css
.livesearch.popover-container {
    background-color: lavender;
}

.livesearch.view-all-footer {
    background-color: magenta;
}
```

## Visibilità dei contenitori

Il componente principale del `.livesearch.popover-container` è `.search-autocomplete`.  La `.active` Classe indica la visibilità del contenitore. La `.active` viene aggiunta in modo condizionale quando la [!DNL popover] è aperto.

```css
.search-autocomplete.active   /* visible */
.search-autocomplete          /* not visible */
```

Per ulteriori informazioni sullo stile degli elementi della vetrina, consulta [Fogli di stile a cascata (CSS)](https://devdocs.magento.com/guides/v2.4/frontend-dev-guide/css-topics/css-overview.html) in [Guida per gli sviluppatori di Frontend](https://devdocs.magento.com/guides/v2.4/frontend-dev-guide/bk-frontend-dev-guide.html).

## Selettori di classe

I seguenti selettori di classe possono essere utilizzati per assegnare uno stile al contenitore e agli elementi di prodotto nel [!DNL popover].

* `.livesearch.popover-container`
* `.livesearch.view-all-footer`
* `.livesearch.products-container`
* `.livesearch.product-result`
* `.livesearch.product-name`
* `.livesearch.product-price`

### Selettori classe contenitore

#### .livesearch.popover-container

![[!DNL Popover] container](assets/livesearch-popover-container.png)

#### .livesearch.view-all-footer

![Visualizza tutto il piè di pagina](assets/livesearch-view-all-footer.png)

### Selettori della classe di prodotto

#### .livesearch.products-container

![Contenitore di prodotti](assets/livesearch-product-container.png)

#### .livesearch.product-result

![Risultato del prodotto](assets/livesearch-product-result.png)

#### .livesearch.product-name

![Nome del prodotto](assets/livesearch-product-name.png)

#### .livesearch.product-price

![Prezzo del prodotto](assets/livesearch-product-price.png)

## Utilizzo di un tema modificato {#working-with-modified-theme}

La [!DNL storefront popover] può essere utilizzato con un [tema](https://devdocs.magento.com/guides/v2.3/frontend-dev-guide/themes/theme-overview.html) che eredita i file richiesti da *Luma*. La `top.search` bloccare `header-wrapper` del `Magento_Search` Impossibile modificare il modulo.

```html
<referenceContainer name="header-wrapper">
   <block class="Magento\Framework\View\Element\Template" name="top.search" as="topSearch" template="Magento_Search::form.mini.phtml">
      <arguments>
         <argument name="configProvider" xsi:type="object">Magento\Search\ViewModel\ConfigProvider</argument>
      </arguments>
   </block>
</referenceContainer>
```

## Disabilitazione della [!DNL popover]

Per disabilitare la funzione [!DNL popover] e ripristinare lo standard [Ricerca rapida](https://docs.magento.com/user-guide/catalog/search-quick.html) , immetti il comando seguente:

```bash
bin/magento module:disable Magento_LiveSearchStorefrontPopover
```
