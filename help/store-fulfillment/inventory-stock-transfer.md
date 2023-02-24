---
title: Trasferimento origine Inventory management
description: "Configurare le risorse per [!DNL Store Fulfillment solution] con Adobe Commerce Inventory management. Imposta un nuovo magazzino e trasferisci magazzino fuori magazzino predefinito in modo da poterlo assegnare a fonti configurate per abilitare le funzionalità di Store Pickup richieste dalla soluzione Store Fulfillment."
role: User, Admin
level: Intermediate
exl-id: 669d4dce-4cac-4bde-acc5-26c70a51f7f1
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---


# Trasferimento origine Inventory management

La [!DNL Store Fulfillment] la soluzione utilizza Adobe Commerce Inventory management nativo. Per impostazione predefinita, la [!DNL Commerce] la configurazione assegna tutto l&#39;inventario web al magazzino predefinito, che non può avere ulteriori origini assegnate. Poiché a un sito web può essere assegnato un solo stock, un commerciante deve configurare un nuovo stock e, facoltativamente, trasferire il proprio inventario di origine predefinito a un&#39;origine assegnata all&#39;ambito appropriato. Quindi, la sorgente può essere assegnata al nuovo stock.

Queste modifiche alla configurazione consentono di eseguire tre operazioni:

1. [Trasferisci inventario all&#39;origine](https://docs.magento.com/user-guide/catalog/inventory-bulk-transfer-inventory.html) per spostare le scorte dalla risorsa o dall&#39;origine predefinita alla nuova scorta/origine.

1. [Assegnazione in blocco di origini](https://docs.magento.com/user-guide/catalog/inventory-bulk-assign-sources.html) per aggiungere le nuove origini per tutti i prodotti.

1. [Aggiornamenti in blocco completi per gli attributi di prodotto](https://docs.magento.com/user-guide/stores/bulk-product-attribute-update.html) per aggiungere `Allow Store Pickup` e `Allow Home Delivery` attributi ai prodotti esistenti. Quando la soluzione viene installata, gli attributi hanno *default* valori. Tuttavia, questi attributi non vengono applicati ai prodotti esistenti finché non completi il processo di aggiornamento in blocco.

L&#39;inventario viene detratto dall&#39;origine selezionata (posizione negozio al dettaglio o magazzino e-commerce). Le origini utilizzate come magazzini di e-commerce devono essere assegnate allo stesso stock della posizione di prelievo del negozio e prioritarie prima delle posizioni di vendita al dettaglio. Per ulteriori informazioni, consulta [Assegnazione di priorità alle fonti per un Stock](https://docs.magento.com/user-guide/catalog/inventory-stock-priority.html).

Per ulteriori informazioni sulla gestione di scorte, scorte e origini, consulta la documentazione utente di Adobe Commerce:

- [Gestione dell&#39;inventario](https://docs.magento.com/user-guide/catalog/inventory-management.html)

- [Gestione delle quantità di magazzino](https://docs.magento.com/user-guide/catalog/inventory-manage-inventory-quantities.html)

- [Gestione delle azioni](https://docs.magento.com/user-guide/catalog/inventory-stock.html)

- [Gestione delle origini](https://docs.magento.com/user-guide/catalog/inventory-sources.html)

- [Assegnazione di priorità alle fonti per un Stock](https://docs.magento.com/user-guide/catalog/inventory-stock-priority.html)

- [Aggiornamenti in blocco per gli attributi del prodotto](https://docs.magento.com/user-guide/stores/bulk-product-attribute-update.html)


>[!IMPORTANT]
>
>La modifica della configurazione per le fonti di inventario e di stock può anche avere un impatto a valle sui sistemi integrati. Assicurati di comprendere in che modo le modifiche alla configurazione dell&#39;inventario influiscono su questi sistemi.
