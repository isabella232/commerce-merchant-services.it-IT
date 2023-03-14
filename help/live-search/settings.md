---
title: "[!DNL Live Search] Settings"
description: "Configurare intervalli e intervalli di facet di prezzo per [!DNL Live Search] facet."
exl-id: a0b63116-4b8f-490c-a54e-e21f1b02b634
source-git-commit: 9bacdb5fd232a3603bcb7abe2e93da9ead794d38
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Impostazioni

Utilizza il *Impostazioni* per configurare gli intervalli e gli intervalli del facet di prezzo disponibili come filtri di ricerca nella vetrina. Le impostazioni del facet di prezzo sono statiche anziché dinamiche e non si basano sui risultati della ricerca.

È possibile specificare il numero di gruppi di intervalli di prezzi e il modo in cui i valori di prezzo vengono distribuiti tra di essi. Ogni fascia di prezzo si sovrappone al gruppo precedente di uno. Ad esempio, cinque gruppi con un intervallo di venti creano le seguenti fasce di prezzo: 0-20, 20-40, 40-60, 60-80 e >80. Se il catalogo non contiene un numero di prodotti sufficiente per riempire tutti gli intervalli definiti, la visualizzazione dei gruppi disponibili viene regolata di conseguenza. Ad esempio: 0-20, 60-80, >80.

![Impostazioni](assets/settings.png)

## Configura raggruppamenti facet di prezzo

1. In Admin (Amministrazione), vai a **Marketing** > *SEO e ricerca* > **[!DNL Live Search]**.
1. Il giorno **Impostazioni** scheda in *Fatturazione del prezzo*, eseguire le operazioni seguenti:
   * Inserisci il **Numero di selezioni** o gruppi di prezzi. È possibile definire fino a 50 raggruppamenti di prezzi.
   * Inserisci il **Valore intervallo**, o fascia di prezzo per ciascun gruppo. Il valore massimo è 10.000.
1. Clic **Salva**.

   La disponibilità delle impostazioni aggiornate nella vetrina richiede circa 15 minuti.

## Descrizioni dei campi

| Campo | Descrizione |
|--- |--- |
| Numero di selezioni | Specifica il numero di raggruppamenti di intervalli di prezzi che possono essere utilizzati come filtri di ricerca nella vetrina. Valore predefinito: 8, valore massimo: 50 |
| Valore intervallo | Specifica l&#39;intervallo di prezzo per ogni gruppo. Ad esempio, cinque selezioni con un valore di intervallo di venti creano cinque raggruppamenti di 0-20, 20-40, 40-60, 60-80 e >80. Valore predefinito: 5, valore massimo: 10.000 |
