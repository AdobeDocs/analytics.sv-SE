---
title: hövding
description: (Borttaget) Implementera hierarkivariabler i Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# hövding

>[!IMPORTANT]
>
>Den här variabeln har tagits bort och är inte en tillgänglig dimension i Analysis Workspace. Adobe rekommenderar att du använder [eVars](evar.md) och klassificeringar i stället.

Hierarkivariabler är anpassade variabler som du kan använda för att visa strukturen för en plats. Adobe stöder upp till 5 hierarkivariabler i implementeringen.

Den här variabeln är användbar för platser som har mer än tre nivåer i platsstrukturen. En mediewebbplats kan till exempel ha fyra nivåer för sportavsnittet: `Sports`, `Local Sports`, `Baseball` och `Team name`. Om någon besöker Baseball-sidan, Sport, Local Sports och Baseball återspeglar alla nivåer detta besök.

Innan du använder hierarkier i implementeringen måste du konfigurera varje hierarki i inställningarna för rapportsviten.

## Hierarkier med Web SDK

Hierarkier [mappas för Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) under XDM-fälten `xdm._experience.analytics.customDimensions.hierarchies.hier1` till `xdm._experience.analytics.customDimensions.hierarchies.hier5`.

## Hierarkier med Adobe Analytics-tillägget

Du kan ange hierarkier antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Hierarchy].

Du kan ställa in ett hierarkivärde på en statisk sträng eller referera till ett dataelement. Du kan också ange önskad avgränsare. Kontrollera att avgränsaren som du anger här matchar avgränsaren som anges i inställningarna för rapportsviten.

## s.hier1 - s.hier5 i AppMeasurementet och den anpassade kodredigeraren i Analytics-tillägget

Varje hierarki är en sträng som innehåller anpassade värden som är specifika för din organisation. Deras maxlängd är 255 byte. Värden som är längre än 255 byte trunkeras automatiskt när de skickas till Adobe.

Kontrollera att inga av avsnittsnamnen har avgränsaren. Om till exempel ett av avsnitten heter `Coach Griffin, Jim` väljer du en annan avgränsare än ett komma. Den totala variabelgränsen är 255 byte. Avgränsare kan bestå av flera tecken, t.ex. `||` eller `/|\`, som mindre sannolikt förekommer i variabelvärden.

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
