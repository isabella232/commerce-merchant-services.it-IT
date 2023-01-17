---
title: '[!DNL Catalog Service and API Mesh]'
description: '''[!DNL API Mesh] per Adobe Commerce offre un modo per integrare più origini dati tramite un endpoint GraphQL comune."'
source-git-commit: 7b95be48c21e17cb6ba88d326fd061f7de2f8fb5
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Catalog Service and API Mesh]

La [Rete API per Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/gateway/overview/) consente agli sviluppatori di integrare API private o di terze parti e altre interfacce con i prodotti Adobe tramite Adobe IO.

Il primo passaggio per utilizzare la mesh API con il servizio catalogo è quello di collegare la mesh API alla tua istanza. Vedi istruzioni dettagliate in [Creare una mesh](https://developer.adobe.com/graphql-mesh-gateway/gateway/create-mesh/).

Per completare la configurazione, è necessario [Pacchetto Adobe IO CLI](https://developer.adobe.com/runtime/docs/guides/tools/cli_install/) installato.

Una volta configurato Mesh su Adobe IO, esegui il seguente comando che aggiunge un `CommerceCatalogServiceGraph` alla rete.

```bash
aio api-mesh:source:install "CommerceCatalogServiceGraph" -f variables.json
```

dove `variables.json` è un file separato che memorizza i valori comunemente utilizzati per Adobe IO.
Ad esempio, la chiave API può essere salvata all’interno del file :

```json
{
    "CATALOG_SERVICE_API_KEY":"your_api_key"
}
```

Dopo aver eseguito questo comando, il servizio catalogo deve essere in esecuzione attraverso la mesh API. Puoi eseguire il `aio api-mesh:get` per visualizzare la configurazione della mesh aggiornata.

## Utilizzo della mesh API

La mesh API consente agli utenti di utilizzare origini dati esterne per migliorare la tua istanza di Adobe Commerce. Può essere utilizzato anche per configurare i dati Commerce esistenti per abilitare nuove funzionalità.

In questo esempio, la mesh API viene utilizzata per abilitare i prezzi di livello in Adobe Commerce.
Sostituisci il `name `, `endpoint` e `x-api-key` valori.

```json
{
  "meshConfig": {
    "sources": [
      {
        "name": "<Commerce Instance Name>",
        "handler": {
          "graphql": {
            "endpoint": "<Adobe Commerce GraphQL endpoint>"
          }
        },
        "transforms": [
            {
                "prefix": {
                    "includeRootOperations": true,
                    "value": "Core_"
                }
            }
        ]
      },
      {
        "name": "CommerceCatalogServiceGraph",
        "handler": {
          "graphql": {
            "endpoint": "https://commerce.adobe.io/catalog-service/graphql/",
            "operationHeaders": {
              "Magento-Store-View-Code": "{context.headers['magento-store-view-code']}",
              "Magento-Website-Code": "{context.headers['magento-website-code']}",
              "Magento-Store-Code": "{context.headers['magento-store-code']}",
              "Magento-Environment-Id": "{context.headers['magento-environment-id']}",
              "x-api-key": "storefront-catalog-apollo",
              "Magento-Customer-Group": "{context.headers['magento-customer-group']}"
            },
            "schemaHeaders": {
              "x-api-key": "<YOUR API-KEY>"
            }
          }
        }
      }
    ],
    "additionalTypeDefs": "extend interface ProductView {\n  price_tiers: [Core_TierPrice]\n}\n extend type SimpleProductView {\n  price_tiers: [Core_TierPrice]\n}\n extend type ComplexProductView {\n  price_tiers: [Core_TierPrice]\n}\n",
    "additionalResolvers": [
        {  
            "targetTypeName": "ProductView",
            "targetFieldName": "price_tiers",
            "sourceName": "MagentoStageCore",
            "sourceTypeName": "Query",
            "sourceFieldName": "Core_products",
            "requiredSelectionSet": "{\n    items {\n  sku\n    price_tiers {\n        quantity,\n        final_price {\n          value\n          currency\n        }\n      }\n    }\n  }",
            "sourceArgs": {
                "filter.sku.eq": "{root.sku}"
            },
            "result": "items[0].price_tiers"
        },
        {  
            "targetTypeName": "SimpleProductView",
            "targetFieldName": "price_tiers",
            "sourceName": "MagentoStageCore",
            "sourceTypeName": "Query",
            "sourceFieldName": "Core_products",
            "requiredSelectionSet": "{\n    items {\n  sku\n    price_tiers {\n        quantity,\n        final_price {\n          value\n          currency\n        }\n      }\n    }\n  }",
            "sourceArgs": {
                "filter.sku.eq": "{root.sku}"
            },
            "result": "items[0].price_tiers"
        },
        {  
            "targetTypeName": "ComplexProductView",
            "targetFieldName": "price_tiers",
            "sourceName": "MagentoStageCore",
            "sourceTypeName": "Query",
            "sourceFieldName": "Core_products",
            "requiredSelectionSet": "{\n    items {\n  sku\n    price_tiers {\n        quantity,\n        final_price {\n          value\n          currency\n        }\n      }\n    }\n  }",
            "sourceArgs": {
                "filter.sku.eq": "{root.sku}"
            },
            "result": "items[0].price_tiers"
        }
    ]
   }
}
```

Una volta configurato, esegui una query sulla mesh per il prezzo su più livelli:

```json
query {
  products(skus: ["24-MB04"]) {
    sku
    description
    price_tiers {
        quantity
        final_price {
          value
          currency
        }
      }
    ... on SimpleProductView {
      id
       
      price {
        final {
          amount {
            value
          }
        }
      }
    }
  }
}
```
