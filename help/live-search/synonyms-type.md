---
title: "Tipi di sinonimi"
description: "unidirezionale e bidirezionale [!DNL Live Search] i sinonimi espandono la definizione di parole chiave."
exl-id: 708d7b0d-7361-44f4-ae9e-b92f574ac975
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Tipi di sinonimi

I sinonimi unidirezionali e bidirezionali espandono la definizione di parole chiave. Alcuni sono intercambiabili con la parola chiave, mentre altri rappresentano un sottoinsieme della parola chiave.

## A due vie

I sinonimi bidirezionali hanno lo stesso significato e restituiscono gli stessi risultati di ricerca. Nell’esempio seguente, la prima parola in grassetto è la parola chiave utilizzata nel catalogo, seguita da parole che hanno lo stesso significato della parola chiave originale. È possibile creare una coppia semplice di sinonimi a due vie o una catena di più sinonimi a due vie per la stessa parola chiave.

**giacca** ![Selettore bidirezionale](assets/btn-two-way.png) cappotto
**pantaloni** ![Selettore bidirezionale](assets/btn-two-way.png) baracca ![Selettore bidirezionale](assets/btn-two-way.png) pantaloni

## unidirezionale

Un sinonimo di senso unico è un sottoinsieme di una parola chiave, ma con un significato più specifico. Per esempio, capris e pantaloncini sono pantaloni, ma non tutti i pantaloni sono di capris o pantaloncini. Una ricerca di pantaloni include capris e pantaloncini. Tuttavia, una ricerca per i pantaloncini non restituisce i capri.

**felpa** ![Selettore unidirezionale](assets/btn-one-way.png) felpa
**pantaloni** ![Selettore unidirezionale](assets/btn-one-way.png) caprioli ![Selettore multiplo unidirezionale](assets/btn-multiple-one-way.png) pantaloni a base di vitello ![Selettore multiplo unidirezionale](assets/btn-multiple-one-way.png) pedalò

## Best practice

Tieni presente le seguenti best practice per ottenere il massimo dai sinonimi di Live Search.

### Evitare &quot;stop words&quot;

Live Search filtra le comuni &quot;parole di stop&quot; inglesi dai sinonimi, come:

a, an, e, sono, come, at, be, ma, per, per, se, in, in, è, è, no, non, di, on, o, tale, il, loro, allora, là, questi, loro, questo, a, era, volontà, con

Le parole di arresto non rendono i sinonimi più significativi, ma aumentano la quantità di dati da elaborare.

### Usa parole singole

Se un termine sinonimo contiene più parole, lo spazio vuoto tra le parole le fa sì che siano trattate come sinonimi separati. Ad esempio, se definisci &quot;tempo&quot; come sinonimo di &quot;orologio&quot;, le parole &quot;tempo&quot; e &quot;pezzo&quot; vengono trattate come sinonimi separati.

### Uso del singolare e plurale

Non è necessario definire sia le forme singolari che plurali di una parola come sinonimo. Se nel catalogo è presente una combinazione di termini singolari e plurali, Ricerca trova il set corretto di prodotti. Ad esempio, se utilizzi la parola &quot;pant&quot; nel nome del prodotto e un acquirente cerca &quot;pantaloni&quot;, viene restituito il set corretto di prodotti e viene offerta come suggerimento la singola parola &quot;pant&quot;. Il termine singolare &quot;pant&quot; è spesso utilizzato nell&#39;industria della moda e a volte nel commercio al dettaglio, anche se la forma plurale &quot;pantaloni&quot; è più comunemente utilizzato in alcune aree. (La parola &quot;pant&quot; tecnicamente si riferisce alla parte di un indumento che copre una gamba, che è il motivo per cui hai bisogno di un &quot;paio di pantaloni&quot; per coprire entrambe le gambe.)

### Coerenza

Assicurati di essere coerente con il modo in cui la terminologia viene utilizzata nel catalogo. Tieni presente che potrebbero esserci differenze di utilizzo a livello regionale e talvolta anche all’interno di un settore.

### Mappatura delle parole chiave

Questa tecnica utilizza attributi di prodotto ricercabili, anziché sinonimi, per creare associazioni basate su parole chiave tra i prodotti. Di conseguenza, un prodotto mappato può essere visualizzato nei risultati di ricerca di un altro prodotto. Per ulteriori informazioni, consulta [Risultati ricerca](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-results.html).
