---
title: Opzioni di pagamento
description: Impostare le opzioni di pagamento per personalizzare i metodi disponibili per i clienti del negozio.
exl-id: 95e648e6-6cb8-4226-b5ea-e1857212f20a
source-git-commit: bfb2b6632fe494d6e392c214f5e3f5a11930c0b2
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 0%

---

# Opzioni di pagamento

Con Adobe Commerce e Magento Open Source [!DNL Payment Services], hai a disposizione più opzioni di pagamento. Puoi configurare queste opzioni di pagamento tramite:

* [Dashboard](configure-dashboard.md)
* [Configurazione archivio](configure-admin.md) (consigliato per le opzioni di pagamento legacy o per una configurazione multistore)

Esistono diversi comportamenti per ogni metodo di pagamento a seconda della posizione nel processo di pagamento:

* Pagina prodotto: la pagina prodotto per un elemento
* Mini-carrello - Disponibile facendo clic sull&#39;icona del carrello quando un prodotto è stato aggiunto al carrello
* Carrello—Disponibile al clic di _Visualizza e modifica carrello_ dal mini-carrello
* Visualizzazione Pagamento—Disponibile al clic di _Procedi all&#39;estrazione_ da mini carrello o carrello

>[!IMPORTANT]
>
>L&#39;onboarding di Payment Services deve essere completato prima che i pagamenti possano essere elaborati.

## [!UICONTROL Credit Card Fields]

[!UICONTROL Credit Card Fields] fornire un pagamento semplice e sicuro per le modalità di pagamento con carta di credito o con carta di debito. Quando un acquirente effettua il Check-Out utilizzando i campi della carta di credito, immette il proprio nome, indirizzo di fatturazione e informazioni sulla carta di credito o di debito per effettuare l&#39;ordine. Le informazioni sui clienti vengono utilizzate in modo sicuro durante la sessione di acquisto per guidarle facilmente attraverso il flusso di cassa.

