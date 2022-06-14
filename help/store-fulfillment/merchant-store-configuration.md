---
title: Configurazione dell’archivio merchant
description: 'È stata migliorata la configurazione delle sorgenti Inventory management come negozi commerciali. '
role: User, Admin
level: Intermediate
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '1209'
ht-degree: 0%

---

# Configurazione Negozi Merchant (Origine)

Questa soluzione migliora le funzionalità native di Inventory management estendendo le sorgenti di stock con funzionalità orientate alle operazioni per i commercianti.

- Aggiungi coordinate geografiche per la posizione dello store
- Designare l’origine come [!DNL Store Pickup Location] e specificare le capacità di spedizione disponibili (Spedisci al negozio, Spedizione dal negozio)
- Specifica le opzioni di ritiro disponibili (in negozio o a bordo del nastro), le istruzioni di ritiro personalizzate e altre informazioni per comunicare i dettagli del ritiro e le istruzioni ai clienti

I termini _source_ e _luogo del negozio commerciale_ sono utilizzati in modo intercambiabile. Tutti i record sono origini di inventario, ma le origini possono essere anche posizioni di negozio mercantili, a seconda delle impostazioni di configurazione.

Gestisci la configurazione di Merchant Stores dall&#39;amministratore: **[!UICONTROL Stores > Inventory > Sources >  Edit Source]**.

>[!NOTE]
>
>Durante il processo di configurazione, potrebbe essere necessario svuotare la cache dopo aver creato sorgenti o aggiornato sorgenti esistenti.

## **Generale**

<table>
<tbody>
<tr>
<th>Campo</th>
<th>Descrizione</th>
<th>Ambito</th>
<th>Obbligatorio</th>
</tr>
<tr>
<td><strong>[!UICONTROL Latitude]</strong></br><code>Base Attribute: latitude</code></td>
<td>Coordinata longitudinale della posizione del negozio mercantile. Queste informazioni richieste vengono utilizzate nella ricerca di posizione e nella posizione della mappa nell’esperienza di vetrina. Per passare la convalida, il valore deve corrispondere all'indirizzo esatto dell'archivio.</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Longitude]</strong></br><code>Base Attribute: Longitude</code></td>
<td>Coordinata longitudinale della posizione del negozio commerciale. Queste informazioni richieste vengono utilizzate nella ricerca di posizione e nella posizione della mappa nell’esperienza di vetrina. Per passare la convalida, il valore deve corrispondere all'indirizzo esatto dell'archivio.</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Use as Pickup Location]</br></strong><code>Base Attribute: is_pickup_location_active</code></td>
<td>Designa l'origine come posizione di prelievo del Negozio disponibile. Questa impostazione determina se l’origine viene sincronizzata e visualizzata ai visitatori.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship to Store]</strong><br><code>Extension Attribute: allow_ship_to_store</code></td>
<td>Configura le funzionalità di spedizione-archiviazione a livello di origine. Per ulteriori informazioni, consulta l’opzione [Configurazione generale](enable-general.md), <strong>[!UICONTROL Enable Ship To Store]
</tr>
<tr>
<td><strong>[!UICONTROL Latitude]</strong></br><code>Base Attribute: latitude</code></td>
<td>Coordinata longitudinale della posizione del negozio mercantile. Queste informazioni richieste vengono utilizzate nella ricerca di posizione e nella posizione della mappa nell’esperienza di vetrina. Per passare la convalida, il valore deve corrispondere all'indirizzo esatto dell'archivio.</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Longitude]</strong></br><code>Base Attribute: Longitude</code></td>
<td>Coordinata longitudinale della posizione del negozio commerciale. Queste informazioni richieste vengono utilizzate nella ricerca di posizione e nella posizione della mappa nell’esperienza di vetrina. Per passare la convalida, il valore deve corrispondere all'indirizzo esatto dell'archivio.</td>
<td>Globale</td>
<td>Sì</td>
</tr>
<tr>
<td><strong>[!UICONTROL Use as Pickup Location]</br></strong><code>Base Attribute: is_pickup_location_active</code></td>
<td>Designa l'origine come posizione di prelievo del Negozio disponibile. Questa impostazione determina se l’origine viene sincronizzata e visualizzata ai visitatori.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship to Store]</strong></br> <code>Extension Attribute: [!DNL allow_ship_to_store]</code></td>
<td>Configura le funzionalità di spedizione-archiviazione a livello di origine. Per ulteriori informazioni, consulta l’opzione [Configurazione generale](enable-general.md), <strong>[!UICONTROL Enable Ship To Store]</strong>.</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship From Store]</strong></br><code>Extension Attribute: [!DNL use_as_shipping_source]</code></td>
 <td>Configura le funzionalità di spedizione dall'archivio a livello di origine. Per ulteriori informazioni, consulta l’opzione [Configurazione generale](enable-general.md), [!UICONTROL Enable Ship From Store].</td>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td>Globale</td>
