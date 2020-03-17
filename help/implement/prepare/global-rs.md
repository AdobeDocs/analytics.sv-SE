---
title: Globala rapportsviter i Adobe Analytics
description: Förstå fördelarna och kraven med att använda ett globalt rapporteringsprogram.
translation-type: tm+mt
source-git-commit: d7c4412feb85f4381d8811b29fc23c9c85d23555

---


# Överväganden för globala rapportsviter

En global rapportserie är en rapportserie som samlar in data från alla domäner och appar som organisationen äger. Denna datainsamlingsteknik kräver förberedelse och kan kräva samordning mellan team inom organisationen.

## Fördelar

Adobe rekommenderar att man i de flesta fall implementerar en global rapportserie.

* **Sammanställda data:** Med globala rapportsviter kan du se KPI:er och framgångshändelser på egna webbplatser. Segmentering och virtuella rapportsviter kan användas för att visa platsspecifika data.
* **Stöd för analys på olika enheter:** CDA kräver en rapportserie som samlar in data från flera platser, till exempel din webbplats och mobilapp. Separata enheter kan sammanfoga data om de implementeras på rätt sätt. Mer information finns i [Enhetsövergripande analys](../../components/cda/cda-home.md) i användarhandboken för komponenter.
* **Du behöver inte mer än en rapportserie:** Alla data kan samlas in i en enda rapportserie, så det är mindre troligt att en utvecklare av misstag skickar data till fel rapportserie.
* **Inga sammanslagningar:** Sammanslagningar är en funktion som är ganska daterad och som sammanställer data från enskilda rapporteringsprogram dagligen. Upplysta listor tar inte bort besöks- eller besöksdata, vilket kan leda till ett högt antal. Mer information finns i [Samlingar](../../admin/c-manage-report-suites/rollup-report-suite.md) i användarhandboken för Admin.
* **Spara tid:** Arbetsyteprojekt, klassificeringar, segment och beräknade värden är kopplade till samma globala rapportserie. Administratörer lägger mindre tid på att hantera dessa komponenter och datastyrning.
* **Exaktare varumärkesattribuering:** Om ett besök börjar på en webbplats och sedan klickar på en annan av dina ägda webbplatser innan en lyckad händelse utlöses, samlas attribueringen in korrekt. En besökare klickar till exempel på en betald söklänk och hamnar på plats A. De klickar sedan på en länk till webbplats B och gör sedan ett köp. En global rapportsvit har korrekta attribut som återgår till betalsökningar.
* **Förenklad implementering:** Eftersom alla varumärken/webbplatser skickar data till samma rapporteringsprogram justeras implementeringarna för varje webbplats. Den här tvingande styrningen säkerställer att en viss dimension eller mätvärden sparas i samma eVar eller händelse. Administratörer, testare, tagghanteringsägare och analytiker drar nytta av denna förenkling.

> [!NOTE] Att samordna en global rapportsvitsimplementering är ett stort projekt. Adobe rekommenderar att du samarbetar med en konsult för att minska antalet komplikationer och problem som kan uppstå.

## Starta en ny implementering med en global rapportserie

Använd följande allmänna riktlinjer för att förstå hur man implementerar en global rapportserie.

1. Skapa den globala rapportsviten i Adobe Analytics. Mer information finns i [Skapa en rapportsserie](../../admin/admin-console/create-report-suite.md) i användarhandboken för Admin.
2. Arbeta med team i organisationen som ansvarar för varje domän. Många team har rapporteringskrav som är specifika för deras verksamhetsområde.
3. Registrera och samla alla dessa krav i ett [konstruktionsdokument](solution-design.md). Om team har liknande krav för en dimension kan de använda samma anpassade variabel. Om till exempel plats A och plats B båda kräver en bredd-crumb-dimension, kan implementeringar för båda platserna skicka dessa data via eVar1.
   > [!IMPORTANT] Se till att alla anpassade variabler används på samma sätt i alla domäner. Använd inte samma eVar eller händelse för olika syften på olika platser.
4. Se till att varje domän har ett datalager som förenklar datainsamlingen. Data kan fortfarande samlas in utan ett datalager, men tillförlitligheten och varaktigheten i implementeringen minskar, särskilt när sajten genomgår omformningar.
5. Använd Adobe Experience Platform Launch för att implementera Analytics. Olika webbplatser kommer troligtvis att kräva olika dataelement. Använd regler som är specifika för varje domän för att säkerställa att varje dataelement är korrekt ifyllt och tilldela sedan dessa dataelement till deras respektive eVars- och händelser. Se [Startöversikt](https://docs.adobe.com/content/help/en/launch/using/overview.html) i användarhandboken för Adobe Experience Platform Launch.
6. Inkludera [Adobe Experience Cloud ID Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) och använd funktionen [appendVisitorIDsTo](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/appendvisitorid.html) . Den här funktionen sammanfogar besökardata när användare klickar från en domän till en annan.

## Ändra en befintlig implementering med en global rapportserie

Processen med att flytta en befintlig implementering över flera webbplatser till en enda global rapportserie kräver mer tid och samordning mellan teamen i organisationen.

1. Bestäm om du vill använda någon av dina befintliga rapportsviter eller börja om från början med en ny rapportserie. Om du vill ändra användningsområdena för befintliga variabler i implementeringen rekommenderar vi att du börjar med en ny rapportserie.
2. Ange ett brytdatum för när du vill byta till en global rapportserie. Det bästa tillfället att göra en övergång är mellan två signifikanta rapportperioder eller tillsammans med större förändringar på er webbplats. Exempel är början av ett räkenskapskvartal eller räkenskapsår, under en webbplatsuppdatering eller ändring till ett nytt tagghanteringssystem.
3. Följ stegen ovan (skapa en rapportsserie, samla in rapporteringskrav i ett lösningsdesigndokument och skapa ett datalager på varje webbplats). När du implementerar Launch validerar du implementeringen med en utvecklingsversion av din webbplats.
4. När du har bekräftat att implementeringen fungerar på dev, publicerar du implementeringen av Launch på brytdatumet.

## Relaterade sidor

[Gå från taggning av flera programsviter till en global rapportserie och virtuella rapportsviter](../../components/vrs/vrs-considerations.md)[Jämföra sammanslagningar och globala rapportsviter](../../admin/c-manage-report-suites/rollup-report-suite.md)
