---
description: Läs mer om alternativen för Report Builder.
title: Om Report Builder-alternativ
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---

# Alternativ för Report Builder

På panelen Alternativ kan du ange datuminställningar, fördröjningsinställningar (Aktuella data), logginformation och konfigurera uppdateringar.

1. Klicka på **[!UICONTROL Options]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) i verktygsfältet Tillägg:

| Element | Beskrivning |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Ange till aktuellt datum | Gör att du kan ange eller återställa [!UICONTROL As Of Date] så att Report Builder använder det aktuella datumet eller frågar vilket datum som ska användas vid uppdateringen. |
| Be mig ställa in vid uppdatering | Gör att du kan ange [!UICONTROL As Of Date] när du uppdaterar en begäran. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Gör att du kan visa datatlatens (kallas även [!UICONTROL Data Recency]) ända ned till den minut som rapporteras, ibland även innan dessa data har bearbetats av Adobe Analytics.<br>Om du inte använder det här alternativet används det slutliga läget (bearbetat), som vanligtvis är mer [latent](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html).<br>Den här inställningen gäller för alla begäranden i arbetsboken som är kompatibla med aktuella data. Om begäran inte är kompatibel används det slutliga läget.<br>Observera följande situationer när [!UICONTROL Include Current Data]-läget används:<br>**Formatalternativ**: Du kan ange om den här informationen ska visas ([!UICONTROL Data Recency]) när [visningsrubriker formateras](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md).<br>**Uppdelningar**: Stöds inte. Om [!UICONTROL Data Recency]-läget är inställt på Aktuella data och en av förfrågningarna innehåller ett element för radbrytning, återgår den här begäran till ett dataläge som inte är aktuellt. Andra förfrågningar fortsätter dock att använda läget Aktuella data.<br>**Begäranhanteraren**: Du kan visa kolumnen Aktuella data i Begäranhanteraren, så att du kan se om inställningen har tillämpats på en schemalagd begäran.<br>**Schemalagda arbetsböcker**: Det här läget lagras under schemaläggningsprocessen på arbetsboksnivå. Om du öppnar en schemalagd arbetsbok som använder slutförda data och använder [!UICONTROL Include Current Data] används det aktuella läget därefter.<br>**Behörigheter**: För användare som inte har tillgång till aktuella data är det här alternativet dolt.  När du aktiverar det här alternativet skickas en varning om en eller flera begäranden inte kan tillämpas. |
| Inaktivera varningar för inkompatibla data-begäranden | Visar varningar om läget [!UICONTROL Include Current Data] har valts men dataläget inte kan tillämpas på den redigerade begäran.  Om du till exempel anger [!UICONTROL Include Current Data] och sedan redigerar en begäran som har ett segment markerat, visas en varning. |
| Logga Report Builder-begäranden till lokala filer (för felsökning) | Gör att du kan logga begäranden till en lokal fil. Använd den här loggfilen för felsökning. |
| Tolka typvärde.. | Tolkar ett angivet värde i en filterkontroll som en cellplats innan det betraktas som ett filteruttryck.<br>Om du till exempel skapar en Top 10 Page-begäran med filterskor, visar begäran en cell som innehåller något liknande:   Filter: Övre 1-10 sida, sidan innehåller bilder |
| Uppdatera när en ny version är tillgänglig | Meddelar systemet att meddela dig om det finns en ny version att installera. |
