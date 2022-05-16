---
title: '"Aggiungi sinonimi"'
description: '"Aggiungi [!DNL Live Search] sinonimi per migliorare la risposta alle richieste di ricerca."'
exl-id: 6c277d88-cb22-4174-abda-6d6bb65fe3be
source-git-commit: bffbede99865e9085f60392e474065a454446370
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Aggiungi sinonimi

Aumenta il coinvolgimento dei clienti aggiungendo il tuo elenco curato dei sinonimi di Live Search. [!DNL Live Search] può gestire fino a 200 sinonimi per `Data Space ID`.

![[!DNL Live Search] sinonimi](assets/synonym-workspace.png)

## Passaggio 1: Aggiungi un sinonimo

1. Nell&#39;Admin, vai a **Marketing** > SEO &amp; Search > **[!DNL Live Search]**.
1. Per più negozi, impostare **Ambito** al [vista store](https://docs.magento.com/user-guide/configuration/scope.html) dove si applicano le impostazioni sinonimo.
1. Fai clic sul pulsante **Sinonimi** scheda .
1. Fai clic sul pulsante **Aggiungi sinonimi** pulsante .

## Passaggio 2: Definire il sinonimo per tipo

Segui le istruzioni per [tipo di sinonimo](synonyms-type.md) che desideri creare.

### sinonimo di doppio senso

1. Accetta il valore predefinito **A due vie** opzione .

   ![Aggiungi sinonimo di bidirezionale](assets/synonym-add-two-way.png)


1. Inserisci il **Parola chiave** termine o frase da abbinare.
1. Inserisci il **Espansione** termini che si desidera aggiungere come sinonimi della parola chiave. Separa più termini con una virgola.
In questo esempio, la parola chiave da abbinare è &quot;pantaloni&quot; e l&#39;insieme di termini di espansione sono &quot;pantaloni lunghi, pantaloni, slack&quot;.

   ![Esempio di sinonimo a due vie](assets/synonym-add-two-way-example.png)

1. Al termine, fai clic su **Salva**.
L&#39;insieme dei sinonimi viene visualizzato nell&#39;elenco con una freccia bidirezionale tra ciascun termine, il che significa che i termini sono intercambiabili.

   ![sinonimo di doppio senso](assets/synonym-two-way.png)

### sinonimo di unidirezionale

1. Fai clic sul pulsante **unidirezionale** tipo sinonimo.

   ![Aggiungi sinonimo di unidirezionale](assets/synonym-add-one-way.png)

1. Inserisci il **Parola chiave** e **Espansione** termini. Separa più termini con una virgola.

   ![Esempio di sinonimo di unidirezionale](assets/synonym-add-one-way-example.png)

   In questo esempio, la parola chiave è &quot;pantaloni&quot; e i termini di espansione a senso unico &quot;capris, pantaloni a lunghezza di vitello, peddle-pushers&quot; sono tutti un sottoinsieme di &quot;pantaloni&quot;, ma con un significato specifico.

1. Al termine, fai clic su **Salva**.
L&#39;insieme dei sinonimi viene visualizzato nell&#39;elenco con una freccia a senso unico che punta dai termini di espansione alla parola chiave per indicare che i termini sono sottoinsiemi della parola chiave. Un segno più separa ogni termine di espansione.

   ![sinonimo di unidirezionale](assets/synonym-one-way.png)

## Passaggio 3: Pubblicare le modifiche

1. Al termine dei sinonimi, fai clic su **Pubblicare le modifiche**.
1. Attendi fino a due ore perché gli aggiornamenti siano disponibili nella vetrina.

![Pubblicare le modifiche](assets/synonym-publish.png)

## Descrizioni campo

| Campo | Descrizione |
|--- |--- |
| [Tipo](synonyms.md) | Determina se i sinonimi hanno lo stesso significato della parola chiave o sono un sottoinsieme della parola chiave. Opzioni:<br />Due modi (predefinito) - Termini che hanno lo stesso significato della parola chiave e restituiscono gli stessi risultati di ricerca<br />Solo andata - Termini che sono un sottoinsieme della parola chiave. I sinonimi unidirezionali restituiscono un elenco più ristretto di prodotti specifici. |
| Parola chiave | Parola comunemente associata a una selezione di prodotti nel catalogo. |
| Espansione | Altri termini che hanno lo stesso significato o lo stesso significato della parola chiave. |
