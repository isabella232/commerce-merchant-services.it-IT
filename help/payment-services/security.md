---
title: Sicurezza e conformità
description: Controlla i requisiti di sicurezza e conformità per il tuo sito.
exl-id: 083c5a12-1d78-48b5-b9e3-612b104ce7e0
source-git-commit: 17ba23192fed6cd219411420c5d56b42c94af0f5
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Sicurezza e conformità

La sicurezza è della massima preoccupazione [!DNL Payment Services] e nessuna informazione riservata o regolamentata del settore delle carte di pagamento (PCI) viene trasmessa attraverso il tuo [!DNL Payment Services].

## Sicurezza Commerce

[!DNL Adobe Commerce] e [!DNL Magento Open Source] include il supporto per diverse funzioni di sicurezza.

Vedi [Sicurezza](https://docs.magento.com/user-guide/stores/security.html){target="_blank"} nella guida utente di base per esaminare le best practice relative alla sicurezza e scoprire come gestire le sessioni e le credenziali di amministrazione, implementare CAPTCHA e gestire le restrizioni relative ai siti web.

## Conformità PCI

Il settore delle carte di pagamento (PCI) ha stabilito una serie di requisiti per le aziende che accettano pagamenti con carta di credito su Internet. Oltre a mantenere un ambiente sicuro, i commercianti che gestiscono le informazioni sulle carte di credito dei clienti sono responsabili del rispetto di alcune linee guida standard.

Vedi [Linee guida per la conformità PCI](https://docs.magento.com/user-guide/stores/compliance-pci.html){target="_blank"} per ulteriori informazioni.

I commercianti possono completare un [questionario di autovalutazione (SAQ)](https://www.pcisecuritystandards.org/pci_security/completing_self_assessment){target="_blank"}, che è uno strumento di autoconvalida per valutare la sicurezza dei dati dei titolari della carta.

### Campi carta di credito

Con i campi della carta di credito, nessun dato regolamentato PCI viene trasmesso tra i servizi. Non è necessario archiviare o mantenere tali dati, il che riduce notevolmente i problemi di conformità PCI.

### 3DS

PCI 3-D Secure (3DS) consente l&#39;autenticazione dell&#39;acquirente con l&#39;emittente della carta di credito quando effettua acquisti di carte di credito online. Questo ulteriore livello di sicurezza aiuta a prevenire le frodi online ed è richiesto come parte delle normative di conformità dell&#39;Unione Europea (UE).

[!UICONTROL Payment Services] fornisce funzionalità 3DS per consentire ai commercianti di conformarsi alle normative UE e proteggere i clienti e i commercianti da attività fraudolente nei loro negozi.

Se sei un commerciante all&#39;interno dell&#39;UE o della Gran Bretagna dove è richiesta la conformità 3DS, devi attivare manualmente 3DS (è `Off` per impostazione predefinita, in [Impostazioni](settings.md#credit-card-fields).

Gli ordini immessi per l&#39;acquirente dal personale del commerciante/del negozio non sono configurati con misure di conformità 3DS.

Vedi [3DS nelle impostazioni](settings.md#3ds) per ulteriori informazioni.

### Vaulting delle schede

Quando un acquirente [vaults o &quot;salva&quot; le loro informazioni sulla carta di credito](vaulting.md) per gli acquisti futuri nei vostri negozi, le informazioni minime sulla carta di credito vengono condivise con l&#39;acquirente (ultime quattro cifre, data di scadenza della carta e marca della carta). Le informazioni sulla carta di credito vengono memorizzate con il provider di pagamento. Quando una carta scade o non ha più bisogno delle informazioni salvate, può cancellare quel token in modo che le informazioni non vengano più memorizzate dal provider di pagamento.

Vedi [Archiviazione carte di credito](vaulting.md) per ulteriori informazioni.

### Pulsanti avanzati PayPal

Con i pulsanti Smart PayPal, nessun dato regolamentato PCI viene trasmesso tra i servizi. Non è necessario archiviare o mantenere tali dati, il che riduce notevolmente i problemi di conformità PCI.

Per motivi di sicurezza, PayPal non trasmette l&#39;indirizzo di fatturazione durante il pagamento: paese, e-mail e nome è l&#39;unica informazione di fatturazione utilizzata. Facoltativamente, puoi abilitare il pagamento del tuo sito per restituire l&#39;indirizzo di fatturazione completo contattando PayPal e completando un processo di verifica.

PayPal ha anche una protezione integrata contro le frodi che utilizza l&#39;apprendimento automatico per aiutarti a combattere le frodi. Vedi PayPal&#39;s [Documentazione sulla protezione del venditore](https://www.paypal.com/us/webapps/mpp/security/seller-protection) per ulteriori informazioni.
