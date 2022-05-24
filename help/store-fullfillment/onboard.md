---
title: A bordo "[!DNL Store Fulfillment]"
description: Collega la tua istanza Commerce a [!DNL Store Fulfillment Manager] per completare alcune fasi di onboarding.
role: User, Admin
level: Intermediate
source-git-commit: 24639b75d3c629856fbb8fc74e7eb072d4197815
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---


# Evasione a bordo del negozio da Walmart Technologies

Implementazione dell’archivio a bordo installando l’estensione sull’istanza Commerce e configurando le connessioni API. Queste connessioni consentono la comunicazione e la sincronizzazione dei dati tra l’istanza Commerce, i sistemi di terze parti per la gestione dell’inventario e l’app Store Assist.

Dopo aver completato l’onboarding, configura e gestisci la soluzione dall’amministratore Commerce

![[!DNL Store Fulfillment Service] configurazione in Admin view](assets/store-fulfillment-admin-home.png)

## Panoramica sull’onboarding

1. Installa l&#39;estensione Store Fulfillment di Walmart Technologies per Adobe Commerce.

1. Dall’amministratore, abilita la soluzione e la configurazione generale completa per l’integrazione, le sue funzioni attive e completa il modulo di assunzione per la connessione ai servizi di evasione.

1. Configura i metodi di consegna.

1. Imposta le origini come archivi fisici e configura i prodotti nel catalogo.

1. Seleziona e configura i modelli e-mail per gestire le comunicazioni dei clienti per le transazioni di acquisto online, ritiro in negozio (BOPIS).

1. Crea utenti e ruoli per l&#39;app Store Assist.

1. Configura le pianificazioni per i processi in background per sincronizzare i dati al servizio di evasione.

## Prerequisiti

* **Informazioni sull’account Commerce**- Download e installazione [!DNL Channel Manager] richiede un [Account Commerce](https://docs.magento.com/user-guide/magento/magento-account.html){target=&quot;_blank&quot;}. È necessario un ID account e le credenziali con accesso Proprietario o Amministratore al [!DNL Adobe Commerce] o [!DNL Magento Open Source] istanza.

* Per [!DNL Adobe Commerce] nei progetti di infrastruttura cloud, i programmi di installazione del software devono avere i seguenti accessi [!DNL Commerce] istanza:

   * Accesso utente privilegiato al progetto Cloud
   * Accesso dell’amministratore a un ambiente specifico
   * Un [!DNL Adobe Commerce] o [!DNL Magento Open Source] account con autorizzazioni per accedere all&#39;archivio Composer

      Vedi [Gestire l’accesso utente](https://devdocs.magento.com/cloud/project/user-admin.html).

* **Accesso all&#39;archivio software Store Fulfillment di Walmart Technologies per installare la soluzione Store Fulfillment sulla tua istanza Adobe Commerce**- Il rappresentante del tuo account cliente può fornire accesso al file di installazione dell&#39;estensione.

* **Esperienza con Compositore e[!DNL Commerce CLI]** -Vedi [Installazione generale CLI](https://devdocs.magento.com/extensions/install/){target=&quot;_blank&quot;} per informazioni sull&#39;utilizzo di questi strumenti per installare e gestire le estensioni in [!DNL Adobe Commerce] e [!DNL Magento Open Source] piattaforme.

* [!DNL Inventory Management] estensione per Adobe Commerce e Magenti Open Source

   È necessario che l’estensione Inventory management sia installata e abilitata nell’istanza Adobe Commerce e Magenti Open Source. In genere, questa estensione viene installata e abilitata per impostazione predefinita in Adobe Commerce e Magenti Open Source 2.3.x e versioni successive. Per ulteriori informazioni, consulta [Installare Inventory management](https://devdocs.magento.com/extensions/inventory-management/) nella documentazione per sviluppatori di Adobe Commerce.

## Requisiti

La soluzione Store Fulfillment è disponibile per i clienti Adobe Commerce e Magenti Open Source. Devi soddisfare i seguenti requisiti di sistema e aziendali per installare, distribuire e utilizzare la soluzione.

### Requisiti di sistema

L&#39;estensione Store Fulfillment di Walmart Technologies è stata testata per verificare la compatibilità con le seguenti versioni software.

**Compatibilità software**

| **Software** | **Versione minima** | **Versione massima** |
|----------------|---------------------|---------------------|
| Adobe Commerce | 2.4.0 | 2.4.4 |
| Compositore | 1.x | 2.x |
| MariaDB | 10,2 | 10,4 |
| MySQL | 5,7 | 8,0 |
| PHP | 7.4 | 8.1 |

Per requisiti dettagliati, consulta Adobe Commerce [Requisiti di sistema](https://devdocs.magento.com/guides/v2.4/install-gde/system-requirements.html) nella documentazione per sviluppatori.

### Requisiti aziendali

Per implementare la soluzione Store Fulfillment, la tua azienda deve soddisfare i seguenti criteri minimi.

* Azienda con sede negli Stati Uniti

* Rivenditori B2C, produttori di CPG che vendono D2C o distributori che vendono D2C o a piccole imprese

* Almeno un negozio fisico o un magazzino

* Gestisci l’inventario dei prodotti con Inventory management for Commerce (era MSI)

* Capacità di diffondere l&#39;inventario dei commercianti

* Disponibilità Wi-Fi in tutti i punti che supportano la soluzione Store Fulfillment

* I collaboratori del negozio e del magazzino possono accedere ai dispositivi mobili iOS o Android durante i loro spostamenti, personali o forniti dal commerciante

* I prodotti gestiti tramite la soluzione Store Fulfillment devono avere attributi di prodotto che includono un prodotto SKU o UPC.

### Piattaforme supportate

* Adobe Commerce on Cloud (ECE) : 2.4.x
* Adobe Commerce nei locali (EE) : 2.4.x
* Magenti Open Source 2.4.x
