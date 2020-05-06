---
title: Frågor och svar
description: Få svar på vanliga frågor när du går från en tredjepartsplattform till Adobe.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---


# Frågor och svar

**Hur migrerar jag mina historiska data från min tredjepartsplattform till Adobe Analytics?**

Alla Analytics-plattformar har olika sätt att samla in, hantera och lagra data. I stället för att migrera historiska data rekommenderar Adobe att du skapar ett tydligt brytdatum för att börja samla in och använda data i Adobe Analytics. Vanliga brytdatum är början av ett räkenskapsår, början av ett kalenderår eller början av en kalendermånad. Om användarna vill se historiska data kan de logga in på tredjepartsplattformen för att få fram specifika historiska rapporteringsbehov.

Om din organisation är mån om att få historisk information överförd till Adobe kontaktar du er organisations Account Manager. En implementeringskonsult kan samarbeta med organisationen för att översätta en Google Analytics-dataexport till en datakälla som kan importeras av Adobes datainsamlingsservrar.

Adobe rekommenderar inte att man porterar historiska data eftersom det är en komplex process som är kostnadsbesparande för er organisation. Det går inte heller att importera besökaridentifiering till Adobe eftersom besökarinformationen lagras i olika cookies och olika format på olika plattformar.

**Jag är van vid en segmenteringslistruta i många av mina rapporter. Hur kan jag återskapa det där i[!UICONTROL Analysis Workspace]?**

Listrutefilter är en flexibel och robust funktion i [!UICONTROL Analysis Workspace] som möjliggör en listruta för segmentering. I ett arbetsyteprojekt:

1. Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på de komponenter som du vill ta med i listrutan. Du är inte begränsad till bara segment; valfri komponent kan inkluderas i ett listrutefilter.
2. Dra gruppen med komponenter till arbetsytan med namnet &#39;Släpp ett segment här&#39;. Håll ned Skift innan du släpper.

Användare som använder det här [!UICONTROL Workspace] projektet kan nu använda den här listrutan för att tillämpa segment eller andra komponenter i projektet. Mer information finns i [Panelöversikt](/help/analyze/analysis-workspace/c-panels/panels.md) i Adobe Analytics-verktygshandboken.

**Jag är van vid att klicka på ett dimensionsvärde för att se en detaljnivå. Hur kan jag replikera det enkla arbetsflödet i Analysis Workspace?**

Dimensionsvärden i [!UICONTROL Analysis Workspace] har också ett enkelt uppdelningsarbetsflöde. Du öppnar den genom att högerklicka i stället för att vänsterklicka. Högerklicka på ett dimensionsvärde, klicka på **[!UICONTROL Breakdown]och välj sedan önskad komponent. Du kan tillämpa samma uppdelning på flera dimensionsvärden genom att Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på varje värde.
