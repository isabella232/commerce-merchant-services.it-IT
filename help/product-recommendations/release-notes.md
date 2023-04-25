---
title: '''[!DNL Product Recommendations] Note sulla versione"'
description: Informazioni aggiornate sulla versione di [!DNL Product Recommendations] da Adobe Commerce.
exl-id: 1758e688-d26f-45e7-818c-d4726338a6c3
source-git-commit: 5b6a3c2dc15d41e5245cbf62ed736022f48281fa
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 0%

---

# [!DNL Product Recommendations] Note sulla versione

Le note sulla versione contengono aggiornamenti a quanto segue [!DNL Product Recommendations] moduli:

* [!DNL Product Recommendations] metapackage: `magento/product-recommendations`
* Supporto di Page Builder in [!DNL Product Recommendations] (facoltativo) modulo: `magento/module-page-builder-product-recommendations`
* Supporto per tipi di raccomandazione per similarità visiva per [!DNL Product Recommendations] (facoltativo) modulo: `magento/module-visual-product-recommendations`

Le note sulla versione includono:

![Nuovo](../assets/new.svg) Nuove funzioni
![Correzione](../assets/fix.svg) Correzioni e miglioramenti

Consulta la documentazione per gli sviluppatori su [informazioni sulla compatibilità dei prodotti](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).

## Versione principale corrente

_25 aprile 2023_

![Nuovo](../assets/new.svg) I clienti Recommendations possono ora sfruttare [Indicizzazione dei prezzi SaaS](../price-index/index.md).

### 5.0.0 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stato aggiornato Product Recommendations per supportare Adobe Commerce 2.4.6.
![Nuovo](../assets/new.svg) Questa è una versione principale. [Modifica](install-configure.md#update) radice `composer.json` per il progetto.

#### Limitazioni note

* La `websiteCode` viene restituito in modo non corretto se contiene un carattere di sottolineatura (_).

### Versioni precedenti

+++4.0.1 e versioni precedenti

### 4.0.1 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) In precedenza, il Recommendations prodotto mostrava un errore quando la valuta di visualizzazione veniva convertita in una valuta non predefinita. Il cambio di valuta ora funziona correttamente.

### 4.0.0 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Aggiunto [indicatori di preparazione](create.md) per visualizzare l&#39;avanzamento del training di ciascun tipo di raccomandazione.
![Nuovo](../assets/new.svg) Questa è una versione principale. [Modifica](install-configure.md#update) radice `composer.json` per il progetto. Questa versione richiede anche di fornire due chiavi API durante l’installazione e la configurazione del Product Recommendations: [una chiave di produzione e una chiave sandbox](../landing/saas.md).

#### Limitazioni note

* La `websiteCode` viene restituito in modo non corretto se contiene un carattere di sottolineatura (_).

### 3.3.7 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stato aggiunto il supporto per PHP 8.1
![Nuovo](../assets/new.svg) È stato migliorato il ridimensionamento delle immagini in modo che il ridimensionamento delle immagini sia gestito in modo più coerente nel modello di visualizzazione di riferimento

### 3.3.6 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Ottimizzato [!DNL Product Recommendations] metapackage elencando esplicitamente le dipendenze

### 3.3.5 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Aggiunto [Supporto B2B](onboarding.md#b2bsupport) in Recommendations prodotto
![Nuovo](../assets/new.svg) Sono stati aggiunti nuovi feed a [sincronizzare i dati del catalogo](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/data-services/catalog-sync.html) a Commerce Services tramite la riga di comando

### 3.3.3 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Aggiunto nuovo [tipi di raccomandazione](type.md): Conversione (visualizzazione al carrello), Conversione (visualizzazione all’acquisto) e Visualizzata di recente. Questi nuovi tipi di consigli sono disponibili nella sezione `magento/product-recommendations` modulo 3.2.2 e versioni successive.
![Correzione](../assets/fix.svg) È stato risolto un problema che impediva in modo errato il blocco di un cookie da parte del firewall per applicazioni Web di Flast (WAF)
![Correzione](../assets/fix.svg) È stato risolto un problema a causa del quale i prodotti assegnati alla visualizzazione archivio non predefinita non venivano visualizzati nel _Anteprima del prodotto Recommendations_ durante la creazione di una raccomandazione per la visualizzazione archivio specifica
![Correzione](../assets/fix.svg) È stato risolto un problema a causa del quale alcuni nomi di unità di raccomandazione in Page Builder impedivano la visualizzazione dell&#39;unità di raccomandazione sulla vetrina

### 3.3.2 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) È stata corretta la dipendenza mancante per il supporto B2B

### 3.3.1 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stato aggiunto il supporto per i prezzi per gruppi di clienti B2B. Quando imposti un [filtro a prezzi](filters.md) su un&#39;unità di raccomandazione, i clienti B2B che hanno effettuato l&#39;accesso visualizzano i prezzi del gruppo di clienti impostati per i prodotti visualizzati.

### 3.3.0 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stato aggiunto il supporto per Adobe Client Data Layer per standardizzare la raccolta di dati comportamentali tra le funzioni e i servizi Adobe Commerce. Consulta la sezione [leggimi](https://github.com/adobe/magento-storefront-event-collector/blob/main/README.md) per saperne di più.

### 3.2.6 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) È stato corretto un errore modale JavaScript
![Correzione](../assets/fix.svg) È stato risolto un problema che impediva in modo errato il blocco di un cookie da parte del firewall per applicazioni Web di Flast (WAF)

### 3.2.5 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Servizi Magento rinominati in [Commerce Services](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html) e una migliore usabilità in Admin

### 3.2.4 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) È stato corretto l’errore &quot;Impossibile recuperare i dati delle opzioni di prodotto configurabili&quot; durante l’indicizzazione degli attributi di prodotto

### 3.2.3 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) È stato corretto l’errore &quot;Impossibile recuperare i dati configurabili delle opzioni di prodotto&quot; durante la sincronizzazione del catalogo
![Correzione](../assets/fix.svg) È stato risolto un problema a causa del quale il codice store non veniva impostato correttamente quando si attivava la configurazione &quot;Aggiungi codice store all’URL&quot;
![Correzione](../assets/fix.svg) È stato migliorato il rilevamento delle modifiche di configurazione del pannello di amministrazione per garantire che queste modifiche si riflettano nei dati di sincronizzazione del catalogo

### 3.2.2 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Aggiunta la possibilità di [visualizzare in anteprima i risultati della raccomandazione](create.md) al momento della creazione. Potrebbe essere necessario aggiornare il modulo alla versione più recente.
![Nuovo](../assets/new.svg) Aggiunta la possibilità di [monitorare e gestire](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/data-services/catalog-sync.html) il processo di sincronizzazione del catalogo da Admin.
![Nuovo](../assets/new.svg) Aggiunto [filtri](filters.md) per controllare quali prodotti vengono visualizzati nei consigli.
![Nuovo](../assets/new.svg) È stato aggiunto il [Somiglianza visiva](type.md#visualsim) tipo di raccomandazione.

### 1.2.1 di magento/module-page-builder-product-recommendations per Page Builder

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stato aggiunto il supporto per la versione 3.2.0+ di `magento/product-recommendations` modulo

### 3.1.0 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Aggiunta la possibilità di [resync](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/data-services/catalog-sync.html) il catalogo ai servizi SaaS tramite la riga di comando.
![Nuovo](../assets/new.svg) È stato aggiunto il supporto per i prefissi delle tabelle del database.
![Correzione](../assets/fix.svg) Supporto PHP 7.1 rimosso

### 3.0.8 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) È stato risolto un problema a causa del quale gli eventi venivano inviati per la raccolta dati prima della configurazione del modulo, causando traffico non valido

### 3.0.6 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) **(Beta)** Include il supporto per i nuovi [Somiglianza visiva](type.md#visualsim) tipo di raccomandazione.

### 1.0.0 di magento/module-visual-product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) **(Beta)** [Somiglianza visiva](type.md#visualsim). Con la _Somiglianza visiva_ tipo di raccomandazione, potete distribuire un&#39;unità di raccomandazione alla pagina dei dettagli del prodotto che visualizza prodotti visivamente simili al prodotto visualizzato.

### 3.0.5 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) È stato corretto l’errore &quot;Impossibile recuperare i dati delle opzioni prodotto&quot; che poteva verificarsi durante l’esportazione del catalogo.
![Correzione](../assets/fix.svg) Il simbolo di valuta nel _Entrate_ nella colonna _Recommendations di prodotto_ il dashboard ora riflette correttamente la valuta di base configurata.

### 3.0.4 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) È stato aggiunto il supporto per Adobe Commerce 2.4.0

### 3.0.3 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Correzione](../assets/fix.svg) Implementazione dei simboli migliorata nel modello di vetrina

### 1.0.4 di magento/module-page-builder-product-recommendations per Page Builder

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stato aggiunto il nome della raccomandazione del prodotto durante la modifica del tipo di contenuto Page Builder

### 3.0.2 magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) È stata aggiunta una colonna di stato sulla griglia quando si selezionano le unità Consigli in Page Builder
![Correzione](../assets/fix.svg) È stato risolto un problema relativo ai protocolli http/https errati negli URL di prodotti e immagini

### 3.0.1 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

Questa è una versione principale. [Modifica](install-configure.md#update) file composer.json principale del progetto.

![Nuovo](../assets/new.svg) Recupero [!DNL Product Recommendations] da spazi di dati SaaS alternativi. Questo consente di utilizzare i consigli di prodotto calcolati nell’ambiente di prodotto su altri ambienti non di produzione. [Commutazione degli spazi dati SaaS](settings.md) descrive ulteriormente questa funzione.

![Correzione](../assets/fix.svg) È stato risolto un problema a causa del quale il pagamento veniva bloccato per gli acquirenti che utilizzavano uBlock Origin
![Correzione](../assets/fix.svg) È stato risolto un problema relativo all’invio di eventi aggiuntivi estranei al carrello

### 1.0.3 di magento/module-page-builder-product-recommendations per Page Builder

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Supporto di Page Builder. Con l’integrazione di Page Builder, è possibile posizionare in modo preciso e granulare le unità di Recommendations in qualsiasi posizione arbitraria sui contenuti creati da Page Builder. Potete inoltre assegnare loro lo stile per le intestazioni e le unità dei consigli. Vai a [Page Builder](https://experienceleague.adobe.com/docs/commerce-admin/page-builder/add-content/recommendations.html) per ulteriori informazioni.

### 2.0.0 di magento/product-recommendations

[!BADGE Compatibilità]{type=Informative tooltip="Compatibilità"}

![Nuovo](../assets/new.svg) Versione generale di disponibilità

+++

## Documentazione

Per ulteriori informazioni [!DNL Product Recommendations] e [!DNL Product Recommendations] sviluppo:

* [Guida utente](overview.md)
* [Documentazione per gli sviluppatori](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/development-overview.html)
