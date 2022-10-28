---
title: Gestire le limitazioni dei cookie
description: Scopri come i consigli di prodotto gestiscono le restrizioni relative ai cookie.
source-git-commit: 81ab2e22b0ec81e97d27ee135c88b50731a3986d
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Gestire le limitazioni dei cookie

Sia Adobe Commerce che il Magento Open Source richiedono il consenso prima che i dati vengano memorizzati nei cookie del browser. Per ulteriori informazioni, consulta [Modalità di restrizione dei cookie](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html).

Quando distribuisci `magento/product-recommendations` modulo in produzione, inizia a raccogliere gli eventi di interazione dell&#39;acquirente sulla vetrina. Poiché i dati per questi eventi possono essere memorizzati nei cookie del browser o nell’archiviazione locale, la funzione supporta la modalità di restrizione dei cookie non raccogliendo gli eventi finché l’acquirente non ha dato il consenso ai cookie.

Questo potrebbe non funzionare con soluzioni di consenso dei cookie di terze parti. È responsabilità di ogni commerciante garantire che la raccolta dei dati non avvenga prima che sia stato dato il consenso ai cookie, come spesso richiesto dalla legge. Se gestisci il consenso dei cookie con codice personalizzato, puoi utilizzare un cookie non-track chiamato `mg_dnt` limitare la raccolta di dati.

- Nome del cookie:

   ```text
   `const DNT_COOKIE = "mg_dnt";`
   ```

- Imposta il cookie do-not-track per disabilitare la raccolta dati:

   ```text
   `$.mage.cookies.set(DNT_COOKIE, true);`
   ```

- Per cancellare il cookie quando l’utente accetta i cookie:

   ```text
   `$.mage.cookies.clear(DNT_COOKIE);`
   ```
