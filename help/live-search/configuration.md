---
title: '"Impostazioni delle configurazioni Commerce e [!DNL Live Search] '''
description: Descrive le impostazioni di configurazione di Adobe Commerce che [!DNL Live Search] può leggere.
exl-id: a4e9e2dd-e912-4ced-a44a-091ac5334e50
features: Services, Search, Configuration
source-git-commit: 9ae4aff1851e9ce9920c4fbf11d2616d6f0f6307
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# [!DNL Live Search] e Adobe Commerce Configuration Settings

Alcune impostazioni di configurazione di Commerce [!DNL Live Search] supporta. In questo argomento sono elencati questi valori di configurazione.

## Valori di configurazione supportati

| Impostazione configurazione Commerce | Supportato da Popover | Supportato dall&#39;adattatore |
|---|---|---|
| Archivi > Configurazione > Catalogo > Catalogo > Ricerca nel catalogo > Consenti tutti i prodotti per lunghezza pagina | Sì. Max. 500 prodotti | Sì. Max. 500 prodotti |
| Archivi > Configurazione > Catalogo > Catalogo > Ricerca nel catalogo > Lunghezza minima query | Sì | Sì |
| Archivi > Configurazione > Catalogo > Catalogo > Ricerca nel catalogo > Prodotti per pagina sulla griglia Valori consentiti | Sì | Sì |
| Archivi > Configurazione > Catalogo > Catalogo > Ricerca nel catalogo > Prodotti per pagina sulla griglia Valore predefinito | Sì | Sì |
| Negozi > Configurazione > Catalogo > Inventario > Visualizza prodotti esauriti | Sì con v2.0.4+ | Sì con v2.0.4+ |
| Archivi > Configurazione > Valuta > Valuta di visualizzazione predefinita | Sì con 3.1.0+ | Sì con 3/1/0+ |
| Archivi > Configurazione > Generale > Impostazione divisa > Opzioni divisa > Divisa di base | Sì | Sì |

I prezzi nella pagina di elenco dei prodotti Widget e nel popover vengono ora convertiti nella valuta di visualizzazione predefinita utilizzando i tassi di valuta configurati

## Valori di configurazione non supportati

[!DNL Live Search] impossibile leggere tutti i valori di configurazione. Questa tabella elenca i valori che possono essere di maggiore interesse per gli sviluppatori.

| Impostazione configurazione Commerce | Note |
|---|---|
| Archivi > Configurazione > Catalogo > Storefront > Modalità elenco | Esegue correttamente il rendering, ma per alcune interazioni di pagina non vengono inviati eventi |
| Archivi > Configurazione > Catalogo > Catalogo > Ricerca nel catalogo > Lunghezza massima query | Non implementato; Search Services accetta fino a 255 caratteri |
| Configurazione > Vendite > Imposta > Impostazioni visualizzazione prezzo > Visualizza prezzi prodotto nel catalogo |  |