<td>No</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship From Store]</strong><code>Extension Attribute: [!DNL use_as_shipping_source]</code></td><td></td><td></td><td></td></tr></tbody></table>



| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Latitude]**</br>`Base Attribute: latitude` | Coordinata longitudinale della posizione del negozio mercantile. Queste informazioni richieste vengono utilizzate nella ricerca di posizione e nella posizione della mappa nell’esperienza di vetrina. Per passare la convalida, il valore deve corrispondere all&#39;indirizzo esatto dell&#39;archivio. | Globale | Sì |
| **[!UICONTROL Longitude]**</br>`Base Attribute: Longitude` | Coordinata longitudinale della posizione del negozio commerciale. Queste informazioni richieste vengono utilizzate nella ricerca di posizione e nella posizione della mappa nell’esperienza di vetrina. Per passare la convalida, il valore deve corrispondere all&#39;indirizzo esatto dell&#39;archivio. | Globale | Sì |
| **[!UICONTROL Use as Pickup Location]**</br>`Base Attribute:[!DNL is_pickup_location_active]` | Designa l&#39;origine come posizione di prelievo del Negozio disponibile. Questa impostazione determina se l’origine viene sincronizzata e visualizzata ai visitatori. | Globale | No |
| **[!UICONTROL Enable Ship to Store]**</br>`Extension Attribute: [!DNL allow_ship_to_store]` | Configura le funzionalità di spedizione-archiviazione a livello di origine. Per ulteriori informazioni, consulta la sezione [Configurazione generale](enable-general.md) opzione, **[!UICONTROL Enable Ship To Store]**. | Globale | No |
| **[!UICONTROL Enable Ship From Store]**</br>`Extension Attribute: [!DNL use_as_shipping_source]` | Configura le funzionalità di spedizione dall&#39;archivio a livello di origine. Per ulteriori informazioni, consulta la sezione [Configurazione generale](enable-general.md) opzione, [!UICONTROL Enable Ship From Store] | Globale | No |

{style=&quot;table-layout:auto&quot;}

## Configurazione della posizione del pickup

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|-----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Allow In-Store Pickup]**</br>`Extension Attribute: [!DNL store_pickup_enabled]` | Una delle due opzioni di ritiro. [!DNL In-Store Pickup] si riferisce alla capacità di consentire a un cliente di entrare nella posizione del negozio di merchant per recuperare il loro ordine. </br></br>Se abilitata, questa opzione potrebbe essere presentata al cliente durante il pagamento. </br></br>Questa opzione sostituisce anche la configurazione globale in [!UICONTROL Enable In-store Pickup] configurato nel [!UICONTROL Delivery Method] per [!UICONTROL In-store Pickup] | Globale | No |
| **Istruzioni per il caricamento nello store**</br>`Extension Attribute: store_pickup_instructions` | Un messaggio personalizzabile consegnato al cliente nel **Ordine pronto per il ritiro nel negozio** notifica via e-mail. | Globale | No |
| **Consenti Curbside**</br>`Extension Attribute: curbside_enabled` | Una delle due opzioni di ritiro. Curbside delivery consente a un cliente di parcheggiare il proprio veicolo in un posto designato al negozio commerciale. In questo caso, l&#39;ordine viene consegnato al cliente da un associato del negozio. </br></br>Se abilitata, questa opzione può essere presentata al cliente durante il pagamento. Inoltre, al cliente potrebbe essere chiesto di descrivere il proprio veicolo e posto di parcheggio durante il processo di check-in. </br></br>Questa opzione sostituisce anche la configurazione globale in **Abilita ritocco urbano** configurato nel **Metodo di consegna** per **Caricamento in-store** | Globale | No |
| **[!UICONTROL Curbside Instructions]**</br>`Extension Attribute: curbside_instructions` | Un messaggio personalizzabile consegnato al cliente nel [!UICONTROL Order Ready For Pickup in Store] notifica via e-mail. | Globale | No |
| **[!UICONTROL Estimated Pickup Lead Time]**</br>`Extension Attribute: pickup_lead_time` | Il numero di minuti necessari prima che un ordine venga ricevuto, selezionato e pronto per essere prelevato. </br></br>Queste informazioni vengono utilizzate per visualizzare i tempi stimati per il ritiro degli ordini ai clienti sul sito web.</br></br> L’impostazione di questa opzione sostituisce la configurazione globale per **Lead time di recupero stimato** configurato per **Metodo di consegna** in **Caricamento in-store** configurazione. | Globale | No |
| **[!UICONTROL Estimated Pickup Time Label]**</br>`Extension Attribute: pickup_time_label` | Etichetta che visualizza il numero di minuti fino a quando un ordine è pronto per essere raccolto.</br></br> Quando si personalizza questa etichetta, è possibile utilizzare il codice %1 per inserire il **Lead time di recupero stimato**.</br></br> L’impostazione di questa opzione sostituisce la configurazione globale per [!UICONTROL Estimated Pickup Time Label] configurato per [!UICONTROL Delivery Method] in [!UICONTROL In-store Pickup]. | Globale | No |

