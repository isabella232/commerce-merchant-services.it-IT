---
title: Pozzo di vetrina
description: Il vetrina Live Search restituisce dinamicamente prodotti e miniature consigliati.
exl-id: 88fdc3ed-b606-40de-94b7-435be09c4072
source-git-commit: 7402e97f53b71e488d860215487f4809572b7e6f
workflow-type: tm+mt
source-wordcount: '239'
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
