---
title: Pozzo di vetrina
description: Il vetrina Live Search restituisce dinamicamente prodotti e miniature consigliati.
exl-id: 88fdc3ed-b606-40de-94b7-435be09c4072
source-git-commit: 10cea4389d685ce0e26b083872b13a1cd19ba2af
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Pozzo di vetrina

Quando [!DNL Live Search] è [installato](install.md), un pover appare nella vetrina quando gli acquirenti digitano nel [Ricerca](https://docs.magento.com/user-guide/catalog/search-quick.html) scatola. Per ogni carattere digitato, il puntatore viene aggiornato con prodotti consigliati e immagini in miniatura dei risultati di ricerca principali.

[!DNL Live Search] restituisce risultati per una query di due caratteri o più. Per una corrispondenza parziale, il numero massimo di caratteri per parola è 20. Il numero di caratteri in una query &quot;search as you type&quot; non è configurabile.

>[!NOTE]
>
>La [!DNL Live Search] il pover vetrina è disponibile solo per i negozi che utilizzano *Luma* tema o un tema personalizzato basato su *Luma*. La *Luma* il tema è incluso nel [!DNL Commerce] dati di esempio. Il pover non supporta il *Vuoto* tema. Vedi [Utilizzo di un tema modificato](#working-with-modified-theme) per ulteriori informazioni.

## Attributi ricercabili

Per produrre risultati altamente mirati, controlla l&#39;insieme di [ricercabile](https://docs.magento.com/user-guide/stores/attributes-product.html#storefront-properties) (`searchable=true`) gli attributi del prodotto. Per garantire la pertinenza, rendere gli attributi ricercabili solo se contengono contenuto che ha un significato chiaro e conciso. Evita di utilizzare attributi che contengono testo meno preciso e lungo, come `description`, che sebbene sia abilitata per impostazione predefinita per la ricerca, può ridurre la precisione dei risultati della ricerca. Ad esempio, se una persona cerca &quot;pantaloncini&quot; e ci sono camicie con una descrizione che include il termine &quot;maniche corte&quot;, le camicie saranno incluse nei risultati della ricerca.

È sempre possibile cercare i seguenti attributi:

* `sku`
* `name`
* `categories`

![Pover di Live Search](assets/storefront-search-as-you-type.png)

## Dimensioni pagina del puntatore

La dimensione della pagina del popover determina quante righe di prodotti completati automaticamente possono essere restituite. In precedenza, le dimensioni della pagina venivano codificate in sei righe. Tuttavia, `page_size` ora è un&#39;impostazione che può essere configurata dal *Amministratore*. Durante l&#39;installazione di Live Search, il `page_size` il valore cambia nel valore corrente del [Ricerca nel catalogo](https://docs.magento.com/user-guide/configuration/catalog/catalog.html#catalog-search) - `Autocomplete Limit` impostazione.

Per impostazione predefinita, il valore Ricerca nel catalogo - Limite di completamento automatico è impostato su otto righe. Per modificare le dimensioni della pagina del puntatore, procedi come segue:

1. Sulla *Amministratore* barra laterale, vai a **Negozi** > Impostazioni > **Configurazione**.
1. Nel pannello a sinistra, espandi **Catalogo** e scegli **Catalogo** dall’elenco delle impostazioni.
1. Espandi la *Ricerca nel catalogo* sezione .
1. Imposta la **Limite completamento automatico** al numero di righe che si desidera consentire nel pover.
1. Al termine, fai clic su **Salva configurazione**.
