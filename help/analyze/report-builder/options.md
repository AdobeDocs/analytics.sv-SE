---
description: På panelen Alternativ kan du ange datuminställningar, fördröjningsinställningar (Aktuella data), logginformation och konfigurera uppdateringar.
title: Alternativ för Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 2%

---

# Alternativ för Report Builder

På panelen Alternativ kan du ange datuminställningar, fördröjningsinställningar (Aktuella data), logginformation och konfigurera uppdateringar.

1. Klicka på **[!UICONTROL Options]** ![](assets/options_icon.png) i verktygsfältet Tillägg:

| Element | Beskrivning |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Ange till aktuellt datum | Gör att du kan ange eller återställa [!UICONTROL As Of Date] så att rapportverktyget använder det aktuella datumet eller frågar vilket datum som ska användas vid uppdateringen. |
| Be mig ställa in vid uppdatering | Gör att du kan ange [!UICONTROL As Of Date] när du uppdaterar en begäran. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Gör att du kan visa datalatens (kallas även [!UICONTROL Data Recency]) ända ned till den minut som rapporteras, ibland även innan dessa data har bearbetats av Adobe Analytics.<br>Om du inte använder det här alternativet används det slutliga läget (bearbetat), som vanligtvis är mer  [latent](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html).<br>Den här inställningen gäller för alla begäranden i arbetsboken som är kompatibla med aktuella data. Om begäran inte är kompatibel används det slutliga läget.<br>Observera följande situationer när du använder  [!UICONTROL Include Current Data] läget:<br>**Formatalternativ**: Du kan ange om den här informationen ska visas ([!UICONTROL Data Recency]) vid  [formatering av visningsrubriker](/help/analyze/report-builder/layout/t-format-display-headers.md).<br>**Uppdelningar**: Stöds inte. Om läget [!UICONTROL Data Recency] är inställt på Aktuella data och en av förfrågningarna innehåller ett element för radbrytning, återgår den här begäran till ett dataläge som inte är aktuellt. Andra förfrågningar fortsätter dock att använda läget Aktuella data.<br>**Begäranhanteraren**: Du kan visa kolumnen Aktuella data i Begäranhanteraren, så att du kan se om inställningen har tillämpats på en schemalagd begäran.<br>**Schemalagda arbetsböcker**: Det här läget lagras under schemaläggningsprocessen på arbetsboksnivå. Om du öppnar en schemalagd arbetsbok som använder slutförda data och använder [!UICONTROL Include Current Data], används det aktuella läget därefter.<br>**Behörigheter**: För användare som inte har tillgång till aktuella data är det här alternativet dolt.  När du aktiverar det här alternativet skickas en varning om en eller flera begäranden inte kan tillämpas. |
| Inaktivera varningar för inkompatibla data-begäranden | Visar varningar om [!UICONTROL Include Current Data]-läget är valt men dataläget inte kan användas på den redigerade begäran.  Om du till exempel anger [!UICONTROL Include Current Data] och sedan redigerar en begäran som har ett segment markerat, visas en varning. |
| Logga Report builder-begäranden till lokal fil (för felsökning) | Gör att du kan logga begäranden till en lokal fil. Använd den här loggfilen för felsökning. |
| Tolka typvärde.. | Tolkar ett angivet värde i en filterkontroll som en cellplats innan det betraktas som ett filteruttryck.<br>Om du t.ex. skapar en Top 10 Page-begäran med en filterskor, visar begäran en cell som innehåller något som liknar: Filter: Den översta 1-10 sidan, sidan innehåller bilder |
| Uppdatera när en ny version är tillgänglig | Meddelar systemet att meddela dig om det finns en ny version att installera. |
