---
title: Rimborsi
description: Crea rimborsi per [!DNL Payment Services] ordini nell'amministratore come parte del processo della nota di accredito.
exl-id: 2b3721a1-9c9d-4e3f-ab7d-5bd61573dcb4
source-git-commit: fd818dadbaa2a58efd7313ce888c7dda27d25f14
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Rimborsi

Rimborsi per [!DNL Payment Services] gli ordini vengono creati nell&#39;amministratore come parte del processo della nota di credito. Una nota di credito è un documento che mostra l&#39;importo dovuto al cliente, per un rimborso completo o parziale, che può essere applicato a un acquisto o rimborsato direttamente al cliente. Le note di accredito possono essere emesse solo per gli ordini che sono [fatturato](https://docs.magento.com/user-guide/sales/invoice-create.html){target=&quot;_blank&quot;}.

Vedi [Note di credito](https://docs.magento.com/user-guide/sales/credit-memos.html){target=&quot;_blank&quot;} nella nostra guida utente principale per ulteriori informazioni e per scoprire come emettere e stampare note di credito.

Per gli ordini elaborati con PayPal o una carta di credito è possibile:

* Rimborso dell&#39;intero importo dell&#39;ordine
* Rimborso di un importo parziale di un ordine (o di più importi parziali)
* Rimborso di un importo inferiore al valore di un articolo dell&#39;ordine specifico

Vedi [Emissione di una nota di accredito](https://docs.magento.com/user-guide/sales/credit-memo-create.html){target=&quot;_blank&quot;} nella guida utente principale per ulteriori informazioni.

>[!NOTE]
>
>Si verifica un errore per gli ordini PayPal o elaborati con carta di credito se si tenta di rimborsare parzialmente un ordine per più dell&#39;importo dell&#39;ordine rimanente (importo originale meno il totale dei rimborsi esistenti), o se si emette un rimborso per un importo superiore all&#39;importo dell&#39;ordine completo.

La [!UICONTROL Payment Action] impostazione nella [!UICONTROL Payment Settings] configurazione: o `Authorize` o `Authorize and Capture`- determina il [flusso di lavoro di rimborso di base](https://docs.magento.com/user-guide/sales/credit-memos.html#refund-workflow){target=&quot;_blank&quot;} per gli ordini.

Consulta la sezione [Sezione impostazione azione pagamento](https://docs.magento.com/user-guide/sales/credit-memo-create.html#payment-action-setting){target=&quot;_blank&quot;} di _Emissione di una nota di accredito_ per ulteriori informazioni.
