---
description: Skapa en grundläggande behållare för datainsamling i Adobe Analytics
title: Skapa en rapportsvit
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 6%

---

# Skapa en rapportsvit

En rapportsvit är en silo data som Adobe Analytics använder för att ta fram rapporter. En organisation kan ha många rapportsviter, som alla innehåller olika datauppsättningar. Även om separata rapportsviter var viktiga tidigare har det blivit mer fördelaktigt att ha en enda rapportserie. Införandet av [virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html#virtual-report-suites) och tidsbearbetning av rapporter gör det möjligt för administratörer att skapa egna underuppsättningar av data, vilket ger flexibilitet att hämta både globala och platsspecifika data.

Den här artikeln är avsedd för systemnivåadministratörer eller Adobe Analytics-administratörer som ska förbereda datainsamlingen.

## Förutsättningar

[Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md): Kontrollera att en systemnivåadministratör har gett dig åtkomst till Adobe Analytics via Experience Cloud Admin Console.

## Skapa en rapportsvit {#create-report-suite}

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Klicka på **[!UICONTROL Create New]** > **[!UICONTROL Report Suite]**.
1. Välj antingen en fördefinierad mall eller en befintlig rapportserie att använda som [mall](/help/admin/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >Endast inställningar kan kopieras, inte data. Om kundtjänst kopierar inställningarna måste du lämna en skriftlig bekräftelse till den ansvarsfriskrivning som tillhandahålls av kundtjänst om riskerna. Se [Inställningar som inte kopierats från en källrapportsserie](/help/admin/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) för mer information.

1. Fyll i fälten som beskrivs i [Ny rapportsvit](/help/admin/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md).
1. Klicka på **[!UICONTROL Create Report Suite]**.

Ett rapportsvit-ID får innehålla högst 40 byte. Ett eget namn för en rapportsserie har en maxlängd på 255 byte.

## Felsökning

**När du har loggat in på Experience Cloud är Analytics-ikonen nedtonad.**

Det innebär att ditt konto inte har tilldelats rätt behörigheter till Analytics. Arbeta med en systemnivåadministratör i organisationen för att säkerställa att du tillhör en profil med tillräcklig behörighet för åtkomst till Adobe Analytics.

## Nästa steg

[Skapa en Adobe Analytics-taggegenskap](/help/implement/launch/create-analytics-property.md): Skapa ett område för att hantera er Analytics-implementering.
