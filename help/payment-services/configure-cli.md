---
title: Configurazione della riga di comando
description: Dopo l'installazione, è possibile configurare [!DNL Payment Services] utilizzando l’interfaccia CLI (Command-line Interface).
role: Admin, Developer
level: Intermediate
exl-id: 265ab1be-fe52-41f3-85cb-addbc2ddfb17
source-git-commit: 817a01e98876bddf5f41a253501984539b3351cd
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Configurazione della riga di comando

Dopo l&#39;installazione [!DNL Payment Services], è possibile configurarlo facilmente da [all&#39;interno della casa](payments-home.md) o tramite l’interfaccia a riga di comando (CLI).

## Configurare l’esportazione di dati

[!DNL Payment Services] combina i dati degli ordini esportati da [!DNL Magento Open Source] e [!DNL Adobe Commerce] con i dati di pagamento aggregati dei fornitori di pagamenti per creare utili rapporti. La [!DNL Payment Services] l&#39;estensione utilizza gli indicizzatori per raccogliere in modo efficiente tutti i dati necessari per i rapporti.

Per informazioni sui dati utilizzati in [!DNL Payment Services] reporting, vedi [Report stato del pagamento dell&#39;ordine](order-payment-status.md#data-used-in-the-report).

### Configura cron on [!DNL Magento Open Source]

Se desideri utilizzare un `BY SCHEDULE` modalità indice attiva [!DNL Magento Open Source], devi configurare cron. Vedi [Configurare ed eseguire cron](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html).

### Imposta indici

I dati dell&#39;ordine vengono esportati e mantenuti nel servizio di pagamento, utilizzando una delle due modalità di indice:`ON SAVE` (predefinito) o `BY SCHEDULE` (consigliato).

I seguenti indici sono per [!DNL Payment Services]:

| Codice | Nome | Descrizione |
|    ---    |  ---  |  ---  |
| `sales_order_data_exporter` | Feed ordine di vendita | Genera l&#39;indice dei dati dell&#39;ordine |
| `sales_order_status_data_exporter` | Feed stato ordine di vendita | Crea l&#39;indice degli stati degli ordini di vendita |
| `store_data_exporter` | Memorizza feed | Genera l&#39;indice dei dati dell&#39;archivio |

Per modificare la modalità indice per tutti e tre gli indici, esegui:

```bash
bin/magento indexer:set-mode schedule sales_order_data_exporter sales_order_status_data_exporter store_data_exporter
```

>[!TIP]
>
>Se non si specificano indici nel comando, tutti gli indici vengono aggiornati allo stesso valore. Se si desidera modificare un indicizzatore specifico, è necessario inserirlo nel comando.

Per ulteriori informazioni sulla modifica manuale della modalità di un indicizzatore, vedere [Configurare gli indicizzatori](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html#configure-indexers){target="_blank"} in the developer documentation. To learn how to change it in the Admin, see [Index management](https://docs.magento.com/user-guide/system/index-management.html#change-the-index-mode){target="_blank"} nella guida utente di base.

### Reindicizzare manualmente i dati

È possibile reindicizzare manualmente i dati, invece di attendere che si verifichino automaticamente. Vedi [Reindicizzazione](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html#reindex){target="_blank"} in [Manage the Indexers](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html){target="_blank"} per ulteriori informazioni.

Quando `BY SCHEDULE` viene impostata, il sistema tiene traccia delle entità modificate e il processo cron ne aggiorna l&#39;indice in base a una pianificazione impostata. Vedi [Esegui cron dalla riga di comando](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html#config-cli-cron-group-run) in [Configurare ed eseguire cron](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html)) per scoprire come attivare manualmente l’indicizzazione utilizzando cron jobs.

### Invia dati reindicizzati al servizio di pagamento

Dopo l’indicizzazione dei dati, questi vengono inviati automaticamente a [!DNL Payment Services]. Puoi anche attivare manualmente il processo di invio di dati indicizzati con questo comando:

```bash
bin/magento saas:resync --feed [feedName]
```

Utilizzare le seguenti opzioni di comando:

| Comando | Descrizione |
|  ---  |  ---  |
| `bin/magento saas:resync --feed [feedName]` | Esegue una reindicizzazione del feed specificato e lo invia al servizio corrispondente |
| `bin/magento saas:resync --no-reindex` | Ignora l&#39;indicizzazione e invia dati non sincronizzati dagli indici |

La `--feed` Il parametro consente di specificare quale feed si desidera inviare:

| Feed | Descrizione |
|  ---  |  ---  |
| `paymentServicesOrdersProduction` | Feed ordini in modalità Produzione |
| `paymentServicesOrdersSandbox` | Feed ordini in modalità Sandbox |
| `paymentServicesOrderStatusesProduction` | Stato dell’ordine in modalità Produzione |
| `paymentServicesOrderStatusesSandbox` | Stato dell’ordine in modalità Sandbox |
| `paymentServicesStoresProduction` | Negozi in modalità Produzione |
| `paymentServicesStoresSandbox` | Negozi in modalità Sandbox |

Tutti i dati necessari per i rapporti vengono inviati a [!DNL Payment Services] automaticamente se cron è configurato e installato. Puoi anche attivare manualmente il processo di invio dei dati cron a [!DNL Payment Services].

```bash
bin/magento cron:run --group payment_services_data_export
```

Per ulteriori informazioni sulla reindicizzazione e sugli indici, consulta la sezione [Gestire gli indici](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html) nella documentazione per gli sviluppatori.
