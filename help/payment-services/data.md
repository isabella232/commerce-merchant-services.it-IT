---
title: Dati disponibili
description: Utilizza i dati di reporting finanziario per riconciliare il reporting con i sistemi non Commerce.
role: User
level: Intermediate
source-git-commit: ed471f363546f1d337e85568dc5079cae4507840
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Dati disponibili

Sono disponibili alcuni dati sugli ordini e sui pagamenti in modo da poter coordinare il reporting finanziario di Adobe Commerce tra sistemi esterni.

## Riconciliare con il sistema ERP

È possibile riconciliare il reporting finanziario di Adobe Commerce con il sistema ERP (Enterprise Resource Planning) non di Adobe utilizzando l&#39;ID incrementale associato a un ordine specifico.

Quando Payment Services invia l&#39;ordine Commerce a PayPal, l&#39;ID incrementale viene incluso come `custom_id` _e_ in `invoice_id` (che contiene anche una stringa casuale dopo la `increment_id`).

Gli ID sono facilmente accessibili sia nel dettaglio dell&#39;attività commerciale per un pagamento sia nel webhook di PayPal.

La `invoice_id` e `custom_id` sono visualizzati nella parte inferiore del dettaglio dell&#39;attività del commerciante per un pagamento:

![`custom_id` nel dettaglio dell&#39;attività commerciale](assets/merchant-activity-ids.png)

`custom_id` e `invoice_id` nei dettagli del webhook di PayPal:

```json
   ...
   {
    "id": "4E855005GK253170H",
    "intent": "AUTHORIZE",
    "status": "COMPLETED",
    "payment_source": {
        ...
    },
    "purchase_units": [
        {
            ...
            "custom_id": "000001322",
            "invoice_id": "000001322-c01bd7c3-920f-4542-a900-738082177e92",
            ...
            "payments": {
                "authorizations": [
                    {
                       ...
                        "invoice_id": "000001322-c01bd7c3-920f-4542-a900-738082177e92",
                        "custom_id": "000001322",
                        ...
                    }
                ],
                "captures": [
                    {
                        ...
                        "invoice_id": "000001322-c01bd7c3-920f-4542-a900-738082177e92",
                        "custom_id": "000001322",
                        ...
                    }
                ]
            }
        }
    ],
    "payer": {
        ...
    },
    "create_time": "2022-09-12T14:59:01Z",
    "update_time": "2022-09-12T14:59:45Z",
    "links": [
        ...
    ]
}
   ...
```

Per ulteriori informazioni, consulta la documentazione sulle API REST di PayPal:

* [`purchase_unit`, in cui `custom_id` e `invoice_id` risiedere](https://developer.paypal.com/docs/api/orders/v2/#definition-purchase_unit:~:text=Read%20only.-,purchase_unit,-Collapse)
* [Mostra dettagli ordine](https://developer.paypal.com/docs/api/orders/v2/#orders_get)
