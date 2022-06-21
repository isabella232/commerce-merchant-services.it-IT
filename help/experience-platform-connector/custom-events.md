---
title: Creare eventi personalizzati
description: Scopri come creare eventi personalizzati per collegare i dati di Adobe Commerce ad altri prodotti DX di Adobe.
source-git-commit: 1dd8f94e632bb98666ad252badf8420a014260fb
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# Creare eventi personalizzati

È possibile estendere [piattaforma di eventi](events.md) creando eventi di vetrina personalizzati per raccogliere dati unici per il tuo settore. Quando crei e configuri un evento personalizzato, questo viene inviato al [Raccoglitore eventi Magento Storefront](https://www.npmjs.com/package/@adobe/magento-storefront-event-collector).

## Gestire eventi personalizzati

Gli eventi personalizzati sono supportati solo per Adobe Experience Platform. I dati personalizzati non vengono inoltrati alle dashboard e ai tracciatori delle metriche di Adobe Commerce.

Per qualsiasi `custom` , il raccoglitore aggiunge un `personId` (`ecid`) a `customContext` e avvolge un `xdm` prima di inoltrare al server Edge.

Esempio:

Evento personalizzato pubblicato tramite MSE SDK:

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

## Gestire le sostituzioni degli eventi (attributi personalizzati)

Le sostituzioni degli attributi per gli eventi standard sono supportate solo ad Experience Platform. I dati personalizzati non vengono inoltrati ai dashboard e ai tracciatori delle metriche Commerce.

Per qualsiasi evento con un set `customContext`, sostituisce il raccoglitore `personId` e i contatori Adobe Analytics e inoltra tutti gli altri attributi impostati in `customContext`.

Esempi:

Visualizzazione del prodotto con sostituzioni pubblicate tramite MSE SDK:

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

La visualizzazione del prodotto con le sostituzioni di Adobe Commerce viene pubblicata tramite l’SDK MSE:

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
