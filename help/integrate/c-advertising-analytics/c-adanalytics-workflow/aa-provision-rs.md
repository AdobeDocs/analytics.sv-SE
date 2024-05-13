---
description: Konfigurera en rapportsvit som mappats till Experience Cloud för användning i Advertising Analytics.
title: Aktivera rapportsvit för Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Aktivera rapportsvit för Advertising Analytics

Om du vill se Advertising Analytics sökdata i Analytics måste du konfigurera varje rapportsvit som mappas med Experience Cloud för Advertising Analytics-rapportering.

1. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Välj den rapportsvit som är mappad till din Experience Cloud-organisation.
1. Klicka **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Rapportering](assets/aa-reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID refererar till den Adobe Advertising Cloud-variabel (även kallad Adobe Media Optimizer) i vilken sökdata ska infogas.

1. Välj **[!UICONTROL Unfamiliar with Advertising Analytics? Click here to learn more]** för mer information om Advertising Analytics.

1. Ange variabelallokering och förfallodatum som du vill att variabeln AMO ID ska använda. Med konverteringsvariabler (eVars) kan Adobe Analytics attribuera success-händelser till specifika variabelvärden. Ibland påträffar variabler mer än ett värde innan en success-händelse inträffar. I dessa fall avgör allokeringen vilket variabelvärde som får kredit för händelsen.

   | Inställning | Definition |
   |--- |--- |
   | **[!UICONTROL Allocation]** | Välj mellan:<br/> **[!UICONTROL Original Value (First)]**: Det första värdet som visas får fullständig allokeringskredit, oavsett vilka efterföljande värden som används för variabeln. <br/>**[!UICONTROL Most Recent (Last)]**: Det sista värdet som visas får fullständig allokeringskreditering för händelsen success, oavsett vilka variabler som sparades innan. |
   | **[!UICONTROL Expire After]** | Gör att du kan ange en tidsperiod eller händelse efter vilken eVarna förfaller (dvs. inte längre får kredit för lyckade händelser).  Om en lyckad händelse inträffar efter att eVarna har upphört att gälla, får värdet Ingen kredit för händelsen (ingen eVar var aktiv). |

1. Klicka **[!UICONTROL Enable Advertising Analytics Reporting]** (första gången), eller **[!UICONTROL Update Advertising Analytics Reporting]** (efterföljande gånger). Din rapportsvit är nu klar att ta emot data från Advertising Analytics Search. Du är nu redo att [skapa annonskonton](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
