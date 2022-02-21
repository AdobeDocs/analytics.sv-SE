---
description: Konfigurera en rapportsvit som mappats till Experience Cloud för användning i Advertising Analytics.
title: Aktivera rapportsvit för Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 7%

---

# Aktivera rapportsvit för Advertising Analytics

Om du vill kunna se Advertising Analytics sökdata i Analytics måste du konfigurera varje rapportsvit som mappas av Experience Cloud för Advertising Analytics-rapportering.

1. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Välj den rapportsvit som är mappad till din Experience Cloud-organisation.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Rapportering](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID refererar till den Adobe Advertising Cloud-variabel i vilken sökdata ska infogas.

1. Ange variabelallokering och förfallodatum som du vill att variabeln AMO ID ska använda. Med konverteringsvariabler (eVars) kan Adobe Analytics attribuera success-händelser till specifika variabelvärden. Ibland påträffar variabler mer än ett värde innan en success-händelse inträffar. I dessa fall avgör allokeringen vilket variabelvärde som får kredit för händelsen.

   | Inställning | Definition |
   |--- |--- |
   | Ursprungligt värde (första) | Det första värdet som visas får fullständig allokeringskredit, oavsett vilka efterföljande värden som används för variabeln. |
   | Senaste (senaste) | Det senaste värdet som har identifierats får fullständig allokeringskreditering för händelsen success, oavsett vilka variabler som sparades innan. |
   | Förfaller efter | Gör att du kan ange en tidsperiod eller händelse efter vilken eVar förfaller (dvs. inte längre får kredit för lyckade händelser).  Om en lyckad händelse inträffar efter att eVar har upphört att gälla, får värdet Ingen kredit för händelsen (ingen eVar var aktiv). |

1. Klicka **[!UICONTROL Enable Advertising Analytics Reporting]** (första gången), eller **[!UICONTROL Update Advertising Analytics Reporting]** (efterföljande gånger). Din rapportsvit är nu klar att ta emot data från Advertising Analytics Search. Du är inte redo att [skapa annonskonton](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
