---
title: Skapa ett datalager
description: Lär dig vad ett datalager är i Analytics-implementeringen och hur det kan användas för att mappa variabler i Adobe Analytics.
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 2%

---

# Skapa ett datalager

Ett datalager är ett ramverk av JavaScript-objekt på platsen som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.

## Förutsättningar

[Skapa ett designdokument](solution-design.md)  för lösningar - Det är viktigt för er organisation att följa spårningskraven. Se till att du är förberedd på ett lösningsdesigndokument innan du kontaktar utvecklingsteamen i organisationen.

## Arbetsflöde

Implementering av Adobe Analytics med ett datalager följer vanligtvis dessa steg:

1. **Samarbeta med webbplatsens utvecklingsteam för att implementera ett datalager**: Webbplatsutvecklingsteamet ansvarar i första hand för att se till att datalagret fylls med korrekta värden. Granska den här sidan med ditt utvecklingsteam för att se till att förväntningarna är desamma i olika team.

   >[!NOTE]
   >
   >Följande Adobe rekommenderade datalagerspecifikationer är valfria. Om du redan har ett datalager, eller på annat sätt väljer att inte följa Adobe specifikationer, måste du se till att din organisation anpassar sig efter vilken specifikation som ska följas.
1. **Validera datalagret med en webbläsarkonsol**: När ett datalager har skapats kan du validera att det fungerar med hjälp av en webbläsares utvecklarkonsol. Du kan öppna utvecklarkonsolen i de flesta webbläsare med `F12`-tangenten. Ett exempelvariabelvärde skulle vara `digitalData.page.pageInfo.pageID`.
1. **Använd Adobe Experience Platform-taggar för att mappa datalager-objekt till dataelement**: Skapa dataelement i användargränssnittet för datainsamling i Adobe Experience Platform och mappa dem till de JavaScript-attribut som beskrivs i datalagret.
1. **Använd taggtillägget Adobe Analytics för att mappa dataelement till analysvariabler**: Tilldela varje dataelement till rätt Analytics-variabel efter lösningsdesigndokumentet.

## Specifikationer

Adobe rekommenderar att du följer [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) som beskrivs i [Customer Experience Digital Data Community Group](https://www.w3.org/community/custexpdata/). Använd följande avsnitt för att förstå hur datalagerelement samverkar med Adobe Analytics.

Det rekommenderade överliggande datalagret som ska användas är `digitalData`. I följande exempel visas ett något omfattande JSON-datalager med exempelvärden:

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

Använd rapporten [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) för information om varje objekt och underobjekt. Alla platser använder inte alla objekt. Om du till exempel är värd för en nyhetswebbplats är det osannolikt att du har använt för objektarrayen `digitalData.product`.

Datalager är utökningsbara. om du har särskilda krav för organisationen, kan du inkludera objekt i datalagret för att tillgodose dessa behov.

## Ange datalagervärden

Datalager genererar vanligtvis serversidan och refererar till samma objekt som används för att skapa webbplatsinnehållet. Upprätta webbplatsens datalager baserat på spårningskrav som anges i organisationens [lösningsdesigndokument](solution-design.md).

## Nästa steg

[Mappa datalagerobjekt till dataelement](../launch/layer-to-elements.md): Använd webbplatsens datalager i Adobe Experience Platform.
