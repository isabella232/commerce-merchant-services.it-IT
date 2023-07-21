---
title: Trasferimento origine Inventory management
description: "Configurare le scorte per [!DNL Store Fulfillment solution] con Adobe Commerce Inventory management. Impostare un nuovo magazzino e trasferirlo al di fuori del magazzino predefinito in modo da poterlo assegnare alle origini configurate per abilitare le funzionalità di prelievo del magazzino richieste dalla soluzione di evasione del magazzino."
role: Admin
level: Intermediate
feature: Shipping/Delivery, Inventory, Configuration
exl-id: 669d4dce-4cac-4bde-acc5-26c70a51f7f1
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---


# Trasferimento origine Inventory management

Il [!DNL Store Fulfillment] utilizza Adobe Commerce Inventory management nativo. Per impostazione predefinita, il [!DNL Commerce] la configurazione assegna tutto l&#39;inventario web alle scorte predefinite, alle quali non possono essere assegnate altre origini. Poiché a un sito Web è possibile assegnare un solo stock, un commerciante deve configurare un nuovo stock e, facoltativamente, trasferire il proprio inventario di origine predefinito a un&#39;origine assegnata all&#39;ambito appropriato. Quindi, l&#39;origine può essere assegnata al nuovo stock.

>[!IMPORTANT]
>
>I commercianti devono mantenere l’origine predefinita per tutti i prodotti inclusi nei tipi di prodotto di gruppo e bundle. Per questi prodotti è necessaria una quantità di magazzino che soddisfi la soglia della quantità minima per gli articoli in magazzino e includa uno stato di magazzino pari a [!UICONTROL In Stock].

Queste modifiche alla configurazione consentono di eseguire tre operazioni:

1. [Trasferisci magazzino all&#39;origine](https://docs.magento.com/user-guide/catalog/inventory-bulk-transfer-inventory.html) per spostare le scorte dalla scorta/origine predefinita alla nuova scorta/origine.

1. [Assegnazione in blocco delle origini](https://docs.magento.com/user-guide/catalog/inventory-bulk-assign-sources.html) per aggiungere le nuove sorgenti per tutti i prodotti.

1. [Aggiornamenti in blocco completi per gli attributi del prodotto](https://docs.magento.com/user-guide/stores/bulk-product-attribute-update.html) per aggiungere `Allow Store Pickup` e `Allow Home Delivery` attributi ai prodotti esistenti. Quando la soluzione viene installata, gli attributi hanno il *predefinito* valori. Tuttavia, questi attributi non vengono applicati ai prodotti esistenti fino a quando non si completa il processo di updaContes in blocco.

L&#39;inventario viene detratto dall&#39;origine selezionata (ubicazione negozio al dettaglio o magazzino di e-commerce). Le origini utilizzate come magazzini di e-commerce devono essere assegnate alla stessa scorta del luogo di prelievo del negozio e prioritarie prima delle posizioni di vendita al dettaglio. Per ulteriori informazioni, consulta [Assegnazione di priorità alle origini per un Stock](https://docs.magento.com/user-guide/catalog/inventory-stock-priority.html).

Per ulteriori informazioni sulla gestione di inventario, scorte e origini, consulta la documentazione utente di Adobe Commerce:

- [Gestione dell’inventario](https://docs.magento.com/user-guide/catalog/inventory-management.html)

- [Gestione delle quantità di magazzino](https://docs.magento.com/user-guide/catalog/inventory-manage-inventory-quantities.html)

- [Gestione delle scorte](https://docs.magento.com/user-guide/catalog/inventory-stock.html)

- [Gestione delle origini](https://docs.magento.com/user-guide/catalog/inventory-sources.html)

- [Assegnazione di priorità alle origini per un Stock](https://docs.magento.com/user-guide/catalog/inventory-stock-priority.html)

- [Aggiornamenti in blocco per gli attributi del prodotto](https://docs.magento.com/user-guide/stores/bulk-product-attribute-update.html)


>[!IMPORTANT]
>
>La modifica della configurazione delle origini di inventario e di magazzino può avere un impatto a valle anche sui sistemi integrati. Assicurati di comprendere in che modo le modifiche alla configurazione dell’inventario influiscono su questi sistemi.
