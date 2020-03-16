---
title: Skapa ett datalager
description: Lär dig vad ett datalager är i er Analytics-implementering och hur det kan användas för att mappa variabler i Adobe Analytics.
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Skapa ett datalager

Ett datalager är ett ramverk av JavaScript-objekt på platsen som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.

## Förutsättningar

[Skapa ett designdokument](solution-design.md) för lösningar - Det är viktigt för er organisation att följa spårningskraven. Se till att du är förberedd på ett dokument för lösningsdesign innan du kontaktar utvecklingsteamen i organisationen.

## Arbetsflöde

Att implementera Adobe Analytics med ett datalager följer vanligtvis dessa steg:

1. **Samarbeta med webbplatsens utvecklingsteam för att implementera ett datalager**: Webbplatsutvecklingsteamet ansvarar i första hand för att se till att datalagret fylls med korrekta värden. Granska den här sidan med ditt utvecklingsteam för att se till att förväntningarna är desamma i olika team.
   > [!NOTE] Det är valfritt att följa Adobes rekommenderade datalagerspecifikationer. Om du redan har ett datalager, eller på annat sätt väljer att inte följa Adobes specifikationer, måste du se till att din organisation anpassar sig efter vilken specifikation som ska följas.
2. **Validera datalagret med en webbläsarkonsol**: När ett datalager har skapats kan du validera att det fungerar med hjälp av en webbläsares utvecklarkonsol. Du kan öppna utvecklarkonsolen i de flesta webbläsare med hjälp av `F12` . Ett exempelvariabelvärde skulle vara `digitalData.page.pageInfo.pageID`.
3. **Använd Adobe Experience Platform Launch för att mappa datalager-objekt till Launch-dataelement**: Skapa dataelement i Launch och mappa dem till de JavaScript-attribut som beskrivs i datalagret.
4. **Använd Adobe Analytics-tillägget i Launch för att mappa dataelement till Analytics-variabler**: Tilldela varje dataelement till rätt Analytics-variabel efter lösningsdesigndokumentet.

## Specifikationer

Adobe rekommenderar att du följer [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) som beskrivs av [Customer Experience Digital Data Community Group](https://www.w3.org/community/custexpdata/). Använd följande avsnitt för att förstå hur datalagerelement interagerar med Adobe Analytics.

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
            subCategory1: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product1: {
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    },
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
    event1: {
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    component1: {
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    user1: {
        segment: "Premium membership",
        profile1: {
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
        }
    },
    privacy: {
        accessCategories1: {
            categoryName: "Default",
            domains: "adobedtm.com"
        }
    },
    version: "1.0"
}
```

Använd rapporten [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) för mer information om varje objekt och underobjekt. Alla platser använder inte alla objekt. Om du till exempel har en nyhetswebbplats som värd är det osannolikt att du har använt för `digitalData.product` objektet.

Datalager är utökningsbara. om du har särskilda krav för organisationen, kan du inkludera objekt i datalagret för att tillgodose dessa behov.

## Ange datalagervärden

Datalager genererar vanligtvis serversidan och refererar till samma objekt som används för att skapa webbplatsinnehållet. Upprätta webbplatsens datalager baserat på spårningskrav som anges i organisationens [lösningsdesigndokument](solution-design.md).

## Nästa steg

[Mappa datalagerobjekt till dataelement](../launch/layer-to-elements.md): Använd webbplatsens datalager i Adobe Experience Platform Launch.
