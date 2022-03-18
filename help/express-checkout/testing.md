---
title: Verifica [!DNL Express Checkout] per estensione Adobe Commerce
description: La verifica e la convalida garantiscono che [!DNL Express Checkout] l'estensione funziona come previsto.
exl-id: 308f39e1-e2f6-40d8-b876-0f9013effed3
source-git-commit: d8302d2d652b4e2380cc862183e58cbd2cca831b
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# Verifica [!DNL Express Checkout] per estensione Adobe Commerce

>[!IMPORTANT]
>
> Questa funzione è disponibile solo per gli utenti del programma Early Adopter (EAP) e non è ancora accessibile per tutti i clienti. Attualmente limitato ai clienti statunitensi. Per assistenza e domande, contatta il supporto Adobe Commerce.

Prima di esporre il [!DNL Express Checkout] per l’estensione Adobe Commerce ai tuoi acquirenti, si consiglia di eseguire il test in un ambiente sandbox e nell’ambiente di produzione. La verifica e la convalida consentono di [!DNL Express Checkout] funziona come previsto e offre un’esperienza di pagamento fluida per il tuo negozio e i tuoi clienti.

Prima di configurare le [!DNL Express Checkout] nell’amministratore di Adobe Commerce è necessario creare un [produzione](https://merchant.bolt.com/register){target=&quot;_blank&quot;} e [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} account commerciale in Bolt.

## Test in sandbox

Verifica [!DNL Express Checkout] in un ambiente sandbox è un passaggio di convalida molto importante, anche se si tratta di un ambiente simulato connesso solo al conto sandbox Bolt, non a banche o commercianti reali.

### Utilizzo dell’account sandbox

Quando verifichi e convalidi la sandbox devi utilizzare un numero di carta di credito falso e un [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} account mercante in Bolt, in modo da non creare costi reali per un conto della carta di credito esistente.

## Test in produzione

>[!NOTE]
>
> Si consiglia vivamente di testare il [!DNL Express Checkout] in un ambiente di produzione, con carte di credito reali e banche, prima di esporre l&#39;estensione ai consumatori. Anche se il test in sandbox è importante, il test in produzione è il metodo più a prova di inganno per garantire che funzioni come previsto.

Consigliato di testare in produzione in uno dei due modi seguenti:

- Scegli un momento in cui sai che nessun ordine sarà effettuato da acquirenti.
- Utilizza un negozio web temporaneamente inaccessibile agli acquirenti, ma accessibile per te per i test.

Completa i test di produzione con le carte di credito reali e gli account di produzione Bolt, testando l&#39;intero ciclo di vita di un checkout. Quando completi l’intero flusso di cassa durante i test, ti fornisce un quadro chiaro di come funziona la tua funzionalità quando gli acquirenti live la utilizzano.

È inoltre necessario verificare che le informazioni riportate nei rendiconti bancari relative ai metodi di pagamento utilizzati nei test di produzione siano corrette e attese (inclusa la descrizione della propria attività).

## Come verificare il [!DNL Express Checkout] estensione

Completa il pagamento dall’archivio seguendo questi passaggi:

1. Vai alla vetrina e inserisci gli oggetti desiderati nel carrello.
1. Procedi al pagamento.
1. Inserisci un indirizzo e-mail associato a un account Bullt quando richiesto.
1. Inserisci la Password una tantum (OTP, One-Time Password) inviata all’indirizzo e-mail dell’account.
1. Seleziona il dashboard dell’ambiente:

   - Sandbox
   - Produzione

1. Ordine.

Una volta effettuato un ordine, puoi visualizzare i dettagli dei tuoi ordini nel tuo _Griglia ordini_ visualizza:

1. Passa a _Vendite_ > _Ordini_.
1. Vedere elenco di tutti gli ordini inseriti.

Consulta la sezione [ordini](https://docs.magento.com/user-guide/sales/orders.html) per ulteriori informazioni _Griglia ordini_ visualizza.
