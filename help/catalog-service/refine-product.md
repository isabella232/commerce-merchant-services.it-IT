---
title: query refineProduct
description: "Guida di riferimento per la query GraphQL `refineProduct` per Adobe Commerce Catalog Service."
source-git-commit: 7edfdd71c0900a6bdc7c064a29a6cce405a361ab
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 0%

---


# query refineProduct

La `refineProduct` restringe i risultati di un `products` query eseguita su un prodotto complesso. Prima di eseguire il `refineProduct` eseguire la query `products` eseguire una query e creare la risposta in modo che restituisca un elenco di `options` all&#39;interno di `ComplexProductView` frammento in linea. Quando un acquirente seleziona un&#39;opzione di prodotto (come la dimensione o il colore) sulla vetrina, esegui la `refineProduct` query, specifica lo SKU e gli ID dei valori dell’opzione selezionati come input. A seconda del numero di opzioni di prodotto disponibili per il prodotto complesso, potrebbe essere necessario eseguire il `refineProduct` eseguire query più volte, fino a quando l&#39;acquirente non ha selezionato una variante specifica.

È necessario creare la risposta della query in modo che contenga sia `ComplexProductView` e `SimpleProductView` frammenti in linea. Se l’acquirente non ha selezionato tutte le opzioni richieste, la query restituirà gli ID delle opzioni non selezionate e il prezzo minimo e massimo del prodotto, in base alle opzioni selezionate e alle possibili opzioni rimanenti. Se l’acquirente ha selezionato tutte le opzioni richieste, la query restituisce i dettagli relativi a un prodotto semplice, che include un prezzo impostato.

## Sintassi

```graphql
refineProduct(sku: String!, optionIds: [String!]!): ProductView
```

## Intestazioni richieste

Per eseguire questa query è necessario specificare le seguenti intestazioni HTTP.

| Intestazione | Descrizione |
|--- | ---|
| `Magento-Customer-Group` | Per i client di vetrina, questo valore sarà disponibile nella vetrina nel `dataservices_customer_group` cookie. |
| `Magento-Environment-Id` | Questo valore viene visualizzato in **Sistema** > **Connettore Commerce Services** > **Identificatore SaaS** > **ID spazio dati** o può essere ottenuto eseguendo il `bin/magento config:show services_connector/services_id/environment_id` comando. |
| `Magento-Store-Code` | Il codice assegnato all&#39;archivio associato alla visualizzazione archivio attiva. Ad esempio, `main_website_store`. |
| `Magento-Store-View-Code` | Codice assegnato alla visualizzazione archivio attiva. Ad esempio, `default`. |
| `Magento-Website-Code` | Il codice assegnato al sito web associato alla visualizzazione store attiva. Ad esempio, `base`. |
| `X-Api-Key` | Chiave univoca generata durante il processo di onboarding. |

## Esempio di utilizzo

### Restituisce i dettagli di un prodotto complesso selezionato parzialmente

La seguente query restituisce i dettagli sulle opzioni di colore disponibili per una variante di prodotto di medie dimensioni `MH12`. Il valore del `optionIDs` il parametro di input è tratto dalla variabile `products` query [Restituire dettagli su un prodotto complesso](products.md#complex-product-example) esempio.

**Richiesta:**

```graphql
query {
    refineProduct(optionIds: ["Y29uZmlndXJhYmxlLzE4Ni8xNzc="], sku: "MH12") {
        __typename
        id
        sku
        name
        url
        ... on SimpleProductView {
            price {
                final {
                    amount {
                        value
                    }
                }
                regular {
                    amount {
                        value
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
                        }
                    }
                    regular {
                        amount {
                            value
                        }
                    }
                }
                minimum {
                    final {
                        amount {
                            value
                        }
                    }
                    regular {
                        amount {
                            value
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
    "refineProduct": {
      "__typename": "ComplexProductView",
      "id": "VFVneE1nAFpHVm1ZWFZzZEEATXpSbE1qYzBNR0V0TnpRM015MDBZemc1TFRnM016QXROVGMwTURObVkyVXlOMkZsAGJXRnBibDkzWldKemFYUmxYM04wYjNKbABZbUZ6WlEAVFVGSFUxUkhNREExTlRjNU1ETTQ",
      "sku": "MH12",
      "name": "Ajax Full-Zip Sweatshirt 2",
      "url": "http://example.com/ajax-full-zip-sweatshirt.html",
      "options": [
        {
          "id": "color",
          "title": "Color",
          "required": false,
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
        }
      ],
      "priceRange": {
        "maximum": {
          "final": {
            "amount": {
              "value": 69
            }
          },
          "regular": {
            "amount": {
              "value": 69
            }
          }
        },
        "minimum": {
          "final": {
            "amount": {
              "value": 69
            }
          },
          "regular": {
            "amount": {
              "value": 69
            }
          }
        }
      }
    }
  }
}
```

### Restituisci dettagli su un prodotto complesso completamente selezionato

Nella seguente query, l’acquirente ha selezionato le opzioni per le dimensioni e il colore. La risposta contiene dettagli sul prodotto semplice corrispondente.

**Richiesta:**

```graphql
query {
    refineProduct(optionIds: ["Y29uZmlndXJhYmxlLzE4Ni8xNzc=", "Y29uZmlndXJhYmxlLzkzLzU5"], sku: "MH12") {
        __typename
        id
        sku
        name
        url
        ... on SimpleProductView {
            price {
                final {
                    amount {
                        value
                    }
                }
                regular {
                    amount {
                        value
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
                        }
                    }
                    regular {
                        amount {
                            value
                        }
                    }
                }
                minimum {
                    final {
                        amount {
                            value
                        }
                    }
                    regular {
                        amount {
                            value
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
    "refineProduct": {
      "__typename": "SimpleProductView",
      "id": "VFVneE1pMU5MVUpzZFdVAFpHVm1ZWFZzZEEATXpSbE1qYzBNR0V0TnpRM015MDBZemc1TFRnM016QXROVGMwTURObVkyVXlOMkZsAGJXRnBibDkzWldKemFYUmxYM04wYjNKbABZbUZ6WlEAVFVGSFUxUkhNREExTlRjNU1ETTQ",
      "sku": "MH12-M-Blue",
      "name": "Ajax Full-Zip Sweatshirt -M-Blue",
      "url": "http://example.com/catalog/product/view/id/235/s/ajax-full-zip-sweatshirt-m-blue/",
      "price": {
        "final": {
          "amount": {
            "value": 69
          }
        },
        "regular": {
          "amount": {
            "value": 69
          }
        }
      }
    }
  }
}
```

## Campi di input

È necessario specificare un valore SKU e almeno un ID opzione come input.

| Campo | Tipo di dati | Descrizione |
|--- | --- | ---|
| `optionIds` | [Stringa!]! | Un elenco di ID assegnati alle opzioni di prodotto selezionate dall&#39;acquirente, quali colori e dimensioni specifici. |
| `sku` | Stringa! | SKU di un prodotto complesso. |

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
