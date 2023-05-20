---
title: Opzioni di pagamento
description: Imposta le opzioni di pagamento per personalizzare i metodi disponibili per i clienti del tuo Negozio.
exl-id: 95e648e6-6cb8-4226-b5ea-e1857212f20a
source-git-commit: 9bc392f2ae12269ded6174b830562444d6827f5f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---

# Opzioni di pagamento

Con [!DNL Adobe Commerce] e [!DNL Magento Open Source] [!DNL Payment Services], sono disponibili più opzioni di pagamento. Puoi configurare queste opzioni di pagamento tramite:

* [Impostazioni home](payments-home.md)
* [Configurazione archivio](configure-admin.md) (consigliato per le opzioni di pagamento legacy o per una configurazione multistore)

Esistono comportamenti diversi per ogni metodo di pagamento a seconda della posizione in cui sei nel processo di pagamento:

* Pagina prodotto: la pagina di prodotto di un elemento
* Mini carrello: disponibile facendo clic sull&#39;icona del carrello quando un prodotto è stato aggiunto al carrello
* Carrello acquisti: disponibile facendo clic su _Visualizza e modifica carrello_ dal mini-carrello
* Vista Check-Out - Disponibile quando fate clic su _Procedi all&#39;estrazione_ da mini-carrello o carrello

>[!IMPORTANT]
>
>L’onboarding di Payment Services deve essere completato prima dell’elaborazione dei pagamenti.

## [!UICONTROL Credit Card Fields]

[!UICONTROL Credit Card Fields] fornire un pagamento semplice e sicuro per i metodi di pagamento con carta di credito o con carta di debito. Quando un acquirente effettua il check-out utilizzando i campi della carta di credito, inserisce il proprio nome, l’indirizzo di fatturazione e le informazioni sulla carta di credito o di debito per effettuare l’ordine. Le informazioni sui clienti vengono utilizzate in modo sicuro durante la sessione di acquisto per guidarli all’interno del flusso di pagamento.

