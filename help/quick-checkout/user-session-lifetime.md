---
title: Durata della sessione utente
description: L’amministratore consente di configurare la durata dei cookie dell’utente Adobe Commerce per il [!DNL Quick Checkout] estensione.
exl-id: 32cf5d70-9a50-49ca-8b40-5f04bc1e24b7
feature: Checkout, Services
source-git-commit: b1984a26463e14b8dc9a789421e49e5ea81ad039
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Durata sessione utente

La durata di una sessione cliente è determinata da diversi fattori che possono essere configurati nell’amministratore di Adobe Commerce. Consulta [Configurare la durata del cookie](https://experienceleague.adobe.com/docs/commerce-admin/customers/customer-accounts/configure/customer-online-options.html){target=_blank} per ulteriori informazioni.

La durata configurata dei cookie può influire sul tuo [!DNL Quick Checkout] se:

1. A causa di inattività, l’acquirente è disconnesso da Adobe Commerce.
1. Il [!DNL Bolt] la sessione scade.

Se un acquirente effettua un ordine quando il [!DNL Bolt] scadenza della sessione, l’ordine viene effettuato correttamente ma l’utente viene disconnesso da entrambe le reti.

Se l’utente è ancora attivo dopo un check-out riuscito, non verrà disconnesso da Adobe Commerce e [!DNL Bolt].
