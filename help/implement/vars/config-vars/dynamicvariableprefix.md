---
title: dynamicVariablePrefix
description: Gör att du kan anpassa strängen som identifierar dynamiska variabler.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# dynamicVariablePrefix

Dynamiska variabler är ett koncept som du kan använda för att kopiera värden från en variabel till en annan. De är användbara för långa variabelvärden eftersom de hjälper till att korta URL-längden för en bildförfrågan. Mer information om det här konceptet finns i [Dynamiska variabler](../page-vars/dynamic-variables.md).

Som standard använder dynamiska variabler prefixet `D=`. Med variabeln `dynamicVariablePrefix` kan du anpassa strängen som identifierar dynamiska variabler. Den är skiftlägeskänslig.

## Dynamiskt variabelprefix med Web SDK

I Web SDK används inte dynamisk variabelformatering. I stället kan du använda Datastream-mappning för att fylla i flera målfält med ett enda Source-fält. Mer information finns i [Dynamiska variabler med Web SDK](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk).

Om du skickar data direkt till Adobe Analytics utan att följa ett schema, används följande variabel:

* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.dynamicVariablePrefix`

## Dynamiskt variabelprefix med Adobe Analytics-tillägget

Dynamiskt variabelprefix är ett fält under dragspelet [!UICONTROL Global Variables] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL Global Variables] som visar fältet [!UICONTROL Dynamic Variable Prefix].

Det här fältet innehåller `D=` som standard. Du kan ändra värdet om du vill använda ett annat dynamiskt variabelprefix. Du kan använda vilket värde du vill, förutsatt att det matchar teckenkodningen på webbplatsen.

## s.dynamicVariablePrefix i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.dynamicVariablePrefix` är en sträng som kan innehålla alla teckensekvenser. Om variabeln inte definieras används strängen `D=` som standard i AppMeasurementet.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
