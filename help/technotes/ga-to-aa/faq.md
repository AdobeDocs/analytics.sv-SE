---
title: Frågor och svar om migrering till Adobe Analytics
description: Få svar på vanliga frågor när du går från en tredjepartsplattform till Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 58d53d6013abcd7d99f2c3cb640d6a648a4ef360
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 35%

---

# Frågor och svar om migrering till Adobe Analytics

**Hur migrerar jag mina historiska data från min tredjepartsplattform till Adobe Analytics?**

Alla Analytics-plattformar har olika sätt att samla in, hantera och lagra data. I stället för att migrera historiska data rekommenderar Adobe att du skapar ett tydligt brytdatum för att börja samla in och använda data i Adobe Analytics. Vanliga brytdatum är början av ett räkenskapsår, början av ett kalenderår eller början av en kalendermånad. Om användarna vill se historiska data kan de logga in på tredjepartsplattformen för att få fram specifika historiska rapporteringsbehov.

Om din organisation är mån om att få historisk information överförd till Adobe kontaktar du ditt kontoteam för Adobe. En implementeringskonsult kan samarbeta med organisationen för att översätta en Google Analytics-dataexport till en datakälla som kan importeras av Adobes datainsamlingsservrar.

För att kunna flytta över historiska data rekommenderar vi att du använder [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview) som kan ta in valfri datakälla i flera kanaler.

**Jag är van vid en listruta för segmentering i många av mina rapporter. Hur återskapar jag det i [!UICONTROL Analysis Workspace]?**

Nedrullningsbara filter är en flexibel och robust funktion i [!UICONTROL Analysis Workspace] som tillåter en listruta för segmentering. I ett arbetsyteprojekt:

1. Använd ***Ctrl***+***klicka*** (Windows) eller ***cmd***+***klicka*** (Mac) på de komponenter som du vill ta med i listrutan. Du är inte begränsad till bara segment. Alla komponenter kan inkluderas i ett nedrullningsbart filter.
2. Dra gruppen med komponenter till arbetsytan med etiketten *Släpp ett segment här*. Håll **[!UICONTROL shift]** innan du släpper.

Användare som använder det här [!UICONTROL Workspace]-projektet kan nu använda det här nedrullningsbara filtret för att tillämpa segment eller andra komponenter i projektet. Mer information finns i [Panelöversikt](/help/analyze/analysis-workspace/c-panels/panels.md) i Adobe Analytics-handboken.

**Jag är van vid att klicka på ett dimensionsobjekt för att visa en detaljnivå. Hur kan jag replikera det enkla arbetsflödet i Analysis Workspace?**

Dimension-objekt i [!UICONTROL Analysis Workspace] har också ett enkelt arbetsflöde för att dela upp dem. Få åtkomst till detaljerna via snabbmenyn för ett dimensionsobjekt. Välj sedan **[!UICONTROL Breakdown]** och den önskade komponenten. Du kan tillämpa samma uppdelning på flera dimensionsobjekt genom att använda ***ctrl***+***select*** (Windows) eller ***cmd***+***select*** (Mac) för varje värde.
