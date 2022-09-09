---
title: Dati disponibili
description: Utilizza i dati di reporting finanziario per riconciliare il reporting con i sistemi non Commerce.
role: User
level: Intermediate
source-git-commit: 1186b4e52f1d613332a7862c58f482c2591e29a8
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Dati disponibili

Sono disponibili alcuni dati sugli ordini e sui pagamenti in modo da poter coordinare il reporting finanziario di Adobe Commerce tra sistemi esterni.

## Riconciliare con il sistema ERP

È possibile riconciliare il reporting finanziario di Adobe Commerce con il sistema ERP (Enterprise Resource Planning) non di Adobe utilizzando l&#39;ID incrementale associato a un ordine specifico.

Quando Payment Services invia l&#39;ordine Commerce a PayPal, l&#39;ID incrementale viene incluso come `custom_id`. La `custom_id` è visibile nel dettaglio dell&#39;attività commerciale per un pagamento e nel webhook PayPal.

`custom_id` nella parte inferiore del dettaglio dell&#39;attività commerciale per un pagamento:

![`custom_id` nel dettaglio dell&#39;attività commerciale](assets/merchant-activity.png)

`custom_id` nei dettagli del webhook di PayPal:

```json
   ...
   },
   "seller_protection": {
   "status": "NOT_ELIGIBLE"
   },
   "create_time": "2022-08-28T21:06:53Z",
   "custom_id": "000000829",
   "supplementary_data": {
   "related_ids":

   { "authorization_id": "6WW957787A749904A", "order_id": "3SV13726F9525791J" }
   },
   ...
```

Per ulteriori informazioni, consulta la documentazione sulle API REST di PayPal:

* [`purchase_unit` in cui `custom_id` risiede](https://developer.paypal.com/docs/api/orders/v2/#definition-purchase_unit:~:text=Read%20only.-,purchase_unit,-Collapse)
* [Mostra dettagli ordine](https://developer.paypal.com/docs/api/orders/v2/#orders_get)
