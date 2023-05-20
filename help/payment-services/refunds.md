---
title: Rimborsi
description: Crea rimborsi per [!DNL Payment Services] ordini nell'Admin come parte del processo della nota di credito.
exl-id: 2b3721a1-9c9d-4e3f-ab7d-5bd61573dcb4
source-git-commit: fd818dadbaa2a58efd7313ce888c7dda27d25f14
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Rimborsi

Rimborsi per [!DNL Payment Services] Gli ordini vengono creati nell&#39;Admin come parte del processo della nota di credito. Una nota di credito è un documento che mostra l&#39;importo dovuto al cliente, per un rimborso completo o parziale, che può essere applicato a un acquisto o rimborsato direttamente al cliente. Le note di accredito possono essere emesse solo per gli ordini che sono [fatturato](https://docs.magento.com/user-guide/sales/invoice-create.html){target="_blank"}.

Consulta [Note di credito](https://docs.magento.com/user-guide/sales/credit-memos.html){target="_blank"} nella nostra guida utente di base per ulteriori informazioni e per scoprire come emettere e stampare le note di credito.

Per gli ordini elaborati con PayPal o con una carta di credito puoi:

* Rimborsare l&#39;intero importo dell&#39;ordine
* Rimborsare un importo parziale di un ordine (o più importi parziali)
* Rimborso di un importo inferiore al valore di un articolo dell&#39;ordine specifico

Consulta [Emissione di una nota di credito](https://docs.magento.com/user-guide/sales/credit-memo-create.html){target="_blank"} nella nostra guida utente di base per ulteriori informazioni.

>[!NOTE]
>
>Si verifica un errore per gli ordini PayPal o elaborati con carta di credito se si tenta di rimborsare parzialmente un ordine per un importo superiore all&#39;importo restante (importo originale meno il totale dei rimborsi esistenti) o se si emette un rimborso per un importo superiore all&#39;intero importo dell&#39;ordine.

Il [!UICONTROL Payment Action] impostazioni in [!UICONTROL Payment Settings] configurazione: `Authorize` o `Authorize and Capture`- determina la [flusso di lavoro di rimborso di base](https://docs.magento.com/user-guide/sales/credit-memos.html#refund-workflow){target="_blank"} per gli ordini.

Consulta la [Sezione impostazione azione pagamento](https://docs.magento.com/user-guide/sales/credit-memo-create.html#payment-action-setting){target="_blank"} di _Emissione di una nota di credito_ per ulteriori informazioni.
