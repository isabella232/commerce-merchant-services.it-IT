---
title: query productSearch
description: 'Guida di riferimento per la query GraphQL `productSearch` per il servizio catalogo Adobe Commerce.'
source-git-commit: d9b8c89f6d04aa9d569b450af2893b92938119ad
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# query productSearch

Servizio catalogo per Adobe Commerce `productSearch` query può utilizzare Live Search per restituire i dettagli sugli SKU specificati come input. Anche se questa query è la stessa del [`productSearch` query](https://devdocs.magento.com/live-search/product-search.html), Live Search restituisce un `productView` oggetto. Consulta la sezione [`productSearch` query](https://devdocs.magento.com/live-search/product-search.html) argomento per informazioni di riferimento.

## Sintassi

```graphql
productSearch(
    phrase: String!
    page_size: Int = 20
    current_page: Int = 1
    filter: [SearchClauseInput!]
    sort: [ProductSearchSortInput!]
): ProductSearchResponse!
```

## Intestazioni richieste

Per eseguire questa query è necessario specificare le seguenti intestazioni HTTP.

| Intestazione | Descrizione |
|--- | ---|
| `Magento-Customer-Group` | Per i client di vetrina, questo valore sarà disponibile nella vetrina nel `dataservices_customer_group` cookie. |
| `Magento-Environment-Id` | Questo valore può essere ottenuto eseguendo il `bin/magento config:show services_connector/services_id/environment_id` comando. Vedere il campo &quot;Spazio dati&quot; in [Commerce Services](https://docs.magento.com/user-guide/configuration/services/saas.html) |
| `Magento-Store-Code` | Il codice assegnato all&#39;archivio associato alla visualizzazione archivio attiva. Ad esempio, `main_website_store`. |
| `Magento-Store-View-Code` | Codice assegnato alla visualizzazione archivio attiva. Ad esempio, `default`. |
| `Magento-Website-Code` | Il codice assegnato al sito web associato alla visualizzazione store attiva. Ad esempio, `base`. |
| `X-Api-Key` | Chiave univoca generata durante il processo di onboarding. |

## Esempio di utilizzo

Nell’esempio seguente, la query restituisce informazioni sugli stessi prodotti dell’esempio precedente. Tuttavia, è stato costruito per restituire le informazioni sugli elementi all’interno del servizio catalogo `productView` oggetto invece del nucleo `product` oggetto. Le informazioni sui prezzi variano a seconda del tipo di prodotto. Per motivi di brevità, le informazioni sulle sfaccettature non vengono visualizzate.

**Richiesta:**

```graphql
{
  productSearch(
    phrase: "bag"
    sort: [
      {
        attribute: "price"
        direction: DESC }]
    page_size: 9
  ) {
    page_info {
      current_page
      page_size
      total_pages
    }
    items {
      productView {
        name
        sku
        ... on SimpleProductView {
          price {
            final {
              amount {
                value
                currency
              }
            }
            regular {
              amount {
                value
                currency
              }
            }
          }
        }
        ... on ComplexProductView {
          options {
            id
            title
            required
            values {
              id
              title
            }
          }
          priceRange {
            maximum {
              final {
                amount {
                  value
                  currency
                }
              }
              regular {
                amount {
                  value
                  currency
                }
              }
            }
            minimum {
              final {
                amount {
                  value
                  currency
                }
              }
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
    }
  }
}
```

**Risposta:**

```json
{
  "data": {
    "productSearch": {
      "page_info": {
        "current_page": 1,
        "page_size": 9,
        "total_pages": 3
      },
      "items": [
        {
          "productView": {
            "name": "Impulse Duffle",
            "sku": "24-UB02",
            "price": {
              "final": {
                "amount": {
                  "value": 74,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 74,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Fusion Backpack 567890",
            "sku": "24-MB02",
            "price": {
              "final": {
                "amount": {
                  "value": 59,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 59,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Rival Field Messenger",
            "sku": "24-MB06",
            "price": {
              "final": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Push It Messenger Bag",
            "sku": "24-WB04",
            "price": {
              "final": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Overnight Duffle",
            "sku": "24-WB07",
            "price": {
              "final": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Wayfarer Messenger Bag 987",
            "sku": "24-MB05",
            "price": {
              "final": {
                "amount": {
                  "value": 44,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 44,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Driven Backpack",
            "sku": "24-WB03",
            "price": {
              "final": {
                "amount": {
                  "value": 36,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 36,
                  "currency": "USD"
                }
              }
            }
          }
        }
      ]
    }
  }
}
```
