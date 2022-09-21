---
title: query sui prodotti
description: "Guida di riferimento per la query GraphQL `products` per Adobe Commerce Catalog Service."
source-git-commit: 7edfdd71c0900a6bdc7c064a29a6cce405a361ab
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 0%

---


# query sui prodotti

Servizio catalogo per Adobe Commerce `products` query restituisce i dettagli sugli SKU specificati come input. Anche se questa query ha lo stesso nome della [`products` query](https://devdocs.magento.com//guides/v2.4/graphql/queries/products.html) che viene fornito con Adobe Commerce e Magento Open Source di base, ci sono alcune differenze.

La query Servizio catalogo richiede uno o più valori SKU come input. La query è progettata principalmente per recuperare informazioni per eseguire il rendering dei seguenti tipi di contenuto:

* Pagine dei dettagli del prodotto - Puoi fornire dettagli completi sul prodotto identificato dallo SKU specificato.

* Pagine di confronto dei prodotti - È possibile recuperare informazioni selezionate su più prodotti, come nome, prezzo e immagine.

La `ProductView` l&#39;oggetto di output è significativamente diverso dal core `products` query `Products` oggetto di output. Le principali differenze includono:

* I prodotti sono semplici o complessi. I prodotti con carta regalo semplici, virtuali, scaricabili e possono essere mappati su `SimpleProductView`. Tutti gli altri tipi di prodotto vengono mappati su `ComplexProductView`. I prodotti semplici hanno definito i prezzi. I prodotti complessi hanno fasce di prezzo. Dal momento che i prodotti complessi sono costituiti da più prodotti semplici, hanno accesso a prezzi di prodotto semplici.

* Gli attributi definiti dal merchant sono esposti in un contenitore principale e indicano i loro ruoli di vetrina. I ruoli includono Mostra su PDP, Mostra su PLP e Mostra sui risultati della ricerca.

* Le immagini sono accessibili anche come contenitore principale e possono essere filtrate in base al loro ruolo. Un&#39;immagine può avere un ruolo di base, piccolo o miniatura.

## Sintassi

```graphql
products (skus [String]) [ProductView]
```

## Intestazioni richieste

Per eseguire questa query è necessario specificare le seguenti intestazioni HTTP.

| Intestazione | Descrizione |
| --- | --- |
| `Magento-Customer-Group` | Per i client di vetrina, questo valore sarà disponibile nella vetrina nel `dataservices_customer_group` cookie. |
| `Magento-Environment-Id` | Questo valore viene visualizzato in **Sistema** > **Connettore Commerce Services** > **Identificatore SaaS** > **ID spazio dati** o può essere ottenuto eseguendo il `bin/magento config:show services_connector/services_id/environment_id` comando. |
| `Magento-Store-Code` | Il codice assegnato all&#39;archivio associato alla visualizzazione archivio attiva. Ad esempio, `main_website_store`. |
| `Magento-Store-View-Code` | Codice assegnato alla visualizzazione archivio attiva. Ad esempio, `default`. |
| `Magento-Website-Code` | Il codice assegnato al sito web associato alla visualizzazione store attiva. Ad esempio, `base`. |
| `X-Api-Key` | Chiave univoca generata durante il processo di onboarding. |

## Esempio di utilizzo

### Restituire dettagli su un prodotto semplice

La seguente query restituisce i dettagli su un prodotto semplice.

**Richiesta:**

```graphql
query {
  products(skus: ["24-MB02"]) {
    id
    sku
    name
    url
    description
    shortDescription
    attributes(roles: ["visible in Search"]) {
      name
      label
      value
      roles
    }
    ... on SimpleProductView {
      price {
        regular {
          amount {
            value
            currency
          }
        }
      }
    }
  }
}
```

**Risposta:**

```json
{
  "data": {
    "products": [
      {
        "id": "TWpRdFRVSXdNZwBaR1ZtWVhWc2RBAE16UmxNamMwTUdFdE56UTNNeTAwWXpnNUxUZzNNekF0TlRjME1ETm1ZMlV5TjJGbABiV0ZwYmw5M1pXSnphWFJsWDNOMGIzSmwAWW1GelpRAFRVRkhVMVJITURBMU5UYzVNRE00",
        "sku": "24-MB02",
        "name": "Fusion Backpack 567890",
        "url": "http://example.com/fusion-backpack.html",
        "description": "<p>With the Fusion Backpack strapped on, every trek is an adventure - even a bus ride to work. That's partly because two large zippered compartments store everything you need, while a front zippered pocket and side mesh pouches are perfect for stashing those little extras, in case you change your mind and take the day off.</p>\r\n<ul>\r\n<li>Durable nylon construction.</li>\r\n<li>2 main zippered compartments.</li>\r\n<li>1 exterior zippered pocket.</li>\r\n<li>Mesh side pouches.</li>\r\n<li>Padded, adjustable straps.</li>\r\n<li>Top carry handle.</li>\r\n<li>Dimensions: 18\" x 10\" x 6\".</li>\r\n</ul>",
        "shortDescription": "",
        "attributes": [
          {
            "name": "activity",
            "label": "Activity",
            "value": [
              "Hiking",
              "School",
              "Yoga"
            ],
            "roles": [
              "visible in PDP",
              "visible in compare list",
              "visible in Search"
            ]
          },
          {
            "name": "features_bags",
            "label": "Features",
            "value": [
              "Hydration Pocket",
              "Audio Pocket",
              "Waterproof",
              "Lightweight"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "material",
            "label": "Material",
            "value": [
              "Burlap",
              "Nylon",
              "Polyester"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "strap_bags",
            "label": "Strap/Handle",
            "value": [
              "Adjustable",
              "Double",
              "Padded"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "style_bags",
            "label": "Style Bags",
            "value": [
              "Backpack",
              "Laptop"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          }
        ],
        "price": {
          "regular": {
            "amount": {
              "value": 59,
              "currency": "USD"
            }
          }
        }
      }
    ]
  }
}
```

### Restituire dettagli su un prodotto complesso {#complex-product-example}

La seguente query restituisce i dettagli su un prodotto configurabile.

**Richiesta:**

```graphql
query {
  products(skus: ["MH12"]) {
    __typename
    id
    sku
    name
    url
    description
    shortDescription
    attributes(roles: ["visible in Search"]) {
      name
      label
      value
      roles
    }
    ... on ComplexProductView {
      priceRange {
        maximum {
          regular {
            amount {
              value
              currency
            }
          }
        }
        minimum {
          regular {
            amount {
              value
              currency
            }
          }
        }
      }
      options {
        id
        required
        title
        values {
          id
          title
        }
      }
    }
  }
}
```

**Risposta:**

```json
{
  "data": {
    "products": [
      {
        "__typename": "ComplexProductView",
        "id": "VFVneE1nAFpHVm1ZWFZzZEEATXpSbE1qYzBNR0V0TnpRM015MDBZemc1TFRnM016QXROVGMwTURObVkyVXlOMkZsAGJXRnBibDkzWldKemFYUmxYM04wYjNKbABZbUZ6WlEAVFVGSFUxUkhNREExTlRjNU1ETTQ",
        "sku": "MH12",
        "name": "Ajax Full-Zip Sweatshirt 2",
        "url": "http://example.com/ajax-full-zip-sweatshirt.html",
        "description": "<p>The Ajax Full-Zip Sweatshirt makes the optimal layering or outer piece for archers, golfers, hikers and virtually any other sportsmen. Not only does it have top-notch moisture-wicking abilities, but the tight-weave fabric also prevents pilling from repeated wash-and-wear cycles.</p>\r\n<p>&bull; Mint striped full zip hoodie.<br />&bull; 100% bonded polyester fleece.<br />&bull; Pouch pocket.<br />&bull; Rib cuffs and hem. <br />&bull; Machine washable.</p>",
        "shortDescription": "",
        "attributes": [
          {
            "name": "climate",
            "label": "Climate",
            "value": [
              "All-Weather",
              "Cool",
              "Indoor",
              "Spring",
              "Windy"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "customattribute",
            "label": "customAttribute",
            "value": "asd",
            "roles": [
              "visible in PDP",
              "visible in PLP",
              "visible in Search"
            ]
          },
          {
            "name": "material",
            "label": "Material",
            "value": [
              "Fleece",
              "Polyester"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "pattern",
            "label": "Pattern",
            "value": "Striped",
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "testtttattribute",
            "label": "testtttAttribute",
            "value": "asd",
            "roles": [
              "visible in PDP",
              "visible in PLP",
              "visible in Search"
            ]
          }
        ],
        "priceRange": {
          "maximum": {
            "regular": {
              "amount": {
                "value": 69,
                "currency": "USD"
              }
            }
          },
          "minimum": {
            "regular": {
              "amount": {
                "value": 69,
                "currency": "USD"
              }
            }
          }
        },
        "options": [
          {
            "id": "color",
            "required": false,
            "title": "Color",
            "values": [
              {
                "id": "Y29uZmlndXJhYmxlLzkzLzU5",
                "title": "Blue"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzkzLzY3",
                "title": "Red"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzkzLzYy",
                "title": "Green"
              }
            ]
          },
          {
            "id": "size",
            "required": false,
            "title": "Size",
            "values": [
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzU=",
                "title": "XS"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzY=",
                "title": "S"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzc=",
                "title": "M"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzg=",
                "title": "L"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzk=",
                "title": "XL"
              }
            ]
          }
        ]
      }
    ]
  }
}
```

## Campi di output

La `ProductView` l&#39;oggetto return è un&#39;interfaccia che può contenere i campi seguenti. È implementato dal [`SimpleProductView`](#SimpleProductView-type) e [`ComplexProductView`](#ComplexProductView-type) tipi.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `attributes(roles: [String])` | [ProductViewAttribute] | Elenco degli attributi definiti dal commerciante designati per la vetrina. |
| `description` | Stringa | Descrizione dettagliata del prodotto. |
| `id` | ID! | L’ID prodotto, generato come chiave composita, univoco per impostazione internazionale. |
| `images(roles: [String])` | [ProductViewImage] | Elenco di immagini definite per il prodotto. |
| `metaDescription` | Stringa | Breve panoramica del prodotto per gli elenchi dei risultati della ricerca. |
| `metaKeyword` | Stringa | Un elenco separato da virgole di parole chiave visibili solo ai motori di ricerca. |
| `metaTitle` | Stringa | Una stringa visualizzata nella barra del titolo e nella scheda del browser e negli elenchi dei risultati della ricerca. |
| `name` | Stringa | Nome del prodotto. |
| `shortDescription` | Stringa | Riepilogo del prodotto. |
| `sku` | Stringa | SKU del prodotto. |
| `url` | Stringa | URL canonico del prodotto. |

### Tipo ComplexProductView {#ComplexProductView-type}

La `ComplexProductView` type rappresenta i prodotti bundle, configurabili e di gruppo. I prezzi dei prodotti complessi vengono restituiti come fascia di prezzo, perché i valori di prezzo possono variare in base alle opzioni selezionate. Il tipo implementa `ProductView`.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `attributes(roles: [String])` | [ProductViewAttribute] | Elenco degli attributi definiti dal commerciante designati per la vetrina. |
| `description` | Stringa | Descrizione dettagliata del prodotto. |
| `id` | ID! | L’ID prodotto, generato come chiave composita, univoco per impostazione internazionale. |
| `images(roles: [String])` | [ProductViewImage] | Elenco di immagini definite per il prodotto. |
| `metaDescription` | Stringa | Breve panoramica del prodotto per gli elenchi dei risultati della ricerca. |
| `metaKeyword` | Stringa | Un elenco separato da virgole di parole chiave visibili solo ai motori di ricerca. |
| `metaTitle` | Stringa | Una stringa visualizzata nella barra del titolo e nella scheda del browser e negli elenchi dei risultati della ricerca. |
| `name` | Stringa | Nome del prodotto. |
| `options` | [OpzioneVisualizzazioneProdotto] | Elenco di opzioni selezionabili. |
| `priceRange` | ProductViewPriceRange | Una gamma di prezzi possibili per un prodotto complesso. |
| `shortDescription` | Stringa | Riepilogo del prodotto. |

### Tipo di prezzo

La `Price type` definisce il prezzo di un prodotto semplice o di una parte di una fascia di prezzo per un prodotto complesso. Può includere un elenco di adeguamenti dei prezzi.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `amount` | ProductViewMoney | Contiene il valore monetario e il codice della valuta di un prodotto. |

### Tipo PriceAdjustment

La `PriceAdjustment` tipo specifica l&#39;importo e il tipo di adeguamento del prezzo. Un valore di codice di esempio è `weee`.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `amount` | Mobile | Importo dell&#39;aggiustamento dei prezzi. |
| `code` | Stringa | Identifica il tipo di adeguamento del prezzo. |

### Tipo ProductViewAttribute

La `ProductViewAttribute` type è un contenitore per gli attributi definiti dal cliente visualizzati nella vetrina.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `label` | Stringa | Etichetta dell&#39;attributo. |
| `name` | Stringa! | Nome di un codice di attributo. |
| `roles` | [Stringa] | Ruoli designati per un attributo sulla vetrina, ad esempio &quot;Mostra su PLP&quot;, &quot;Mostra in PDP&quot; o &quot;Mostra in ricerca&quot;. |
| `value` | JSON | Valore attributo, arbitrario di tipo. |

### Tipo ProductViewImage

La `ProductViewImage` Il tipo contiene i dettagli di un’immagine di prodotto.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `label` | Stringa | Etichetta di visualizzazione dell’immagine del prodotto. |
| `roles` | [Stringa] | Elenco che descrive l’utilizzo dell’immagine. Può essere `image`, `small_image`oppure `thumbnail`. |
| `url` | Stringa! | L’URL dell’immagine del prodotto. |

### Tipo ProductViewMoney

La `ProductViewMoney` Il tipo definisce un valore monetario, compreso un valore numerico e un codice valuta.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `currency` | ProductViewCurrency | Codice valuta a tre lettere, ad esempio USD o EUR. |
| `value` | Mobile | Un numero che esprime un valore monetario. |

### Tipo ProductViewOption

Le opzioni di prodotto consentono di configurare i prodotti effettuando selezioni di particolari valori di opzione. Selezionando una o più opzioni si punta a un prodotto semplice specifico.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `id` | ID | ID dell’opzione. |
| `multi` | Booleano | Indica se l’opzione consente più scelte. |
| `required` | Booleano | Indica se l’opzione deve essere selezionata. |
| `title` | Stringa | Nome visualizzato dell’opzione. |
| `values` | [ProductViewOptionValue!] | Elenco dei valori delle opzioni disponibili. |

### Interfaccia ProductViewOptionValue

La `ProductViewOptionValue` l’interfaccia definisce i campi del prodotto disponibili per `ProductViewOptionValueProduct` e `ProductViewOptionValueConfiguration` tipi.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `id` | ID | ID di un valore di opzione. |
| `title` | Stringa | Nome visualizzato del valore dell&#39;opzione. |

### Tipo ProductViewOptionValueConfiguration

La `ProductViewOptionValueConfiguration` type è un’implementazione di `ProductViewOptionValue` per i valori di configurazione.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `id` | ID | ID di un valore di opzione. |
| `title` | Stringa | Nome visualizzato del valore dell&#39;opzione. |

### Tipo di prodotto ProductViewOptionValue

La `ProductViewOptionValueProduct` type è un’implementazione di `ProductViewOptionValue` che aggiunge dettagli su un prodotto semplice.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `id` | ID | ID di un valore di opzione. |
| `title` | Stringa | Nome visualizzato del valore dell&#39;opzione. |
| `product` | SimpleProductView | Dettagli su un prodotto semplice. |

### Tipo ProductViewPrice

La `ProductViewPrice` type fornisce la visualizzazione del prezzo di base del prodotto, inerente ai prodotti semplici.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `final` | Prezzo | Valore del prezzo dopo gli sconti, escluse le promozioni personalizzate. |
| `regular` | Prezzo | Prezzo di base specificato dal commerciante. |
| `roles` | [Stringa] | Determina se il prezzo deve essere visibile o nascosto. |

### Tipo ProductViewPriceRange

La `ProductViewPriceRange` tipo elenca il prezzo minimo e massimo di un prodotto complesso.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `maximum` | PrezzoVisualizzazioneProdotto | Prezzo massimo. |
| `minimum` | PrezzoVisualizzazioneProdotto | Prezzo minimo. |

### Tipo SimpleProductView {#SimpleProductView-type}

La `SimpleProductView` type rappresenta tutti i tipi di prodotto, eccetto bundle, configurabili e group. I prezzi dei prodotti semplici non contengono fasce di prezzo. `SimpleProductView` implementazioni `ProductView`.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `attributes(roles: [String])` | [ProductViewAttribute] | Elenco degli attributi definiti dal commerciante designati per la vetrina. |
| `description` | Stringa | Descrizione dettagliata del prodotto. |
| `id` | ID! | L’ID prodotto, generato come chiave composita, univoco per impostazione internazionale. |
| `images(roles: [String])` | [ProductViewImage] | Elenco di immagini definite per il prodotto. |
| `metaDescription` | Stringa | Breve panoramica del prodotto per gli elenchi dei risultati della ricerca. |
| `metaKeyword` | Stringa | Un elenco separato da virgole di parole chiave visibili solo ai motori di ricerca. |
| `metaTitle` | Stringa | Una stringa visualizzata nella barra del titolo e nella scheda del browser e negli elenchi dei risultati della ricerca. |
| `name` | Stringa | Nome del prodotto. |
| `price` | PrezzoVisualizzazioneProdotto | Vista del prezzo del prodotto di base. |
| `shortDescription` | Stringa | Riepilogo del prodotto. |
| `sku` | Stringa | SKU del prodotto. |
| `url` | Stringa | URL canonico del prodotto. |
