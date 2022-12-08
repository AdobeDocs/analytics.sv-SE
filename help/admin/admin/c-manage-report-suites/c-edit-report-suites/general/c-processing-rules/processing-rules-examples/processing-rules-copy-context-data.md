---
description: Bearbetningsregler används för att flytta värden från Context Data-variabler till props och eVars.
subtopic: Processing rules
title: Kopiera en kontextdatavariabel till en eVar
feature: Admin Tools
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 7%

---

# Kopiera en kontextdatavariabel till en eVar

Bearbetningsregler används för att flytta värden från kontextdatavariabler till props och eVars. Utan bearbetningsregler är kontextdatavariabler meningslösa och fyller inte i några rapporter i Analytics.

The [!UICONTROL Context Variables] listan innehåller alla variabler som har skickats till rapportsviten under de senaste 30 dagarna. Om du känner till namnet på kontextdatavariabeln men inte har skickat den till den aktuella rapportsviten kan du lägga till ett värde genom att skriva variabelnamnet och klicka på **[!UICONTROL Add variable name context data]**:

![Lägg till](assets/add-context-variable.png)

I följande exempel används `search_term` kontextdatavariabel och placerar dess värde i `eVar3`:

![Ange](assets/set-context-data.png)

Exemplet ovan fungerar bra när det bara finns ett fåtal eVars att fylla i. Om din organisation har hundratals sammanhangsberoende datavariabler som alla behöver sina egna eVar, kan du använda villkorssatser. Dussintals villkorssatser får plats i en enda bearbetningsregel, vilket gör att organisationen kan fylla i alla eVars-variabler i en rapportserie utan att behöva köra upp till gränsen på 150 regler.

I följande exempel fylls `prop7` med kontextdatavariabeln `testhierarchy`, men bara om `testhierarchy` är inställt:

![Villkorlig](assets/add-conditional.png)

Mer information om hur du implementerar kontextdatavariabler finns i [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md) i Implementeringshandboken.
