---
title: Sicurezza e conformità
description: Controlla i requisiti di sicurezza e conformità per il tuo sito.
exl-id: 083c5a12-1d78-48b5-b9e3-612b104ce7e0
source-git-commit: bcb817775fe9cd9ac7096931dd40d5ec0c4a5cfc
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# Sicurezza e conformità

La sicurezza è della massima preoccupazione [!DNL Payment Services] e nessuna informazione riservata o regolamentata del settore delle carte di pagamento (PCI) viene trasmessa attraverso il tuo [!DNL Payment Services].

## Sicurezza Commerce

Adobe Commerce e Magenti Open Source includono il supporto per diverse funzioni di sicurezza.

Vedi [Sicurezza](https://docs.magento.com/user-guide/stores/security.html){target=&quot;_blank&quot;} nella guida utente principale per esaminare le best practice relative alla sicurezza e imparare a gestire le sessioni e le credenziali di amministrazione, implementare CAPTCHA e gestire le restrizioni relative al sito web.

## Conformità PCI

Il settore delle carte di pagamento (PCI) ha stabilito una serie di requisiti per le aziende che accettano pagamenti con carta di credito su Internet. Oltre a mantenere un ambiente sicuro, i commercianti che gestiscono le informazioni sulle carte di credito dei clienti sono responsabili del rispetto di alcune linee guida standard.

Vedi [Linee guida per la conformità PCI](https://docs.magento.com/user-guide/stores/compliance-pci.html){target=&quot;_blank&quot;} per ulteriori informazioni.

I commercianti possono completare un [questionario di autovalutazione (SAQ)](https://www.pcisecuritystandards.org/pci_security/completing_self_assessment){target=&quot;_blank&quot;}, strumento di autoconvalida per valutare la sicurezza dei dati del titolare della carta.

### Campi carta di credito

Con i campi della carta di credito, nessun dato regolamentato PCI viene trasmesso tra i servizi. Non è necessario archiviare o mantenere tali dati, il che riduce notevolmente i problemi di conformità PCI.

### Pulsanti avanzati PayPal

Con i pulsanti Smart PayPal, nessun dato regolamentato PCI viene trasmesso tra i servizi. Non è necessario archiviare o mantenere tali dati, il che riduce notevolmente i problemi di conformità PCI.

Per motivi di sicurezza, PayPal non trasmette l&#39;indirizzo di fatturazione durante il pagamento: paese, e-mail e nome è l&#39;unica informazione di fatturazione utilizzata. Facoltativamente, puoi abilitare il pagamento del tuo sito per restituire l&#39;indirizzo di fatturazione completo contattando PayPal e completando un processo di verifica.

PayPal ha anche una protezione integrata contro le frodi che utilizza l&#39;apprendimento automatico per aiutarti a combattere le frodi. Vedi PayPal&#39;s [Documentazione sulla protezione del venditore](https://www.paypal.com/us/webapps/mpp/security/seller-protection) per ulteriori informazioni.
