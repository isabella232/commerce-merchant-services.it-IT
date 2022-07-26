---
title: Test e convalida
description: Il test e la convalida garantiscono che [!DNL Payment Services] funziona come previsto e fornisce le migliori opzioni di pagamento per i clienti
exl-id: 95b4615e-73b0-41e8-83e2-e65a0b22f10f
source-git-commit: 41d93ffc2f9d518d9d4cf4abf2d53484821c13f2
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---

# Test e convalida

Prima di esporre [!DNL Payment Services] per [!DNL Adobe Commerce] e [!DNL Magento Open Source] per i tuoi clienti, è una buona idea testare nel tuo ambiente sandbox _e_ in produzione. Il test e la convalida garantiscono che [!DNL Payment Services] funziona come previsto e offre le migliori opzioni di pagamento per il tuo negozio e clienti.

## Test in ambiente sandbox

Test [!DNL Payment Services] in un ambiente sandbox è un importante passaggio di convalida, anche se si tratta di un ambiente simulato connesso solo alla sandbox PayPal, non a banche e commercianti reali.

1. Completa il pagamento dal tuo negozio con successo [Campi carta di credito](payments-options.md#credit-card-fields) o uno degli [Pulsanti avanzati PayPal](payments-options.md#paypal-smart-buttons). Vedi [Verifica delle credenziali](#testing-credentials) per ulteriori informazioni sull&#39;utilizzo di carte di credito false per i test.
1. Acquisisci (quando l&#39;azione di pagamento è [impostato su `Authorize and Capture`](onboard.md#set-payment-services-as-payment-method)), [rimborso](refunds.md)oppure [void](voids.md) l&#39;ordine appena completato. È inoltre possibile [creare una fattura](https://docs.magento.com/user-guide/sales/invoice-create.html){target=&quot;_blank&quot;} per un ordine, se l&#39;azione di pagamento è impostata su `Authorize` anziché `Authorize and Capture`.
1. Entro 24-48 ore, visualizzare la transazione e altre informazioni nel [Rapporto Pagamenti](payouts.md).
1. Vedi i dettagli dell&#39;ordine nel [Report stato del pagamento dell&#39;ordine](order-payment-status.md).

### Verifica delle credenziali

Quando si verifica e si convalida la sandbox è necessario utilizzare numeri di carta di credito falsi, in modo da non creare costi reali per un conto di carta di credito esistente.

Utilizza il generatore di carte di credito di PayPal per [generare informazioni casuali sulla carta di credito](https://www.paypal.com/us/smarthelp/article/where-can-i-find-test-credit-card-numbers-ts2157) per il test.

Per testare Apple Pay in modalità sandbox, è necessario disporre di un [Account sviluppatore Apple](https://developer.apple.com/programs/enroll/), completo di false carte di credito e informazioni di fatturazione.

>[!NOTE]
>
>L&#39;elaborazione del pagamento sandbox di PayPal a volte è lenta e il servizio può occasionalmente andare giù. Questa situazione non indica la rapidità e l&#39;efficienza del trattamento dei pagamenti per prodotti in diretta.

## Test in produzione

Si consiglia vivamente di eseguire il test [!DNL Payment Services] in produzione, con carte di credito reali e banche, prima di esporre questa funzionalità ai consumatori. Anche se testato [!DNL Payment Services] in sandbox è importante, il test in produzione è il metodo più a prova di inganno per garantire [!DNL Payment Services] funziona come previsto.

Puoi eseguire il test [!DNL Payment Services] in produzione in uno dei due modi seguenti:

* Scegli un momento in cui sai che nessun ordine sarà effettuato da acquirenti.
* Utilizza un negozio web temporaneamente inaccessibile agli acquirenti, ma accessibile per te per i test.

Completa i test di produzione con carte di credito reali e account PayPal, testando l&#39;intero ciclo di vita di un pagamento, compresi l&#39;acquisizione e il rimborso. Il completamento dell&#39;intero flusso di pagamento e di pagamento durante il test offre un quadro più chiaro di come [!DNL Payment Services] Questa funzionalità funzionerà quando gli acquirenti live la utilizzano.

È inoltre necessario verificare che le informazioni riportate nei rendiconti bancari relative ai metodi di pagamento utilizzati nei test di produzione siano corrette e attese (inclusa la descrizione della propria attività).

>[!NOTE]
>
>Per completare il test di produzione per Apple Pay è necessario contattare le vendite per abilitare Apple Pay per il tuo ambiente di produzione.
