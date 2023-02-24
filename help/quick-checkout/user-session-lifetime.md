---
title: Durata della sessione utente
description: L’amministratore offre la possibilità di configurare la durata dei cookie dell’utente Adobe Commerce per [!DNL Quick Checkout] estensione.
exl-id: 32cf5d70-9a50-49ca-8b40-5f04bc1e24b7
source-git-commit: b89427124cf76e7f36076454949191ee1d88f52c
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Ciclo di vita della sessione utente

La durata di una sessione dell’acquirente è determinata da diversi fattori, che possono essere configurati nel tuo amministratore Adobe Commerce. Vedi [Configura la durata del cookie](https://experienceleague.adobe.com/docs/commerce-admin/customers/customer-accounts/configure/customer-online-options.html){target=_blank} per ulteriori informazioni.

La durata configurata dei cookie può influenzare [!DNL Quick Checkout] se:

1. A causa di inattività, l’acquirente viene disconnesso da Adobe Commerce.
1. La [!DNL Bolt] la sessione scade.

Se un acquirente effettua un ordine quando il suo [!DNL Bolt] la sessione scade, l&#39;ordine viene posizionato correttamente ma l&#39;utente viene disconnesso da entrambe le reti.

Se l’utente è ancora attivo dopo un’uscita corretta, non verrà disconnesso sia da Adobe Commerce che da [!DNL Bolt].
