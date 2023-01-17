---
title: Onboarding e installazione
description: Scopri come installare [!DNL Catalog Service]
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: e11b4e86efe3483717cf4484a7fcce6e23015f4c
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 0%

---

# Onboarding e installazione

## Prerequisiti

Il processo di onboarding per [!DNL Catalog Service] richiede l&#39;accesso alla riga di comando del server. Se non hai familiarità con l’utilizzo della riga di comando, chiedi aiuto a uno sviluppatore o a un integratore di sistema.

### Requisiti software

- Adobe Commerce 2.4.x
- PHP 8.1, 7.4, 7.3
- Compositore: 2.x, 1.x

### Piattaforme supportate

- Adobe Commerce sull’infrastruttura cloud: 2.4.x
- Adobe Commerce nei locali: 2.4.x

## Ambienti

Sono disponibili due ambienti per l’onboarding:

- Sandbox (https://catalog-service-sandbox.adobe.io/graphql) - utilizzato per il test e la convalida prima della pubblicazione
- Produzione (https://catalog-service.adobe.io/graphql)-) utilizzata per il traffico live per merchandising e siti web di Commerce

## Installazione e configurazione

Per iniziare a usare il servizio Catalogo per Adobe Commerce , sono necessari i seguenti passaggi:

- Installare le estensioni di esportazione dei dati
- Configurare il servizio e l’esportazione dei dati
- Accedere al servizio

### Installare le estensioni di esportazione dei dati

Il processo di onboarding per Catalog Service richiede l&#39;accesso alla riga di comando del server.

L’estensione del servizio catalogo può essere installata sia nell’infrastruttura cloud Adobe Commerce che nelle istanze locali.

Il Servizio catalogo viene installato con le chiavi del Compositore, collegate all’account Commerce [mageid](https://developer.adobe.com/commerce/marketplace/guides/sellers/profile-personal/#field-descriptions) fornito durante il processo di registrazione. Il Compositore utilizza queste chiavi durante l&#39;installazione iniziale di Adobe Commerce o in situazioni in cui le chiavi del Compositore non sono state precedentemente salvate in un `auth.json` file.

Vedi [Ottieni le chiavi di autenticazione](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/prerequisites/authentication-keys.html) per ulteriori informazioni su come ottenere le chiavi Composer.

#### Adobe Commerce su infrastruttura cloud

Utilizza questo metodo per installare l’estensione del servizio catalogo per un’istanza Commerce Cloud.

1. Apri `<Commerce_root>/composer.json` in un editor di testo e aggiorna la sezione richiesta come segue:

   ```json
   "require": {
     "magento/module-saas-catalog": "^101.4.0",
     "magento/module-saas-product-override": "^101.4.0",
     "magento/module-saas-product-variant": "^101.4.0",
     "magento/module-bundle-product-data-exporter": "^101.3.1",
     "magento/module-catalog-data-exporter": "^101.3.1",
     "magento/module-catalog-inventory-data-exporter": "^101.3.1",
     "magento/module-catalog-url-rewrite-data-exporter": "^101.3.1",
     "magento/module-configurable-product-data-exporter": "^101.3.1",
     "magento/module-data-exporter": "^101.3.1",
     "magento/module-parent-product-data-exporter": "^101.3.1",
     "magento/module-product-override-data-exporter": "^101.3.1",
     "magento/data-services": "^7.0.11",
     "magento/services-id": "^3.0.1",
     "magento/services-connector": "1.2.1",
     "magento/module-catalog-service-installer": "1.0.1"
   }
   ```

1. Verifica la nuova configurazione localmente e aggiorna le dipendenze:

```bash
composer update
```

Il comando aggiorna tutte le dipendenze.

1. Conferma e invia le modifiche per `composer.json` e `composer.lock`.

#### Presso i locali

Utilizza questo metodo per installare l’estensione del servizio catalogo per un’istanza locale.

1. Apri `<Commerce_root>/composer.json` in un editor di testo e aggiorna la sezione richiesta come segue:

```json
"require": {
 "magento/module-saas-catalog": "^101.4.0",
 "magento/module-saas-product-override": "^101.4.0",
 "magento/module-saas-product-variant": "^101.4.0",
 "magento/module-bundle-product-data-exporter": "^101.3.1",
 "magento/module-catalog-data-exporter": "^101.3.1",
 "magento/module-catalog-inventory-data-exporter": "^101.3.1",
 "magento/module-catalog-url-rewrite-data-exporter": "^101.3.1",
 "magento/module-configurable-product-data-exporter": "^101.3.1",
 "magento/module-data-exporter": "^101.3.1",
 "magento/module-parent-product-data-exporter": "^101.3.1",
 "magento/module-product-override-data-exporter": "^101.3.1",
 "magento/data-services": "^7.0.11",
 "magento/services-id": "^3.0.1",
 "magento/services-connector": "1.2.1",
 "magento/module-catalog-service-installer": "1.0.1"
}
```

1. Aggiorna le dipendenze e installa l&#39;estensione:

```bash
composer update
```

Il comando aggiorna tutte le dipendenze.

1. Aggiorna Adobe Commerce:

```bash
bin/magento setup:upgrade
```

1. Cancella la cache:

```bash
bin/magento cache:clean
```

### Configurare il servizio e l’esportazione dei dati

Dopo aver installato il Servizio catalogo, devi configurare il [Connettore Commerce Services](https://experienceleague.adobe.com/docs/commerce-merchant-services/experience-platform-connector/fundamentals/install.html?lang=en) specificando le chiavi API e selezionando uno spazio dati SaaS.

Al termine della configurazione SaaS, esegui una sincronizzazione dati iniziale seguendo la guida di sincronizzazione catalogo.

Per verificare che l’esportazione del catalogo sia eseguita correttamente:

- Conferma l’esecuzione dei cron job.
- Verifica che gli indicizzatori siano in esecuzione.
- Assicurati che `Catalog Attributes Feed, Product Feed, Product Overrides Feed`e `Product Variant Feed` Gli indicizzatori sono impostati su &quot;Aggiorna per pianificazione&quot;.

La sincronizzazione iniziale potrebbe richiedere da alcuni minuti a ore a seconda della dimensione del catalogo. Dopo la sincronizzazione iniziale, il Catalogo esporta i dati di prodotto dal server Commerce a Commerce Services su base continuativa per mantenere i servizi aggiornati.

### Accedere al servizio

L’API del servizio catalogo è accessibile tramite i comandi di POST su HTTPS.

Per ottenere la chiave api, vai all’area Commerce Service Connector nell’amministratore e copia la chiave API pubblica.

Leggi la sezione [Documentazione di GraphQL](https://developer.adobe.com/commerce/webapi/graphql/) per scoprire come eseguire query e inviare le intestazioni necessarie per la generazione di richieste API.

## Rete di servizi del catalogo e API

La [Rete API per Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/gateway/overview/) consente agli sviluppatori di integrare API private o di terze parti e altre interfacce con i prodotti Adobe tramite Adobe IO.

Consulta la sezione  [Rete di servizi del catalogo e API](mesh.md) argomento relativo ai dettagli di installazione e configurazione.
