---
description: Bearbetningsregler används för att flytta värden från Context Data-variabler till props och eVars.
subtopic: Processing rules
title: Kopiera en kontextdatavariabel till en eVar
feature: Admin Tools
role: Admin
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Kopiera en kontextdatavariabel till en eVar

Bearbetningsregler används för att flytta värden från kontextdatavariabler till props och eVars. Utan bearbetningsregler är kontextdatavariabler meningslösa och fyller inte i några rapporter i Analytics.

Listan [!UICONTROL Context Variables] innehåller alla variabler som har skickats till rapportsviten under de senaste 30 dagarna. Om du känner till namnet på kontextdatavariabeln men inte har skickat den till den aktuella rapportsviten kan du lägga till ett värde genom att skriva variabelnamnet och klicka på **[!UICONTROL Add variable name context data]**:

![Lägg till](assets/add-context-variable.png)

I följande exempel används datavariabeln `search_term` för kontext och dess värde placeras i `eVar3`:

![Uppsättning](assets/set-context-data.png)

Exemplet ovan fungerar bra när det bara finns ett fåtal eVars att fylla i. Om din organisation har hundratals sammanhangsberoende datavariabler som alla behöver sin egen eVar, kan du använda villkorssatser. Dussintals villkorssatser får plats i en enda bearbetningsregel, vilket gör att organisationen kan fylla i alla eVars-variabler i en rapportserie utan att behöva köra upp till gränsen på 150 regler.

I följande exempel fylls `prop7` med kontextdatavariabeln `testhierarchy`, men bara om `testhierarchy` är inställt:

![Villkorlig](assets/add-conditional.png)

Mer information om hur du implementerar kontextdatavariabler finns i [Kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) i användarhandboken för Implementera.
