---
title: Globala rapportsviter i Adobe Analytics
description: Förstå fördelarna och kraven med att använda ett globalt rapporteringsprogram.
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 0%

---

# Överväganden för globala rapportsviter

En global rapportserie är en rapportserie som samlar in data från alla domäner och appar som organisationen äger. Denna datainsamlingsteknik kräver förberedelse och kan kräva samordning mellan team inom organisationen.

## Fördelar

Adobe rekommenderar att man i de flesta fall genomför en global rapportserie.

* **Aggregerade data:** Med globala rapportsviter kan du visa KPI:er och lyckade händelser för dina egna webbplatser. Segmentering och virtuella rapportsviter kan användas för att visa platsspecifika data.
* **Stöd för enhetsövergripande analys:** CDA kräver en rapportsvit som samlar in data från flera platser, till exempel din webbplats och mobilapp. Separata enheter kan sammanfoga data om de implementeras på rätt sätt. Mer information finns i [Enhetsövergripande analys](../../components/cda/overview.md) i användarhandboken för komponenter.
* **Inget behov av mer än en rapportsserie:** Alla data kan samlas in i en enda rapportsvit, så det är mindre troligt att en utvecklare av misstag skickar data till fel rapportsserie.
* **Inget behov av sammanslagningar:** Samlingar är en funktion som är ganska daterad och som samlar data för enskilda rapportsviter dagligen. Upplysta listor tar inte bort besöks- eller besöksdata, vilket kan leda till ett högt antal. Mer information finns i [Samlingar](../../admin/admin/c-manage-report-suites/rollup-report-suite.md) i användarhandboken för Admin.
* **Spara tid:** Workspace-projekt, klassificeringar, segment och beräknade värden är knutna till samma globala rapportserie. Administratörer lägger mindre tid på att hantera dessa komponenter och datastyrning.
* **Exaktare varumärkesattribuering:** Om ett besök börjar på en webbplats och sedan klickar på en annan av dina egna webbplatser innan en lyckad händelse utlöses, samlas attribueringen in korrekt. En besökare klickar till exempel på en betald söklänk och hamnar på plats A. De klickar sedan på en länk till webbplats B och gör sedan ett köp. En global rapportsvit har korrekta attribut som återgår till betalsökningar.
* **Förenklad implementering:** Eftersom alla varumärken/webbplatser skickar data till samma rapportsvit justeras implementeringarna för varje webbplats. Denna tvingande styrning säkerställer att en viss dimension eller mätvärden sparas i samma eVar eller händelse. Administratörer, testare, tagghanteringsägare och analytiker drar nytta av denna förenkling.

>[!NOTE]
>
>Att samordna en global rapportsvitsimplementering är ett stort projekt. Adobe rekommenderar att ni samarbetar med en konsult för att minska antalet komplikationer och problem som kan uppstå.

## Starta en ny implementering med en global rapportserie

Använd följande allmänna riktlinjer för att förstå hur man implementerar en global rapportserie.

1. Skapa den globala rapportsviten i Adobe Analytics. Mer information finns i [Skapa en rapportsserie](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) i användarhandboken för Admin.
1. Arbeta med team i organisationen som ansvarar för varje domän. Många team har rapporteringskrav som är specifika för deras verksamhetsområde.
1. Registrera och samla alla dessa krav i ett [lösningsdesigndokument](solution-design.md). Om team har liknande krav för en dimension kan de använda samma anpassade variabel. Om till exempel plats A och plats B båda kräver en omfattande dimension, kan implementeringar för båda platserna skicka dessa data via eVar1.

   >[!IMPORTANT]
   >
   >Se till att alla anpassade variabler används på samma sätt i alla domäner. Använd inte samma eVar eller händelse för olika syften på era webbplatser.
1. Se till att varje domän har ett datalager som förenklar datainsamlingen. Data kan fortfarande samlas in utan ett datalager, men tillförlitligheten och varaktigheten i implementeringen minskar, särskilt när sajten genomgår omformningar.
1. Använd taggar i Adobe Experience Platform för att implementera Analytics. Olika webbplatser kommer troligtvis att kräva olika dataelement. Använd regler som är specifika för varje domän för att säkerställa att varje dataelement är korrekt ifyllt och tilldela sedan dessa dataelement till deras respektive eVars- och händelser. Se [taggöversikten](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).
1. Inkludera [Adobe Experience Cloud ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html) och använd funktionen [appendVisitorIDsTo](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html). Den här funktionen sammanfogar besökardata när användare klickar från en domän till en annan.

## Ändra en befintlig implementering med en global rapportserie

Processen med att flytta en befintlig implementering över flera webbplatser till en enda global rapportserie kräver mer tid och samordning mellan teamen i organisationen.

1. Bestäm om du vill använda någon av dina befintliga rapportsviter eller börja om från början med en ny rapportserie. Om du vill ändra användningsområdena för befintliga variabler i implementeringen rekommenderar vi att du börjar med en ny rapportserie.
2. Fastställ ett brytdatum för när du vill byta till en global rapportserie. Det bästa tillfället att göra en övergång är mellan två signifikanta rapportperioder eller tillsammans med större förändringar på er webbplats. Exempel är början av ett räkenskapskvartal eller räkenskapsår, under en webbplatsuppdatering eller ändring till ett nytt tagghanteringssystem.
3. Följ stegen ovan (skapa en rapportsserie, samla in rapporteringskrav i ett lösningsdesigndokument och skapa ett datalager på varje webbplats). När du implementerar taggar i Adobe Experience Platform validerar du implementeringen med en utvecklingsversion av din webbplats.
4. När du har bekräftat att implementeringen fungerar på dev, publicera taggimplementeringen på brytdatumet.

## Relaterade sidor

[Gå från taggning för flera programsviter till en global rapportserie och virtuella rapportsviter](../../components/vrs/vrs-considerations.md)
[Jämföra sammanslagningar och globala rapportsviter ](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)