Abilita [vaulting con carta di credito](#vaulting) per consentire ai tuoi negozi di archiviare (salvare) le informazioni sulla carta di credito per un pagamento rapido in un secondo momento.

Puoi configurare [!UICONTROL Credit Card Fields] nella configurazione del negozio o nella Home di Payment Services. Consulta [Impostazioni](settings.md#credit-card-fields) per ulteriori informazioni.

È inoltre possibile modificare il layout, la larghezza, l&#39;altezza e lo stile esterno dei campi della carta di credito. Consulta [Documentazione di PayPal](https://developer.paypal.com/docs/checkout/advanced/customize/card-field-style/) per ulteriori informazioni.

## [!DNL PayPal Smart Buttons]

[!DNL PayPal Smart Buttons], che utilizzano PayPal per completare un acquisto, memorizza l&#39;indirizzo di spedizione, gli indirizzi di fatturazione e i dettagli del pagamento del cliente per un uso successivo. Gli acquirenti possono utilizzare qualsiasi metodo di pagamento precedentemente memorizzato o offerto da PayPal.

![[!DNL PayPal Smart Buttons] opzioni](assets/buttons-md.png)

Puoi configurare [!UICONTROL PayPal Smart Buttons] nella configurazione del negozio o nella Home di Payment Services.  Consulta [Impostazioni](settings.md#payment-buttons) per ulteriori informazioni.

### [!DNL PayPal] pulsante

I clienti possono effettuare il check-out con facilità e sicurezza utilizzando il pulsante PayPal.

Il [!DNL PayPal] è visibile dalla pagina del prodotto, dal mini-carrello, dal carrello e dalle viste di pagamento.

### [!DNL Venmo] pulsante

I clienti possono effettuare il check-out utilizzando [Venmo](https://venmo.com/) pulsante.

Il [!DNL Venmo] è visibile dalla pagina del prodotto, dal mini-carrello, dal carrello e dalle viste di pagamento.

### [!DNL Apple Pay] pulsante

I clienti possono utilizzare il Touch ID sui loro dispositivi [[!DNL Apple Pay]](https://www.apple.com/apple-pay/), che utilizza le credenziali di pagamento con carta di credito e di debito memorizzate sul dispositivo iOS o macOS.

Il [!DNL Apple Pay] è visibile dalla pagina del prodotto, dal mini-carrello, dal carrello e dalle viste di pagamento.

>[!NOTE]
>
> Da utilizzare [!DNL Apple Pay] per i negozi, completa [registrazione autonoma con [!DNL Apple Pay]](https://developer.paypal.com/docs/checkout/apm/apple-pay/#register-your-live-domain) (_Registra il dominio live_ solo sezione ) e [configuralo per i tuoi store in [!DNL Payment Services]](settings.md#payment-buttons).

### [!DNL Pay Later] pulsante

Offri ai tuoi clienti pagamenti a breve termine senza interessi e altre opzioni di finanziamento in modo che possano acquistare subito e pagare in seguito con [!DNL Pay Later] pulsante.

Il [!DNL Pay Later] è visibile dalla pagina del prodotto, dal mini-carrello, dal carrello e dalle viste di pagamento:

* **Quando un cliente seleziona un prodotto tra $ 30 e $ 600**, messaggistica con PayPal e [!DNL Pay Later] fornisce al cliente ulteriori informazioni sulla [!DNL Pay in 4] opzione di pagamento. I clienti possono fare clic su **Ulteriori informazioni** per informazioni sulla funzione &quot;[!DNL Pay in 4]Opzione &quot; _o_ fai clic sul testo &quot;Oppure consulta 6 mesi di finanziamento speciale&quot; nel popup per scoprire e richiedere l&#39;opzione PayPal Credit.
* **Quando un cliente seleziona uno o più prodotti superiori a 98,99 $**, messaggistica con PayPal e [!DNL Pay Later] fornisce ai clienti maggiori informazioni sull&#39;opzione di pagamento PayPal Credit. I clienti possono fare clic su **Ulteriori informazioni** per scoprire e richiedere l&#39;opzione PayPal Credit, _o_ fare clic sul testo &quot;Oppure vedere Pagare in 4&quot; nel popup per saperne di più [!DNL Pay in 4] opzione.

   >[!NOTE]
   >
   >Gli importi di cui sopra sono soggetti a modifiche.

Consulta [Impostazioni](settings.md#payment-buttons) per scoprire come disabilitare/abilitare [!DNL Pay Later] messaggi.

Sono disponibili due opzioni di pagamento con [!DNL Pay Later] pulsante:

* **Pagamento in 4**—I clienti possono pagare il saldo dell&#39;ordine in quattro pagamenti senza interessi (ogni due settimane) dopo un iniziale acconto. Consulta la [Documentazione di Pay in 4](https://www.paypal.com/us/digital-wallet/ways-to-pay/buy-now-pay-later) per ulteriori informazioni.
* **Credito PayPal**- I clienti possono pagare il saldo dell&#39;ordine per un periodo di sei mesi, senza interessi. Consulta la [Documentazione di PayPal Credit](https://www.paypal.com/us/webapps/mpp/paypal-credit) per ulteriori informazioni.

### [!DNL Pay Now] pulsante

Il [!DNL Pay Now] è visibile nella finestra popup PayPal quando un cliente fa clic su un pulsante di pagamento nella schermata pagamenti.

Se l&#39;importo dell&#39;ordine finale non è ancora noto (ad esempio quando non si dispone ancora di informazioni sull&#39;indirizzo di spedizione) e il cliente è in fase di check-out dalla pagina del prodotto, dal mini-carrello o dal carrello, un _Continua_ al suo posto. Quando un cliente fa clic _Continua_, dopo aver confermato il metodo di pagamento, vengono indirizzati a una pagina di revisione dell&#39;ordine per raccogliere i dettagli necessari prima di completare il pagamento.

## Ricalcolo ordine

Quando un cliente accede al flusso di pagamento dal mini-carrello, dal carrello o dalla pagina del prodotto, viene indirizzato a una pagina di revisione dell’ordine in cui può visualizzare l’indirizzo di spedizione selezionato in una finestra a comparsa PayPal. Dopo che il cliente ha selezionato il metodo di spedizione, l&#39;importo dell&#39;ordine viene ricalcolato in modo appropriato e il cliente può visualizzare le spese di spedizione e le imposte.

Quando un cliente accede al flusso di pagamento dalla pagina di pagamento, il sistema è già a conoscenza dell&#39;indirizzo di spedizione e dell&#39;importo calcolato finale e i totali sono rappresentati in modo appropriato.

Le esenzioni fiscali, le spese di spedizione e l&#39;IVA possono variare notevolmente da un&#39;ubicazione all&#39;altra. Dopo [!DNL Payment Services] riceve l&#39;indirizzo e la tariffa di spedizione, ricalcola rapidamente tutti i costi applicabili e li visualizza in modo appropriato durante le ultime fasi di pagamento.

## Ritira dalla pagina del prodotto

Quando un cliente effettua il check-out direttamente dalla pagina del prodotto, utilizzando PayPal o [!DNL Pay Later] , viene acquistato solo l&#39;articolo rappresentato nella pagina di prodotto corrente. Gli articoli già presenti nel carrello del cliente non vengono aggiunti al flusso di pagamento e non vengono acquistati.

Se il cliente annulla l’ordine, l’articolo nella pagina del prodotto corrente viene aggiunto al carrello del cliente, unendo tutti gli altri articoli presenti nel carrello. Questa funzione consente al cliente di acquistare rapidamente l’articolo che sta visualizzando, conservando anche tutti gli altri articoli aggiunti al carrello in precedenza durante la navigazione dei prodotti.

Quando un cliente accede al flusso di pagamento dalla pagina del prodotto, la pagina di pagamento viene semplificata: la visualizzazione mostra solo i dati e le opzioni relativi all’ordine.

## Vaulting con carta di credito

Gli acquirenti possono vagliare, o &quot;salvare&quot;, le informazioni sulla loro carta di credito per acquisti futuri a livello del sito web (qualsiasi negozio all&#39;interno dello stesso account del commerciante).

Consulta [Vaulting con carta di credito](vaulting.md) per ulteriori informazioni.

## Sicurezza

Consulta [Conformità PCI](security.md#pci-compliance) per ulteriori informazioni.
