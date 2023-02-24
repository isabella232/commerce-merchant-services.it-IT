---
title: Configurazione del processo in background
description: "Configura le pianificazioni per [!DNL Store Fulfillment] processi in background utilizzati nella sincronizzazione dei dati con i servizi di evasione."
role: User, Admin
level: Intermediate
exl-id: 742ae59e-77a0-4db6-b156-2992d4403be7
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%

---


# Configurazione del processo in background

L&#39;integrazione Store Fulfillment utilizza processi in background e code di messaggi per prestazioni e scalabilità ottimali. Creare ambienti per i negozi Adobe Commerce utilizzando [variabili di distribuzione](https://devdocs.magento.com/cloud/env/variables-deploy.html#cron_consumers_runner) che si avvia automaticamente [corridori della coda messaggi](https://devdocs.magento.com/guides/v2.4/config-guide/mq/rabbitmq-overview.html).

I processi in background vengono gestiti tramite Adobe Commerce standard [Attività pianificate](https://docs.magento.com/user-guide/system/cron.html) funzionalità. Questi processi sono responsabili della sincronizzazione dei dati di configurazione dell&#39;ordine e dell&#39;archivio commerciale con i servizi Web di evasione dell&#39;archivio.

## Gestione delle attività pianificate per l&#39;esecuzione dello store

Dall’amministratore, vai a **[!UICONTROL Stores > Configuration > Advanced > System > Cron (Scheduled Tasks) > Cron configuration options for group:store_fulfillment]**.

Controlla la configurazione predefinita per i servizi Store Fulfillment. A seconda del volume di elaborazione dell&#39;ordine e della disponibilità delle risorse, potrebbe essere necessario modificare queste impostazioni.
