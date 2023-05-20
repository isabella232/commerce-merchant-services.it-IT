---
title: Vuoti
description: I vuoti consentono di liberare i fondi in un conto della carta di credito o di debito che sono bloccati o detenuti da un'autorizzazione per l'importo di un acquisto.
exl-id: 029a7038-2812-46ce-b188-929a7a758d89
source-git-commit: 7b31fe7a71c3c238e6448627b2edfe06bbfbc80e
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Vuoti

Con [!DNL Payment Services], puoi utilizzare la funzionalità Commerce esistente per annullare le transazioni. I vuoti consentono di liberare i fondi in un conto della carta di credito o di debito che sono bloccati o detenuti da un&#39;autorizzazione per l&#39;importo di un acquisto.

>[!NOTE]
>
>Puoi annullare una transazione solo se il pagamento non è ancora stato acquisito.

Se il negozio è [configurato](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} per autorizzare solo i fondi (non acquisirli) presso il punto vendita, un acquisto dal tuo negozio comporta un ordine con un `Processing` stato in Commerce Admin.

È inoltre possibile [annullare un ordine](https://docs.magento.com/user-guide/sales/order-update.html#cancel-a-pending-order){target="_blank"} che non è fatturato. Anche eventuali autorizzazioni non acquisite vengono annullate nell’ambito di tale processo di annullamento.

>[!NOTE]
>
>L’annullamento di un ordine genera anche un annullamento, ma l’annullamento di un ordine non attiva l’annullamento.

Per ulteriori informazioni sui passaggi di base di un ordine, consulta [Flusso di lavoro ordine](https://docs.magento.com/user-guide/sales/order-workflow.html){target="_blank"} nella guida utente di base.

Per informazioni sulla funzionalità di annullamento e su come annullare una transazione dell’ordine, consulta [Elaborazione di un ordine](https://docs.magento.com/user-guide/sales/order-processing.html){target="_blank"} nella guida utente di base.
