---
title: "Regole"
description: "[!DNL Live Search] le regole combinano logica e azioni per modellare l’esperienza di acquisto."
exl-id: d06a3040-6987-4813-90ae-2f7b3ad0b232
source-git-commit: 941fdc25f93679593cb3c5db0d29d7a561fcce58
workflow-type: tm+mt
source-wordcount: '296'
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
