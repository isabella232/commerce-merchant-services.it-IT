---
title: '"Componenti della regola"'
description: '"Scopri di più [!DNL Live Search] componenti e operatori di regole."'
exl-id: 4065aec3-a8d4-4d55-b939-16ad7b0f33ee
source-git-commit: bffbede99865e9085f60392e474065a454446370
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Componenti della regola

Una regola descrive le condizioni necessarie per attivare gli eventi che modificano i risultati della ricerca restituiti in risposta alla query di un acquirente.

## Requisiti

Una regola semplice può avere una singola condizione e un singolo evento, mentre una regola complessa può avere fino a dieci condizioni che attivano fino a venticinque eventi.
Le regole possono avere:

* Fino a 10 condizioni
* Fino a 25 eventi

Il testo della query può contenere:

* Caratteri alfanumerici (lettere e numeri)
* Caratteri maiuscoli o minuscoli

## Operatori logici

Operatori logici `AND` e `OR` unire due condizioni e restituire risultati diversi. Tutti gli operatori logici utilizzati in una regola con più condizioni sono gli stessi. Non è possibile utilizzare entrambi `AND` e `OR` nella stessa regola.

### Operatori di corrispondenza

Operatori di corrispondenza `All` e `Any` determina l’operatore logico utilizzato per unire più condizioni nella regola e può essere utilizzato per modificare l’operatore esistente.

* `All` - Utilizza il `AND` operatore logico per unire più condizioni. Una regola che utilizza il `All` L’operatore di corrispondenza può avere un solo operatore `Search query is` condizione.
* `Any` - Utilizza il `OR` operatore logico per unire più condizioni.

Quando si compone una regola complessa, può essere utile scriverla con un rientro per descrivere le condizioni, gli eventi associati e i nomi di prodotto o gli SKU necessari per restituire i risultati desiderati. Quindi, crea la regola e verifica il risultato.
