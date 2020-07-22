---
title: Frågor och svar
description: Få svar på vanliga frågor när du går från en tredjepartsplattform till Adobe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 68%

---


# Frågor och svar

**Hur migrerar jag mina historiska data från min tredjepartsplattform till Adobe Analytics?**

Alla Analytics-plattformar har olika sätt att samla in, hantera och lagra data. I stället för att migrera historiska data rekommenderar Adobe att du skapar ett tydligt brytdatum för att börja samla in och använda data i Adobe Analytics. Vanliga brytdatum är början av ett räkenskapsår, början av ett kalenderår eller början av en kalendermånad. Om användarna vill se historiska data kan de logga in på tredjepartsplattformen för att få fram specifika historiska rapporteringsbehov.

Om din organisation är mån om att få historisk information överförd till Adobe kontaktar du er organisations Account Manager. En implementeringskonsult kan samarbeta med organisationen för att översätta en Google Analytics-dataexport till en datakälla som kan importeras av Adobes datainsamlingsservrar.

Adobe rekommenderar inte att man porterar historiska data eftersom det är en komplex process som är kostnadsbesparande för er organisation. Det går inte heller att importera besökaridentifiering till Adobe eftersom besökarinformationen lagras i olika cookies och i olika format på olika plattformar.

**Jag är van vid en segmenteringslistruta i många av mina rapporter. How can I recreate that in[!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. I ett arbetsyteprojekt:

1. Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på de komponenter som du vill ta med i listrutan. Du är inte begränsad till bara segment; valfri komponent kan inkluderas i ett listrutefilter.
2. Dra gruppen med komponenter till arbetsytan med namnet &#39;Släpp ett segment här&#39;. Håll ned Skift innan du släpper.

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**Jag är van vid att klicka på ett dimensionsobjekt för att se en detaljnivå. Hur kan jag replikera det enkla arbetsflödet i Analysis Workspace?**

Dimensionsobjekt i har [!UICONTROL Analysis Workspace] också ett enkelt arbetsflöde. Du öppnar den genom att högerklicka i stället för att vänsterklicka. Right-click on a dimension item, click **[!UICONTROL Breakdown], then select the desired component. Du kan tillämpa samma uppdelning på flera dimensionsobjekt genom att Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på varje värde.
