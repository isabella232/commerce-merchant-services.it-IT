---
title: '"Impostazioni delle configurazioni Commerce e [!DNL Live Search] '''
description: Descrive le impostazioni di configurazione di Adobe Commerce che [!DNL Live Search] può leggere.
exl-id: a4e9e2dd-e912-4ced-a44a-091ac5334e50
source-git-commit: 368059d50133d8b01be83e1616044a61ab094e3c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# [!DNL Live Search] e Adobe Commerce Configuration Settings

Alcune impostazioni di configurazione di Commerce [!DNL Live Search] supporta. In questo argomento sono elencati questi valori di configurazione.

## Valori di configurazione supportati

| Impostazione configurazione Commerce | Supportato da Popover | Supportato dall&#39;adattatore |
|---|---|---|
| Archivi -> Configurazione -> Catalogo -> Catalogo -> Ricerca catalogo -> Lunghezza minima query | Sì | Sì |
| Negozi -> Configurazione -> Catalogo -> Inventario -> Visualizzazione prodotti esauriti | Sì con v2.0.4+ | Sì con v2.0.4+ |
| Archivi -> Configurazione -> Generale -> Impostazione valuta -> Opzioni valuta -> Valuta di base | Sì | Sì |

## Valori di configurazione non supportati

[!DNL Live Search] impossibile leggere tutti i valori di configurazione. Questa tabella elenca i valori che possono essere di maggiore interesse per gli sviluppatori.

| Impostazione configurazione Magento | Note |
|---|---|
| Archivi -> Configurazione -> Catalogo -> Vetrina -> Modalità elenco | Esegue correttamente il rendering, ma per alcune interazioni di pagina non vengono inviati eventi |
| Archivi -> Configurazione -> Catalogo -> Vetrina -> Consenti tutti i prodotti per pagina | Non implementato; invia la richiesta al servizio di ricerca senza dimensione pagina e [!DNL Live Search] restituisce una dimensione pagina predefinita di 20 |
| Archivi -> Configurazione -> Catalogo -> Catalogo -> Ricerca catalogo -> Lunghezza massima query | Non implementato; Search Services accetta fino a 255 caratteri |
| Archivi -> Configurazione -> Generale -> Impostazione valuta -> Opzioni valuta -> Valuta di visualizzazione predefinita | Non attuato; [!DNL Live Search] ha accesso solo alla valuta di base |
| Configurazione -> Vendite -> Imposta -> Impostazioni Visualizzazione Prezzo -> Visualizza Prezzi Prodotto Nel Catalogo |  |
