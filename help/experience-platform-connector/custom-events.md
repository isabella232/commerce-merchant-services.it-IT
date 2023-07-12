---
title: Creare eventi personalizzati
description: Scopri come creare eventi personalizzati per collegare i dati di Adobe Commerce ad altri prodotti Adobe DX.
exl-id: 5a754106-c66a-4280-9896-6d065df8a841
source-git-commit: 2e1a0b2a79449562a2716929084f12eeee55a159
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Creare eventi personalizzati

È possibile estendere [piattaforma di gestione eventi](events.md) creando eventi storefront personalizzati per raccogliere dati specifici per il tuo settore. Quando crei e configuri un evento personalizzato, questo viene inviato al [Raccolta eventi di Adobe Commerce](https://github.com/adobe/commerce-events/tree/main/packages/commerce-events-collectors).

## Gestire eventi personalizzati

Gli eventi personalizzati sono supportati solo per Adobe Experience Platform. I dati personalizzati non vengono inoltrati alle dashboard di Adobe Commerce e ai tracker di metriche.

Per qualsiasi `custom` , il raccoglitore aggiunge un `personId` (`ecid`) a `customContext` e racchiude un `xdm` intorno a esso prima dell&#39;inoltro al bordo.

Esempio:

Evento personalizzato pubblicato tramite SDK eventi di Adobe Commerce:

```javascript
mse.publish.custom({
    customContext: { customStrAttr: "cheetah", customNumAttr: 128 },
});
```

In Experience Platform Edge:

```javascript
{
    xdm: {
        personId: 'ecid1234',
        customStrAttr: 'cheetah',
        customNumAttr: 128
    }
}
```

>[!NOTE]
>
> L’utilizzo di eventi personalizzati può influire sui rapporti predefiniti di Adobe Analytics.

## Gestire le sostituzioni di eventi (attributi personalizzati)

Le sostituzioni di attributo per gli eventi standard sono supportate solo per l’Experience Platform. I dati personalizzati non vengono inoltrati alle dashboard di Commerce e ai tracker di metriche.

Per qualsiasi evento con un set `customContext`, il raccoglitore sostituisce `personId` e Adobe Analytics e inoltra tutti gli altri attributi impostati in `customContext`.

Esempi:

Visualizzazione prodotto con sostituzioni pubblicate tramite SDK per eventi di Adobe Commerce:

```javascript
mse.publish.productPageView({
    customContext: { customCode: "okapi" },
});
```

In Experience Platform Edge:

```javascript
{
    xdm: {
        eventType: 'commerce.productViews',
        personId: 'ecid1234',
        customCode: 'okapi',
        commerce: {
            productViews: {
                value : 1
            }
        }
    }
}
```

La visualizzazione del prodotto con le sostituzioni di Adobe Commerce pubblicata tramite l’SDK degli eventi di Adobe Commerce:

```javascript
mse.publish.productPageView({
    customContext: { commerce: { customCode: "mongoose" } },
});
```

In Experience Platform Edge:

```javascript
{
    xdm: {
        eventType: 'commerce.productViews',
        personId: 'ecid1234',
        commerce: {
            customCode: 'mongoose',
            productViews: {
                value : 1
            }
        }
    }
}
```

>[!NOTE]
>
> La sostituzione di eventi con attributi personalizzati può influire sui rapporti predefiniti di Adobe Analytics.
