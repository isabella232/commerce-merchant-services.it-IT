---
title: "Verifica di [!DNL Quick Checkout] per estensione Adobe Commerce"
description: "La verifica e la convalida garantiscono che [!DNL Quick Checkout] l'estensione funziona come previsto."
exl-id: 308f39e1-e2f6-40d8-b876-0f9013effed3
feature: Checkout, Services
source-git-commit: b1984a26463e14b8dc9a789421e49e5ea81ad039
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 0%

---


# Testare [!DNL Quick Checkout] estensione

Prima di esporre [!DNL Quick Checkout] per l’estensione Adobe Commerce ai tuoi acquirenti, si consiglia di eseguire il test in un ambiente sandbox e nell’ambiente di produzione. I test e la convalida garantiscono che [!DNL Quick Checkout] funziona come previsto e offre un’esperienza di pagamento fluida per il tuo negozio e i tuoi clienti.

Prima di configurare [!DNL Quick Checkout] nell’amministratore di Adobe Commerce è necessario creare  [produzione](https://merchant.bolt.com/register){target="_blank"} and [sandbox](https://merchant-sandbox.bolt.com/register){target="_blank"} account esercente in [!DNL Bolt].

## Test in sandbox

Verifica di [!DNL Quick Checkout] in un ambiente sandbox è un passaggio di convalida molto importante, anche se si tratta di un ambiente simulato connesso solo al [!DNL Bolt] conto sandbox, non a banche o commercianti reali.

### Utilizzo dell’account sandbox

Quando verifichi e convalidi la sandbox, devi utilizzare un numero di carta di credito falso e un [sandbox](https://merchant-sandbox.bolt.com/register){target="_blank"} account esercente in [!DNL Bolt], in modo da non creare spese effettive per un account carta di credito esistente.

## Test in produzione

>[!NOTE]
>
> Si consiglia vivamente di verificare [!DNL Quick Checkout] in un ambiente di produzione, con carte di credito reali e banche, prima di esporre l&#39;estensione agli acquirenti. Anche se il test in sandbox è importante, il test in produzione è il metodo più stupido per assicurarne il funzionamento come previsto.

Esegui il test dell’ambiente di produzione in uno dei due modi consigliati:

- Scegli un momento in cui sai che nessun ordine verrà effettuato dagli acquirenti.
- Utilizza un archivio Web temporaneamente inaccessibile agli acquirenti, ma che è accessibile per i test.

Completa i test di produzione con carte di credito reali e [!DNL Bolt] gli account di produzione, testando l’intero ciclo di vita di un pagamento. Quando completi l&#39;intero flusso di pagamento durante il test, potrai avere un quadro chiaro di come funziona la tua funzionalità quando viene utilizzata dagli acquirenti.

È inoltre necessario verificare che le informazioni visualizzate nei rendiconti bancari per i metodi di pagamento utilizzati nei test di produzione siano corrette e previste (inclusa la descrizione della propria attività).

## Come verificare il [!DNL Quick Checkout] estensione

Completa il pagamento dal tuo Negozio:

1. Vai alla vetrina e inserisci gli articoli desiderati nel carrello.
1. Procedi con il pagamento.
1. Immetti un indirizzo e-mail associato a un [!DNL Bolt] quando richiesto.
1. Inserisci la password monouso (OTP) inviata all’indirizzo e-mail dell’account.
1. Seleziona il dashboard dell’ambiente:

   - Sandbox
   - Produzione

1. Effettua l’ordine.

Una volta effettuato un ordine, puoi visualizzare i dettagli degli ordini nel tuo _Griglia ordini_ visualizza:

1. Accedi a _Vendite_ > _Ordini_.
1. Consulta l’elenco di tutti gli ordini eseguiti.

Consulta la [Ordini](https://docs.magento.com/user-guide/sales/orders.html) per ulteriori informazioni sul _Griglia ordini_ visualizzazione.
