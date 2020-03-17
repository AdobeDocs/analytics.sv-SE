---
description: För att inte bli fel med Enkelsidiga besök i ad hoc-analys visar rapporten Single Page Visits vilka sidor besökarna på webbplatsen skriver in och avslutar, utan att vidta några åtgärder för att visa några andra sidor.
title: Single Page Visit
topic: Reports
uuid: 5ca52be8-c7f5-464a-8a06-55e8271760b4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Single Page Visit

För att inte bli fel med Enkelsidiga besök i ad hoc-analys visar rapporten Single Page Visits vilka sidor besökarna på webbplatsen skriver in och avslutar, utan att vidta några åtgärder för att visa några andra sidor.

Den här rapporten används oftast i samband med [!UICONTROL Pages] rapporten, men den kan också visas i alla trafikvariabler med [!UICONTROL pathing] aktiverad. Du kan använda den här rapporten för att identifiera anmälningssidor som sannolikt kommer att tvinga en besökare att utforska din webbplats ytterligare, eller för att fastställa hur många besök som består av en enda sida. Med den här informationen kan du optimera innehåll för att minska antalet utgångar på dessa sidor.

## Egenskaper för rapporten {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* Du kan hämta en identisk rapport genom att dra en [!UICONTROL Pages] rapport [!UICONTROL Single Access] som ett mått.

* Ett enda sidbesök anses vara ett besök som innehåller ett unikt värde, inte en enda bildförfrågan.

   * När det gäller en [sidrapport](/help/components/c-variables/dimensionslist/reports-pages.md)kan bara en unik sida utlösas vid besöket.
   * I samband med en rapport [om](/help/components/c-variables/dimensionslist/reports-site-sections.md)webbplatsavsnitt utlöses en unik webbplatssektion inom besöket.
   * När det gäller en [trafikvariabel](/help/admin/admin/c-traffic-variables/traffic-var.md)fyller ett besök i den här rapporten om ett unikt värde utlöses.

* Besök på en sida kan bestå av många bildbegäranden, förutsatt att variabeln i rapportens sammanhang innehåller ett enda unikt värde. Så snart ett andra unikt värde har fyllts i räknas besöket inte längre som ett enda sidbesök.
* Detta betraktas som en typ av målningsrapport. Som standard har variabeln [!UICONTROL Pages] Pathing enabled. Alla trafikvariabler har dock även denna kapacitet. Om du vill aktivera delning på ytterligare trafikvariabler beror på ditt kontrakt. Kontakta din organisations kontoansvarige om du vill ha mer information.
* Den här rapporten kan använda ett sökfilter för att hitta specifika radobjekt.
* Den här rapporten kan visas i både [trendformat](/help/components/c-variables/dimensionslist/reports-types.md) och [rankat](/help/components/c-variables/dimensionslist/reports-types.md) format.

* Det finns inga tillgängliga uppdelningar i den här rapporten.
* Det enda tillgängliga mätvärdet i den här rapporten är [!UICONTROL Visits].

