---
title: '"Verifica [!DNL Quick Checkout] per estensione Adobe Commerce"'
description: '"La verifica e la convalida garantiscono che [!DNL Quick Checkout] l''estensione funziona come previsto."'
exl-id: 308f39e1-e2f6-40d8-b876-0f9013effed3
source-git-commit: 9841db7616c8aa6d5bc5af3e6e92c0abe9a4a1e2
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---


# Verificare la [!DNL Quick Checkout] estensione

Prima di esporre il [!DNL Quick Checkout] per l’estensione Adobe Commerce ai tuoi acquirenti, si consiglia di eseguire il test in un ambiente sandbox e nell’ambiente di produzione. La verifica e la convalida consentono di [!DNL Quick Checkout] funziona come previsto e offre un’esperienza di pagamento fluida per il tuo negozio e i tuoi clienti.

Prima di configurare le [!DNL Quick Checkout] nell’amministratore di Adobe Commerce è necessario creare  [produzione](https://merchant.bolt.com/register){target=&quot;_blank&quot;} e [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} account commerciali in [!DNL Bolt].

## Test in sandbox

Verifica [!DNL Quick Checkout] in un ambiente sandbox è un passaggio di convalida molto importante, anche se si tratta di un ambiente simulato connesso solo a [!DNL Bolt] conto sandbox, non a banche reali o commercianti.

### Utilizzo dell’account sandbox

Quando verifichi e convalidi la sandbox devi utilizzare un numero di carta di credito falso e un [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} account commerciale in [!DNL Bolt], in modo da non creare spese reali per un conto della carta di credito esistente.

## Test in produzione

>[!NOTE]
>
> Si consiglia vivamente di testare il [!DNL Quick Checkout] in un ambiente di produzione, con carte di credito reali e banche, prima di esporre l&#39;estensione ai consumatori. Anche se il test in sandbox è importante, il test in produzione è il metodo più a prova di inganno per garantire che funzioni come previsto.

Esegui il test dell’ambiente di produzione in uno dei due modi seguenti:

- Scegli un momento in cui sai che nessun ordine sarà effettuato da acquirenti.
- Utilizza un negozio web temporaneamente inaccessibile agli acquirenti, ma accessibile per te per i test.

Completa i test di produzione con carte di credito reali e [!DNL Bolt] account di produzione, verifica l&#39;intero ciclo di vita di un checkout. Quando completi l&#39;intero flusso di cassa durante i test, ti fornisce un quadro chiaro di come funziona la tua funzionalità quando gli acquirenti live la utilizzano.

È inoltre necessario verificare che le informazioni riportate nei rendiconti bancari relative ai metodi di pagamento utilizzati nei test di produzione siano corrette e attese (inclusa la descrizione della propria attività).

## Come verificare il [!DNL Quick Checkout] estensione

Completa il pagamento dal tuo negozio:

1. Vai alla vetrina e inserisci gli oggetti desiderati nel carrello.
2. Procedi al pagamento.
3. Immettere un indirizzo e-mail associato a un [!DNL Bolt] quando richiesto.
4. Inserisci la Password una tantum (OTP) inviata all’indirizzo e-mail dell’account.
5. Seleziona il dashboard dell’ambiente:

   - Sandbox
   - Produzione

6. Effettua l&#39;ordine.

Una volta effettuato un ordine, puoi visualizzare i dettagli dei tuoi ordini nel tuo _Griglia ordini_ visualizza:

1. Passa a _Vendite_ > _Ordini_.
1. Vedere elenco di tutti gli ordini inseriti.

Consulta la sezione [Ordini](https://docs.magento.com/user-guide/sales/orders.html) per ulteriori informazioni _Griglia ordini_ visualizza.
