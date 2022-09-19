---
title: Voci
description: I vuoti consentono di liberare i fondi in un conto di carte di credito o di debito che sono bloccati o tenuti da parte da un'autorizzazione per l'importo di un acquisto.
exl-id: 029a7038-2812-46ce-b188-929a7a758d89
source-git-commit: 7b31fe7a71c3c238e6448627b2edfe06bbfbc80e
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Voci

Con [!DNL Payment Services], puoi utilizzare la funzionalità Commerce esistente per annullare le transazioni. I vuoti consentono di liberare i fondi in un conto di carte di credito o di debito che sono bloccati o tenuti da parte da un&#39;autorizzazione per l&#39;importo di un acquisto.

>[!NOTE]
>
>È possibile annullare una transazione solo se il pagamento non è ancora stato acquisito.

Se il tuo negozio è [configurato](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target=&quot;_blank&quot;} per autorizzare solo (non acquisire) i fondi nel punto vendita, un acquisto dal negozio determina un ordine con un `Processing` in Commerce Admin.

È inoltre possibile [annullare un ordine](https://docs.magento.com/user-guide/sales/order-update.html#cancel-a-pending-order){target=&quot;_blank&quot;} non fatturata. Anche le autorizzazioni non acquisite vengono annullate nell&#39;ambito del processo di cancellazione.

>[!NOTE]
>
>L’annullamento di un ordine produce anche un vuoto, ma l’annullamento di un ordine non provoca l’annullamento.

Per ulteriori informazioni sui passaggi di base di un ordine, consulta la sezione [Flusso di lavoro ordine](https://docs.magento.com/user-guide/sales/order-workflow.html)Argomento {target=&quot;_blank&quot;} nella guida utente principale.

Per informazioni sulla funzionalità void e su come annullare una transazione d&#39;ordine, vedi [Elaborazione di un ordine](https://docs.magento.com/user-guide/sales/order-processing.html){target=&quot;_blank&quot;} nella guida utente principale.