Puoi configurare [!UICONTROL Credit Card Fields] nella configurazione dello store o nel dashboard Servizi di pagamento. Vedi [Configurazione [!DNL Payment Services]](configure-dashboard.md#configure-credit-card-fields) per ulteriori informazioni.

## [!DNL PayPal Smart Buttons]

[!DNL PayPal Smart Buttons], che utilizza PayPal per completare un acquisto, memorizza l&#39;indirizzo di spedizione dell&#39;acquirente, gli indirizzi di fatturazione e i dettagli di pagamento per un utilizzo successivo. Gli acquirenti possono utilizzare qualsiasi metodo di pagamento precedentemente memorizzato o offerto da PayPal.

Puoi configurare [!DNL PayPal Smart Buttons] nella configurazione dello store o nel dashboard Servizi di pagamento.  Vedi [Configurazione [!DNL Payment Services]](configure-dashboard.md#configure-paypal-smart-buttons) per ulteriori informazioni.

### Pulsante PayPal

I clienti possono effettuare il check-out con facilità e sicurezza utilizzando il pulsante PayPal.

Il pulsante PayPal è visibile dalla pagina del prodotto, dal mini-carrello, dal carrello e dalle viste per il pagamento.

### Pulsante Venmo

I clienti possono effettuare il check-out utilizzando [Venmo](https://venmo.com/) pulsante .

Il pulsante Venmo è visibile dalla pagina del prodotto, dal mini-carrello, dal carrello e dalle viste per il pagamento.

### [!DNL Pay Later] pulsante

Offri ai tuoi clienti pagamenti a breve termine, senza interessi e altre opzioni di finanziamento in modo che possano acquistare ora e pagare in seguito con il [!DNL Pay Later] pulsante .

La [!DNL Pay Later] è visibile dalla pagina del prodotto, dal mini-carrello, dal carrello e dalle viste per il pagamento.

Sono disponibili due opzioni di pagamento con [!DNL Pay Later] pulsante:

* **Pagare in 4**- I clienti possono pagare il saldo dell&#39;ordine in quattro pagamenti senza interessi (ogni due settimane) dopo un pagamento iniziale in acconto. Consulta la sezione [Pagare in 4 documentazione](https://www.paypal.com/us/digital-wallet/ways-to-pay/buy-now-pay-later) per ulteriori informazioni.
* **Credito PayPal**- I clienti possono pagare il saldo dell&#39;ordine per tutto il periodo di sei mesi, senza interessi. Consulta la sezione [Documentazione di credito PayPal](https://www.paypal.com/us/webapps/mpp/paypal-credit) per ulteriori informazioni.

### [!DNL Pay Now] pulsante

La [!DNL Pay Now] Questo pulsante è visibile nella finestra a comparsa PayPal quando un cliente fa clic su un pulsante di pagamento nella schermata dei pagamenti.

Se l&#39;importo finale dell&#39;ordine non è ancora noto (ad esempio quando non si dispone ancora delle informazioni sull&#39;indirizzo di spedizione) e il cliente sta effettuando il check-out dalla pagina del prodotto, dal mini-carrello o dal carrello, un _Continua_ è invece disponibile. Quando un cliente fa clic su _Continua_, dopo aver confermato il metodo di pagamento, vengono indirizzati a una pagina di revisione dell&#39;ordine per raccogliere i dettagli necessari prima di completare l&#39;estrazione.

## [!DNL Pay Later] messaggistica

Per aiutare il cliente a identificarli come opzioni di pagamento potenziali, [!DNL Pay Later] i messaggi sono visibili nella pagina del prodotto, nel mini-carrello e nel carrello e durante il pagamento.

* **Quando un cliente seleziona un prodotto tra $ 30 e $ 600**, messaggi sotto PayPal e [!DNL Pay Later] pulsanti offre al cliente ulteriori informazioni sull&#39;opzione di pagamento Paga in 4. I clienti possono fare clic su **Ulteriori informazioni** per saperne di più sull&#39;opzione &quot;Paga in 4&quot; _o_ fare clic sul testo &quot;O vedere 6 mesi di finanziamento speciale&quot; nella finestra a comparsa per informazioni e richiedere per l&#39;opzione Credito PayPal.
* **Quando un cliente seleziona un prodotto o prodotti che superano $98,99**, messaggi sotto PayPal e [!DNL Pay Later] pulsanti offre ai clienti ulteriori informazioni sull&#39;opzione di pagamento PayPal Credit. I clienti possono fare clic su **Ulteriori informazioni** per informazioni e richiedere l&#39;opzione PayPal Credit _o_ fare clic sul testo &quot;O vedere Pagare in 4&quot; nella finestra a comparsa per saperne di più sull&#39;opzione Paga in 4.

   >[!NOTE]
   >
   >Gli importi sopra elencati sono soggetti a modifiche.

Vedi [Configura [!DNL Payment Services]](configure-admin.md#configure-paypal-smart-buttons) per scoprire come disabilitare o abilitare il [!DNL Pay Later] messaggistica.

## Ricalcolo ordine

Quando un cliente accede al flusso di pagamento dalla pagina del mini-carrello, del carrello o del prodotto, viene indirizzato a una pagina di revisione dell&#39;ordine in cui può vedere l&#39;indirizzo di spedizione selezionato in una finestra popup di PayPal. Dopo che il cliente seleziona il metodo di spedizione, l&#39;importo dell&#39;ordine viene ricalcolato in modo appropriato e il cliente può vedere i costi di spedizione e le imposte.

Quando un cliente accede al flusso di pagamento dalla pagina di pagamento, il sistema è già a conoscenza dell&#39;indirizzo di spedizione e dell&#39;importo calcolato finale e i totali sono rappresentati in modo appropriato.

Le ferie fiscali, i costi di spedizione e le tasse di vendita possono variare notevolmente da posizione a posizione. Dopo [!DNL Payment Services] riceve l&#39;indirizzo e il tasso di spedizione, ricalcola rapidamente tutti i costi applicabili e li visualizza in modo appropriato durante le ultime fasi di pagamento.

## Pagamento dalla pagina del prodotto

Quando un cliente effettua il check-out direttamente dalla pagina del prodotto, utilizzando PayPal o [!DNL Pay Later] vengono acquistati solo gli elementi rappresentati nella pagina di prodotto corrente. Gli articoli già presenti nel carrello del cliente non vengono aggiunti al flusso di pagamento e non vengono acquistati.

Se il cliente annulla l&#39;ordine, l&#39;articolo nella pagina di prodotto corrente viene aggiunto al carrello del cliente, unendo tutti gli altri articoli presenti nel carrello. Questa funzione consente al cliente di acquistare rapidamente l&#39;articolo che sta visualizzando, conservando anche tutti gli altri articoli aggiunti al carrello in precedenza durante la navigazione dei prodotti.

Quando un cliente accede al flusso di pagamento dalla pagina del prodotto, la pagina di pagamento viene semplificata; la visualizzazione mostra solo i dati e le opzioni relativi all’ordine.

## Sicurezza

Vedi [Conformità PCI](security.md#pci-compliance) per ulteriori informazioni.
