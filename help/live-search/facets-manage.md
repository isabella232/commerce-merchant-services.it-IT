---
title: "Gestisci facet"
description: "Scopri come gestire gli [!DNL Live Search] facet."
exl-id: 1d51a36a-20d6-46b6-b379-11e46c8824a0
source-git-commit: 9bacdb5fd232a3603bcb7abe2e93da9ead794d38
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# Gestisci facet

Segui queste istruzioni per aggiornare le proprietà dei facet esistenti o modificarne la presentazione nella vetrina.

## Configura raggruppamenti facet di prezzo

Fai riferimento a [Impostazioni](settings.md) per configurare intervalli e raggruppamenti di price faceting.

## Modifica facet

1. Trovare il facet da modificare.
1. Se nell&#39;elenco sono presenti molti facet, impostare *Filtra per* a uno dei seguenti elementi:

   * Bloccato
   * Dinamico

   Per ulteriori informazioni, consulta [Tipi di facet](facets-type.md).

   ![Facet di filtro](assets/facets-filter-by-cropped.png)

1. Per modificare le proprietà del facet, fate clic su **Altro** (...) opzioni.
1. Clic **Modifica**

   ![Opzioni di modifica](assets/facet-edit-menu.png)

1. Per modificare l&#39;etichetta del facet, effettuate una delle seguenti operazioni:

   * Per un [!DNL Commerce] vetrina, modifica [etichetta attributo](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html).
   * Per un’implementazione headless, fai clic sul valore nella prima colonna e modifica il testo in base alle esigenze.

   ![Modifica etichetta](assets/facet-edit-label.png)

1. (Solo headless) Per modificare il metodo utilizzato per ordinare i valori dei facet, fai clic sul valore in *Tipo di ordinamento* e scegliere una delle seguenti opzioni:

   * Alfabetico
   * Conteggio

   ![Modifica conteggio](assets/facets-edit-count.png)

1. In **Valore massimo** , impostare il numero massimo (da 0 a 10) di valori di filtro facet da visualizzare nella vetrina.
1. Al termine, fai clic su **Salva**.
Le modifiche verranno visualizzate nella vetrina solo dopo la loro pubblicazione.

## Faccetta pin/spin

Quando si fa clic, il pin cambia colore e viene utilizzato per spostare il facet in una delle due opzioni *Facet bloccati* o *Facet dinamici* sezione.

1. Per fissare una sfaccettatura alla parte superiore del *Filtri* , trovare il facet in *Facet dinamici* e fare clic sul pin grigio (![Fissa selettore](assets/btn-pin-gray.png)).
Il perno diventa blu e la sfaccettatura si sposta verso *Facet bloccati* sezione.
1. Per sbloccare un facet, individuarlo in *Facet bloccati* e fare clic sul pin blu (![Fissa selettore](assets/btn-pin-blue.png)).
Il pin diventa grigio e la sfaccettatura si sposta verso *Facet dinamici* sezione.

   ![Facet bloccati e dinamici](assets/facets-pinned-unpinned.png)

## Sposta facet fissato

>[!NOTE]
>
>L’ordinamento dei facet bloccati è supportato solo nelle implementazioni headless. Se sono necessari facet ordinati, utilizza [!DNL Live Search] Widget PLP.

L&#39;ordine delle sfaccettature fissate può essere modificato spostando la riga in una posizione diversa. I facet bloccati hanno un *Sposta* icona (![Sposta selettore](assets/btn-move.png)) all&#39;inizio della riga. A differenza dei facet bloccati, i facet dinamici non possono essere spostati.

1. Trova il facet in *Facet bloccati* dell&#39;elenco.
1. Utilizza il **Sposta** (![Sposta selettore](assets/btn-move.png)) per trascinare la riga in una nuova posizione nella *Facet bloccati* sezione.
Dopo la pubblicazione delle modifiche, i facet riordinati vengono visualizzati nella vetrina *Filtri* elenco.

## Elimina facet

1. Trova il facet nell’elenco e fai clic su **Altro** (...) opzioni.
1. Clic **Elimina**.
1. Quando viene richiesto di confermare, fai clic su **Elimina facet**.
Il facet viene rimosso dalla vetrina dopo la pubblicazione delle modifiche.

## Pubblica modifiche

1. Per aggiornare la vetrina con le modifiche apportate, fai clic su **Pubblica modifiche**.
1. Attendi circa 15 minuti prima che gli aggiornamenti vengano visualizzati nel tuo store.
