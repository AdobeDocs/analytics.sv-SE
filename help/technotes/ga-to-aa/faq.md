---
title: Frågor och svar om migrering till Adobe Analytics
description: Få svar på vanliga frågor när du går från en tredjepartsplattform till Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 52%

---

# Frågor och svar om migrering till Adobe Analytics

**Hur migrerar jag mina historiska data från min tredjepartsplattform till Adobe Analytics?**

Alla Analytics-plattformar har olika sätt att samla in, hantera och lagra data. I stället för att migrera historiska data rekommenderar Adobe att du skapar ett tydligt brytdatum för att börja samla in och använda data i Adobe Analytics. Vanliga brytdatum är början av ett räkenskapsår, början av ett kalenderår eller början av en kalendermånad. Om användarna vill se historiska data kan de logga in på tredjepartsplattformen för att få fram specifika historiska rapporteringsbehov.

Om din organisation är van vid att få historisk information porterad till Adobe ska du kontakta ditt kontoteam på Adobe. En implementeringskonsult kan samarbeta med organisationen för att översätta en Google Analytics-dataexport till en datakälla som kan importeras av Adobes datainsamlingsservrar.

Vi rekommenderar att du använder [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) som kan ta med sig alla datakällor i flera kanaler.

**Jag är van vid en segmenteringslistruta i många av mina rapporter. Hur återskapar jag det i [!UICONTROL Analysis Workspace]?**

Listrutefilter är en flexibel och robust funktion i [!UICONTROL Analysis Workspace] som tillåter en listruta för segmentering. I ett arbetsyteprojekt:

1. Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på de komponenter som du vill ta med i listrutan. Du är inte begränsad till bara segment; valfri komponent kan inkluderas i ett listrutefilter.
2. Dra gruppen med komponenter till arbetsytan med namnet &#39;Släpp ett segment här&#39;. Håll ned Skift innan du släpper.

Användare som har åtkomst till detta [!UICONTROL Workspace] kan nu använda den här listrutan för att tillämpa segment eller andra komponenter i projektet. Se [Paneler - översikt](/help/analyze/analysis-workspace/c-panels/panels.md) i Adobe Analytics Tools Guide för mer information.

**Jag är van vid att klicka på ett dimensionsobjekt för att se en detaljnivå. Hur kan jag replikera det enkla arbetsflödet i Analysis Workspace?**

Dimensioner i [!UICONTROL Analysis Workspace] har också ett enkelt arbetsflöde. Du öppnar den genom att högerklicka i stället för att vänsterklicka. Högerklicka på en dimensionspost, klicka **[!UICONTROL Breakdown]markerar du sedan önskad komponent. Du kan tillämpa samma uppdelning på flera dimensionsobjekt genom att Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på varje värde.
