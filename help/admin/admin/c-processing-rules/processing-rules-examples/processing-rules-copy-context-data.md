---
description: Bearbetningsregler används för att flytta värden från Context Data-variabler till props och eVars.
subtopic: Processing rules
title: Kopiera en kontextdatavariabel till en eVar
topic: Admin tools
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Kopiera en kontextdatavariabel till en eVar

Bearbetningsregler används för att flytta värden från kontextdatavariabler till props och eVars. Utan bearbetningsregler är kontextdatavariabler meningslösa och fyller inte i några rapporter i Analytics.

Listan innehåller alla variabler som har skickats till rapportsviten under de senaste 30 dagarna. [!UICONTROL Context Variables] Om du känner till namnet på kontextdatavariabeln men inte har skickat den till den aktuella rapportsviten kan du lägga till ett värde genom att skriva variabelnamnet och klicka på **[!UICONTROL Add variable name context data]**:

![Lägg till](assets/add-context-variable.png)

I följande exempel används variabeln `search_term` context data och dess värde placeras i `eVar3`:

![Ange](assets/set-context-data.png)

Exemplet ovan fungerar bra när det bara finns ett fåtal eVars att fylla i. Om din organisation har hundratals kontextdatavariabler som alla behöver sina egna eVar-variabler kan du använda villkorssatser. Dussintals villkorssatser får plats i en enda bearbetningsregel, vilket gör att organisationen kan fylla i alla eVars-variabler i en rapportserie utan att behöva köra upp till gränsen på 150 regler.

I följande exempel fylls `prop7` kontextdatavariabeln i, `testhierarchy`men bara om `testhierarchy` är inställd:

![Villkorlig](assets/add-conditional.png)

Mer information om hur du implementerar kontextdatavariabler finns i [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md) i användarhandboken för Implementera.
