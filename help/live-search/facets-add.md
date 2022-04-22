---
title: Aggiungi facet
description: Scopri come aggiungere attributi di prodotto filtrabili come facet Live Search.
exl-id: 0df6c21b-55b3-41ce-94f4-f70b70ffb84e
source-git-commit: f31c76404315a9fe142bf0c72ff9999c4a87365d
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 0%

---

# Aggiungi facet

Qualsiasi attributo di prodotto filtrabile può essere utilizzato come facet. La *Aggiungi facet* elenca i facet correnti e consente di assegnare facilmente attributi di prodotto aggiuntivi come facet. Durante questo processo in tre fasi, viene scelto un attributo da utilizzare come facet, le proprietà vengono modificate se necessario e le modifiche pubblicate nella vetrina.

![Area di lavoro di targeting](assets/facets-add.png)

## Passaggio 1: Aggiungi un facet

1. Nell&#39;Admin, vai a **Marketing** > SEO &amp; Search > **[!DNL Live Search]**.
1. Sulla *Facet* scheda , fai clic su **Aggiungi facet**.
1. In *Aggiungi facet* elenco, ogni attributo disponibile ha un *Aggiungi* pulsante . Effettua una delle seguenti operazioni:

   ![Facet aggiunto](assets/facets-list-add.png)

   * In *Attributi di facet* seleziona l’attributo di prodotto che desideri utilizzare come facet e fai clic su **Aggiungi**.
   * Per trovare un attributo di prodotto specifico, immetti i primi caratteri del nome dell’attributo nel *Ricerca* scatola. Quindi, fai clic su **Aggiungi**.

      Per configurare gli intervalli e i raggruppamenti di fattorizzazione dei prezzi, consulta [Impostazioni](settings.md). Per ulteriori informazioni, vai a [Tipi di facet](facets-type.md).
Il facet viene aggiunto nella parte inferiore del *Facet dinamici* e *Pubblicare le modifiche* diventa disponibile.
   ![Facet aggiunto](assets/facet-added.png)

1. Se il facet che desideri aggiungere non è disponibile, vai a **Negozi** > Attributi > **Prodotto** e verifica che l&#39;attributo abbia [proprietà richieste](facets.md) da utilizzare come facet. Se necessario, aggiorna le seguenti proprietà storefront dell&#39;attributo :

   * Usa nella ricerca - `Yes`
   * Usa nella navigazione a livelli dei risultati di ricerca - `Yes`
   * Utilizzo nella navigazione a livelli - `Filterable (with results)`

1. Quando richiesto, aggiorna la cache.

   Il facet diventa disponibile nella vetrina la prossima volta che il catalogo viene sincronizzato con [!DNL Live Search]. Se il facet non è disponibile dopo due ore, vedi [Sincronizzazione dei dati del catalogo](install.md#synchronize-catalog-data).

## Passaggio 2: Modifica proprietà facet (facoltativo)

1. Per modificare le proprietà del facet, fai clic su **Altro** (![Altro selettore](assets/btn-more.png)) nella colonna a destra.
1. Scegliere **Modifica**. Quindi, regola le seguenti proprietà in base alle esigenze.

   * Etichetta - ([Senza testa](facets-type.md) Solo) Immettere l&#39;etichetta del facet che si desidera utilizzare.
   * Seleziona tipo - Il *Seleziona tipo* utilizzato per tutti [!DNL Commerce] vetrine è `single select`. Per implementazioni headless, `multi-select` il tipo può essere assegnato con un operatore logico (`or` o `and`) per determinare il set di prodotti restituiti.
   * Tipo di ordinamento - I facet sono ordinati alfabeticamente per tutti [!DNL Commerce] vetrine. Per le implementazioni headless, i facet possono essere ordinati in ordine alfabetico o per conteggio. Opzioni: Alfabetico, conteggio (solo senza testa)
   * Valore massimo: immetti il numero massimo di valori di facet visualizzati nella vetrina. Voci valide: 0 - 30; Predefinito: 8

1. Al termine, fai clic su **Salva**.

   ![Area di lavoro di targeting](assets/facet-edit.png)

1. Per fissare il facet alla parte superiore del *Filtri* fare clic sulla puntina grigia (![Selettore pin](assets/btn-pin-gray.png)).
1. Per modificare l’ordine del facet bloccato, fai clic sul pulsante **Sposta** (![Selettore di spostamento](assets/btn-move.png)) e trascina la riga in una nuova posizione nel *Facet bloccate* sezione .

## Passaggio 3: Pubblicare le modifiche

1. Al termine del facet, fai clic su **Pubblicare le modifiche**.
1. Attendi che il facet venga visualizzato nel negozio.
Se il facet non è disponibile dopo due ore, vedi [Verifica esportazione](install.md#synchronize-catalog-data) nelle istruzioni di installazione.

## Descrizioni dei campi

| Campo | Descrizione |
|--- |--- |
| Etichetta | ([Senza testa](facets-type.md) Solo) [etichetta del facet](facets-type.md) che è visibile nella vetrina può essere modificato per coerenza con il tuo marchio. |
| Seleziona tipo | Visualizza la [metodo di selezione](facets-type.md) associato all’attributo del prodotto. Tutti i facet nel [!DNL Commerce] le vetrine sono `Single select` solo. Supporto anche delle implementazioni headless `Multi-select` con gli operatori logici `OR` e `AND`. |
| Tipo di ordinamento | Il metodo utilizzato per [sort](facets-type.md) sfaccettature. Tutto [!DNL Commerce] vetrine che ordinano facet solo alfabeticamente. Le implementazioni headless possono anche essere ordinate per `Count`. Opzioni:<br />Alfabetico - Ordina i facet in ordine alfabetico.<br />Conteggio - (solo senza intestazione) Ordina i facet in base al numero di corrispondenze trovate. |
| Valore massimo | Il numero massimo di valori che possono essere visualizzati nella vetrina per ciascun facet. I facet che rappresentano un intervallo di valori sono distribuiti in modo uniforme. Voci valide: 0 - 30; Predefinito: 8 |

### Controlli

| Controllo | Descrizione |
|--- |--- |
| ![Selettore pin](assets/btn-pin-blue.png) | Permette di unire o rimuovere una sfaccettatura nella parte superiore della *Filtri* elenco. |
| ![Altro selettore](assets/btn-more.png) | Visualizza un menu contenente altre azioni che possono essere applicate al facet selezionato. Opzioni: Modifica, Elimina |
| ![Selettore di spostamento](assets/btn-move.png) | Utilizza la *Sposta* icona per trascinare un facet bloccato in un’altra posizione *Facet bloccate* sezione . |