### **Orario di apertura**

| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Location Timezone]**</br>`Extension Attribute: timezone` | Il fuso orario della posizione del negozio commerciale. Per ogni giorno, impostare gli orari di apertura e chiusura.</br></br>Queste impostazioni vengono utilizzate per ottimizzare i tempi di ritiro stimati e i rapporti sul servizio di evasione. | Globale | Sì |
| **[!UICONTROL Opening Hours]**</br>`Internal Attribute: inventory_source_opening_hours_dynamic_rows` | Gli orari di operatività per la posizione del negozio commerciale. </br></br>Queste informazioni possono essere utilizzate per ottimizzare i tempi di ritiro stimati e i rapporti sul servizio di evasione. | Globale | Sì |

### Configurare le opzioni dell’interfaccia di Check-in Experience



| **Campo** | **Descrizione** | **Ambito** | **Obbligatorio** |
|---------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Use Parking Spots]**</br>`Extension Attribute: parking_spots_enabled` | Specifica se la posizione del negozio commerciale dispone di aree di parcheggio a designazione per il ritiro del curbside. </br></br>Quando abilitato, è possibile configurare le aree di parcheggio disponibili. | Globale | No |
| **[!UICONTROL Is Parking Spot a Mandatory Field?]**</br>`Extension Attribute: parking_spot_mandatory` | Specifica se l’identificazione del parcheggio è necessaria per i clienti durante l’esperienza di acquisto.</br></br>Se attivato, al cliente viene richiesto di specificare il posto di parcheggio al momento dell&#39;arrivo. Se disabilitata, il cliente può saltare questo input. | Globale | No |
| **[!UICONTROL Parking Spots List]**</br> `Internal Attribute: inventory_source_parking_spot_dynamic_rows` | I posti auto disponibili in questo negozio commerciale posizione per il ritiro dei curbside. Utilizza l’interfaccia fornita per assegnare un nome a ogni punto.</br></br> Non è necessario indicare ogni posto di parcheggio, solo i posti designati per il bordo del marciapiede. Ad esempio, si possono avere file A-G di parcheggio disponibili, ma solo i primi 8 punti della riga A sono designati per il ritiro a bordo del marciapiede. In questo scenario, puoi definire 8 punti; ex: A1, A2, A3 e così via. | Globale | No |
| **[!UICONTROL Allow "Other" Parking Spot Field]**</br>`Extension Attribute: custom_parking_spot_enabled` | Quando abilitata, questa impostazione consente al cliente di descrivere il proprio parcheggio durante il Check-In. | Globale | No |
| **[!UICONTROL Use Car Color]**</br>`Extension Attribute: use_car_color` | Specifica se supportare la raccolta del colore del veicolo dal cliente durante il Check-In. </br></br> Le selezioni disponibili per [!UICONTROL Car Color] sono configurati nell&#39;amministratore [impostazioni di sistema per l’esperienza di archiviazione](check-in-experience-setup.md). | Globale | No |
| **[!UICONTROL Is Car Color a Mandatory Field?]**</br>`Extension Attribute: car_color_mandatory` | Specificare se l&#39;identificazione del colore del veicolo è necessaria per i clienti durante il Check-In.</br></br>Se attivato, al cliente viene richiesto di specificare il colore del veicolo all&#39;arrivo. Se disabilitata, il cliente può saltare questo input. | Globale | No |
| **[!UICONTROL Use Car Make]** </br>`Extension Attribute: use_car_make` | Specifica se supportare la raccolta di prodotti del veicolo dal cliente durante il Check-In.</br></br> Le selezioni disponibili per [!UICONTROL Car Make] sono configurati nell&#39;amministratore [impostazioni di sistema per l’esperienza di archiviazione](check-in-experience-setup.md). | Globale | No |
| **[!UICONTROL Is Car Make a Mandatory Field?]**</br>`Extension Attribute: car_make_mandatory` | Specificare se l&#39;identificazione del veicolo è necessaria per i clienti durante il Check-In.</br></br>Se attivato, al cliente viene richiesto di specificare la marca del proprio veicolo all&#39;arrivo. Se disabilitata, il cliente può saltare questo input. | Globale | No |
| **[!UICONTROL Use Additional Information]**</br> `Extension Attribute: use_additional_information` | Specifica se supportare la raccolta di informazioni aggiuntive dal cliente durante il Check-In. | Globale | No |
| **[!UICONTROL Is Additional Information a Mandatory Field?]**</br>`Extension Attribute: additional_information_mandatory` | Specifica se sono necessarie informazioni aggiuntive per i clienti durante il Check-In. </br></br>Se attivato, al cliente viene richiesto di inserire ulteriori informazioni all’arrivo. Se disabilitata, il cliente può saltare questo input. | Globale | No |







