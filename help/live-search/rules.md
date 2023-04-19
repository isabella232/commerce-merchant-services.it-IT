---
title: "Regole"
description: "[!DNL Live Search] le regole combinano logica e azioni per modellare l’esperienza di acquisto."
exl-id: d06a3040-6987-4813-90ae-2f7b3ad0b232
source-git-commit: 7307702a62a6b2c3e6c6083a59f2ac3587b0985e
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 0%

---

# Regole

[!DNL Live Search] le regole combinano la logica con le azioni per modellare l’esperienza di ricerca di un acquirente nel tuo negozio. Puoi utilizzare le regole per incrementare, seppellire, fissare o nascondere i prodotti per calibrare i risultati della ricerca in tempo reale per supportare i tuoi obiettivi aziendali.

Ogni regola ha tre componenti principali:

* Condizioni: le condizioni che attivano un’azione.
* Eventi : le azioni che hanno luogo quando le condizioni sono soddisfatte.
* Dettagli: nome della regola, intervallo di tempo facoltativo e descrizione.

È possibile combinare più condizioni e azioni e pianificare una regola per essere attiva per un periodo.

## Requisiti

Una regola semplice può avere una singola condizione e un singolo evento, mentre una regola complessa può avere fino a dieci condizioni che attivano fino a 25 eventi.
Le regole possono avere:

* Fino a dieci condizioni
* Fino a 25 eventi

Il testo della query può contenere:

* Caratteri alfanumerici (lettere e numeri)
* Caratteri maiuscoli o minuscoli. La capitalizzazione viene ignorata.

## Operatori logici

Operatori logici `AND` e `OR` unire due condizioni e restituire risultati diversi. Tutti gli operatori logici utilizzati in una regola con più condizioni sono gli stessi. Non è possibile utilizzare entrambi `AND` e `OR` nella stessa regola.

### Operatori di corrispondenza

Operatori di corrispondenza `All` e `Any` determina l’operatore logico utilizzato per unire più condizioni nella regola e può essere utilizzato per modificare l’operatore esistente.

* `All` - Utilizza il `AND` operatore logico per unire più condizioni. Una regola che utilizza il `All` L’operatore di corrispondenza può avere un solo operatore `Search query is` condizione.
* `Any` - Utilizza il `OR` operatore logico per unire più condizioni.

Quando si compone una regola complessa, può essere utile scriverla con un rientro per descrivere le condizioni, gli eventi associati e i nomi di prodotto o gli SKU necessari per restituire i risultati desiderati. Quindi, crea la regola e verifica il risultato.

## Ordine di precedenza con più regole

A un termine di ricerca viene applicata una sola regola alla volta.
Se si riscontrano più regole applicabili a una frase di ricerca, vengono applicate tutte queste regole. In caso di conflitto tra due regole—`rule 1` che aumenta sku1 ma `rule 2` nasconde la stessa SKU, quindi la regola applicata più di recente (`rule 2`) ha la precedenza.

* Le regole sono ordinate dalla marca temporale &quot;Ultima modifica&quot;. La regola modificata più di recente viene applicata per prima, e le regole precedenti dopo di essa, in ordine di marca temporale.
* La `query is` la condizione ha la precedenza rispetto alle altre condizioni. Se una regola più recente contiene un `query contains` ma una regola precedente ha una `query is` la condizione `query is` viene applicata la regola.

### Richieste Storefront

Se una regola attiva contiene un `query is` La condizione corrisponde alla frase di ricerca, viene applicata. Se sono presenti più regole di corrispondenza con un `query is` viene applicata la regola attiva aggiornata più di recente.
In caso contrario, viene applicata la regola attiva aggiornata più di recente.

### Richieste di anteprima

La richiesta effettuata nell&#39;amministratore funziona in modo leggermente diverso. Quando visualizzi l’anteprima in Admin, vengono applicate tutte le regole, incluse quelle scadute e pianificate.

* Se la regola viene visualizzata in anteprima ha un `query is` viene applicata.
* Se la regola visualizzata in anteprima non ha un `query is` e una successiva regola di corrispondenza attiva con un `query is` la condizione viene trovata, `query is` viene applicata la regola.
* Se la regola visualizzata in anteprima non ha un `query is` e nessun&#39;altra regola con un `query is` viene trovata, quindi viene applicata la regola in anteprima.

## Regole di categoria e assegnazioni di prodotti di categoria

[!DNL Live Search] consente di filtrare per categorie.
Tuttavia, in Adobe Commerce puoi creare una categoria virtuale con [Assegnazione di prodotti per categorie](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/products-in-category/categories-product-assignments.html). Questo tipo di categoria è generato in fase di esecuzione e non esiste nel database delle categorie. Pertanto, [!DNL Live Search] impossibile leggere o utilizzare questo tipo di categoria.
