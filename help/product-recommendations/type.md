---
title: Tipi di consigli
description: Scopri i consigli che puoi distribuire in varie pagine del sito.
exl-id: c3b16307-479b-4736-968b-b6ab38233a48
source-git-commit: 42cb709f4699fcdd56df7ca02466ab416f01cab2
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 0%

---

# Tipi di consigli

Adobe Commerce fornisce un’ampia serie di consigli che puoi distribuire su varie pagine del sito. Tutti i tipi di consigli sono basati sui dati. Sono basati su dati comportamentali, dati di attributi di prodotto e metriche. Per facilitare la consultazione, i tipi di consigli sono raggruppati come segue:

- [Personalizzato](#personalized)
- [Cross-selling e up-sell](#crossup)
- [Popolarità](#popularity)
- [Prestazioni elevate](#highperf)

Come best practice, l’Adobe consiglia le seguenti linee guida nell’utilizzo dei consigli:

- Diversifica i tipi di consigli. I clienti iniziano a ignorare i consigli se suggeriscono di volta in volta gli stessi prodotti.

- Non distribuire gli stessi consigli nella pagina del carrello e nella pagina di conferma dell’ordine. Valuta l’utilizzo di `Most Added to Cart` per la pagina del carrello e `Bought This, Bought That` per la pagina di conferma dell’ordine.

- Mantieni il tuo sito ordinato. Non distribuire più di tre unità di consigli sulla stessa pagina.

- Se il tuo negozio vende vestiti, il `More like this` la raccomandazione può suggerire prodotti specifici per genere che non corrispondono al genere del prodotto visualizzato. Prendi in considerazione l’utilizzo di questo tipo di consigli solo per categorie non di abbigliamento.

## Personalizzato {#personalized}

Questi tipi di consigli consigliano prodotti in base alla cronologia comportamentale dell’acquirente specifica sul tuo sito.

| Tipo | Descrizione |
|---|---|
| Consigliato per te | Consiglia i prodotti in base al comportamento corrente e precedente di ogni cliente. Mostra consigli molto rilevanti in base alla cronologia di navigazione e di acquisto del cliente. Questo tipo di consiglio è valido nella home page in cui la maggior parte degli acquirenti inizia il percorso su un sito. Per i nuovi acquirenti sul tuo sito che non hanno generato alcun segnale per personalizzare la loro esperienza, Adobe Commerce mostra i prodotti in base al tipo di consiglio Più visualizzato. Tuttavia, quando il cliente inizia a interagire con i prodotti sul sito, i prodotti consigliati si adattano in tempo reale al loro comportamento.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria <br/><br/>**Etichette consigliate:**<br/> - Solo per te<br/>- Consigliato per te<br/>- Ideato dalle tendenze di acquisto |
| Visualizzato di recente | Visualizza gli ultimi prodotti visualizzati dall’acquirente, in base alla cronologia del browser. Eventuali prodotti eliminati vengono rimossi dall’unità di consigli. L’unità di consigli non viene visualizzata se non è presente alcuna cronologia del browser o se la cronologia non è sufficiente quando vengono applicate le regole del filtro. Se i risultati contengono meno prodotti di quelli configurati, l’unità di consigli visualizza solo i prodotti restituiti.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/>- Visualizzato di recente<br/>- Dai un&#39;altra occhiata |

## Cross-selling e up-sell {#crossup}

Questi tipi di consigli sono orientati alla protezione dai social network per aiutare gli acquirenti a trovare ciò che piace ad altri o i prodotti per aiutarli a trovare altri prodotti simili

| Tipo | Descrizione |
|---|---|
| Ha visualizzato questo, ha visualizzato quello | Consiglia i prodotti che gli acquirenti visualizzano con maggiore frequenza rispetto al prodotto attualmente visualizzato.<br/><br/>**Se utilizzato:**<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/>- I clienti che hanno visualizzato questo prodotto hanno anche visualizzato (PDP) |
| Ho visto questo, ho comprato quello | Consiglia i prodotti che gli acquirenti tendono ad acquistare in modo sproporzionato più spesso dopo aver visualizzato il prodotto corrente. Aiuta gli acquirenti a scoprire prodotti che altrimenti non avrebbero notato.<br/><br/>**Se utilizzato:**<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/>- Clienti che hanno visto questo acquisto finale<br/>- Acquisto finale da parte dei clienti<br/>- Cosa acquistano gli altri dopo aver visualizzato questo prodotto? |
| Ho comprato questo e quello | Consiglia i prodotti che gli acquirenti acquistano con maggiore frequenza rispetto al prodotto attualmente visualizzato. Utilizzato più spesso nel carrello o nella pagina dei dettagli del prodotto per aumentare l’esposizione del prodotto di cross-selling correlato per aumentare il valore medio dell’ordine. Visualizza prodotti di grande rilevanza che gli acquirenti possono aggiungere al carrello aggregando ciò che altri acquirenti hanno acquistato con il prodotto corrente.<br/><br/>**Se utilizzato:**<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/>- Ottenere tutto ciò che serve<br/>- Non dimenticare questi<br/>- Acquistato spesso insieme |
| Altri argomenti correlati | Consiglia prodotti basati su metadati simili, ad esempio nome, descrizione, assegnazione di categorie e attributi. Valutando gli attributi dei prodotti visualizzati, consiglia prodotti simili nella stessa categoria. Ad esempio, se un acquirente sta navigando tra i tappetini da yoga, si consigliano altri prodotti nella categoria attrezzatura. Poiché questo tipo di consiglio non distingue i sessi, non è consigliato per abbigliamento, moda o altri verticali specifici per genere.<br/><br/>**Se utilizzato:**<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/> - Altri prodotti come questo<br/>- Simile a questo |
| [Somiglianza visiva](#visualsim) | Consiglia prodotti dall’aspetto simile al prodotto visualizzato. Questo tipo di consiglio è più utile se le immagini e gli aspetti visivi dei prodotti sono importanti per l’esperienza di acquisto. |

## Popolarità {#popularity}

Questi tipi di consigli consigliano prodotti che sono i più popolari o di tendenza negli ultimi sette giorni.

| Tipo | Descrizione |
|---|---|
| Articoli più visualizzati | Consiglia i prodotti più visualizzati contando il numero di sessioni in cui si è verificata un’azione di visualizzazione negli ultimi sette giorni.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/>- Più popolari<br/>- Di tendenza<br/>- Popolari al momento<br/>- Di recente popolari<br/>- Prodotti popolari ispirati da questo prodotto (PDP)<br/>- Articoli più venduti |
| Più acquistati | Consiglia i prodotti acquistati più di frequente dagli acquirenti negli ultimi sette giorni.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/> - Più popolari<br/>- Di tendenza<br/>- Popolari al momento<br/>- Di recente popolari<br/>- Prodotti popolari ispirati da questo prodotto (PDP)<br/>- Articoli più venduti |
| Più aggiunti al carrello | Consiglia i prodotti aggiunti più frequentemente ai carrelli dagli acquirenti negli ultimi sette giorni. Questo tipo di consiglio può essere utilizzato su tutte le pagine.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/> - Più popolari<br/>- Di tendenza<br/>- Popolari al momento<br/>- Di recente popolari<br/>- Prodotti popolari ispirati da questo prodotto (PDP)<br/>- Articoli più venduti |
| Di tendenza | Consiglia i prodotti in base al recente impulso di popolarità di un prodotto nel tuo sito.<br/><br/>Adobe Sensei aggrega i dati di navigazione e di acquisto nel tuo sito per determinare e classificare quali prodotti sono più di recente popolari tra gli acquirenti. Dato che Trending analizza il recente slancio dei prodotti, è un tipo di raccomandazione efficace per i cataloghi che hanno un fatturato elevato. Se il catalogo è più statico, potrebbe non essere utile a meno che i modelli di acquisto del pubblico non siano altamente variabili.<br/><br/>Quando viene utilizzato nella pagina Home, Trending consiglia prodotti che sono stati recentemente popolari in tutto il sito. La tendenza non mostra i prodotti che sono costantemente popolari, ma piuttosto quelli che sono diventati di recente popolari. Ad esempio, in presenza di una campagna di marketing e-mail che promuove determinati prodotti, l’aumento di popolarità generato dall’e-mail aumenta la probabilità che i prodotti promossi siano classificati come di tendenza.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/>- Di tendenza<br/>- Di tendenza<br/>- Di tendenza recente<br/>- Prodotti caldi<br/>- Prodotti correlati di tendenza (PDP) |

## Prestazioni elevate {#highperf}

Questi tipi di consigli consigliano prodotti con le prestazioni migliori in base a criteri di successo come l’aggiunta al carrello o i tassi di conversione.

| Tipo | Descrizione |
|---|---|
| Visualizza per conversione acquisto | Consiglia prodotti con il più alto tasso di conversione visualizzazione-acquisto. Di tutte le sessioni cliente che hanno registrato una visualizzazione di prodotto, qual è la proporzione che alla fine ha registrato un acquisto da parte del cliente.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/> -Più venduti<br/>- Prodotti più diffusi<br/>- Potrebbe interessarti |
| Conversione da Vista a Carrello | Consiglia i prodotti con il più alto tasso di conversione da vista a carrello. Di tutte le sessioni cliente che hanno registrato una visualizzazione di prodotto, qual è la proporzione che alla fine ha registrato e aggiunto al carrello da parte del cliente.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/> - Articoli più venduti<br/>- Prodotti più diffusi<br/>- Potrebbe interessarti |
| Più acquistati | Spesso definito &quot;Più venduti&quot;, questo tipo di consiglio conta il numero di sessioni in cui si è verificata un’azione di ordine negli ultimi sette giorni. Questo tipo di consiglio può essere utilizzato su tutte le pagine.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/> - Più popolari<br/>- Di tendenza<br/>- Popolari al momento<br/>- Di recente popolari<br/>- Prodotti popolari ispirati da questo prodotto (PDP)<br/>- Articoli più venduti |
| Più aggiunti al carrello | Consiglia i prodotti aggiunti più frequentemente ai carrelli dagli acquirenti negli ultimi sette giorni. Questo tipo di consiglio può essere utilizzato su tutte le pagine.<br/><br/>**Se utilizzato:**<br/>- Home page<br/>- Categoria<br/>- Dettagli del prodotto<br/>- Carrello<br/>- Conferma <br/><br/>**Etichette consigliate:**<br/> - Più popolari<br/>- Di tendenza<br/>- Popolari al momento<br/>- Di recente popolari<br/>- Prodotti popolari ispirati da questo prodotto (PDP)<br/>- Articoli più venduti |

## Somiglianza visiva {#visualsim}

Il _Somiglianza visiva_ il tipo di consiglio consiglia prodotti dall’aspetto simile al prodotto visualizzato. Questo tipo di consigli è più utile quando le immagini e gli aspetti visivi dei prodotti sono parti importanti dell’esperienza di acquisto.

### Come funziona

Il _Somiglianza visiva_ tipo di consiglio offre consigli per altri prodotti nel catalogo che hanno una somiglianza visiva con le immagini attualmente visualizzate. La somiglianza visiva include aspetti quali:

- Colore
- Forma
- Dimensione
- Texture
- Materiale
- Stile

Adobe Sensei utilizza l’intelligenza artificiale per elaborare e analizzare le immagini nel catalogo e creare gli attributi utilizzati per determinare le somiglianze visive.

>[!NOTE]
>
> Se stai sottoponendo a test questo tipo di consigli in un ambiente non di produzione, assicurati che gli URL delle immagini siano accessibili al pubblico.

>[!NOTE]
>
> Attualmente, le immagini del prodotto devono avere dimensioni pari o inferiori a 10 MB.

Poiché questo tipo di consiglio non è applicabile alla maggior parte dei cataloghi, non è abilitato per impostazione predefinita. Devi abilitare esplicitamente questo tipo di consigli.

### Abilita tipo di consiglio per somiglianza visiva

>[!NOTE]
>
> Il _Somiglianza visiva_ il tipo di consiglio è disponibile quando [installare](install-configure.md) come modulo opzionale.

1. Il giorno _Amministratore_ barra laterale, vai a **Marketing** > _Promozioni_ > **Recommendations del prodotto** per visualizzare _Recommendations del prodotto_ dashboard.

1. Clic **Impostazioni** (icona ingranaggio) per visualizzare _Impostazioni_ pagina.

1. In _Visual Recommendations_ sezione, seleziona per **Abilita Visual Recommendations**.

1. Clic **Salva modifiche** quando hai finito.

   Il [Crea nuovo consiglio](create.md) ora viene visualizzata la pagina **Somiglianza visiva** come tipo di consiglio selezionabile quando il tipo di pagina è **Dettagli prodotto**.

Dopo aver abilitato i consigli visivi, Adobe Sensei avvia l’elaborazione dell’immagine. Il tempo necessario dipende dalle dimensioni del catalogo.

### Dove usato

- Dettagli del prodotto

### Etichette consigliate per la vetrina

- Ti potrebbe piacere
- Abbiamo trovato altri prodotti che potresti apprezzare
- Ispirato da questo stile

### Esempio

L’immagine seguente mostra la pagina dei dettagli del prodotto per _Orologio a quadretti_:

![Orologio a quadretti](assets/visual-sim-pdp.png)

Di seguito sono riportati i _Somiglianza visiva_ unità di consigli per _Orologio a quadretti_:

![Unità di somiglianza visiva](assets/visual-sim-unit.png)
