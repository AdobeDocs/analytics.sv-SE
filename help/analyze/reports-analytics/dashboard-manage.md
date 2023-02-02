---
description: Använd Kontrollpanelshanteraren för att kopiera, dela, arkivera och schemalägga kontrollpaneler för leverans.
subtopic: Dashboards
title: Kontrollpanelshanterare
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
feature: Reports & Analytics Basics
role: User, Admin
exl-id: abd5acf5-f743-4c94-81fb-fc6cc69e8f26
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 1%

---

# Kontrollpanelshanterare

{{ra-eol}}

Använd Kontrollpanelshanteraren för att kopiera, dela, arkivera och schemalägga kontrollpaneler för leverans.

>[!IMPORTANT]
>
>Det bästa sättet att använda kontrollpanelshanteraren är att inte ha fler än 300 kontrollpaneler för en enskild användare. Observera även att hanteraren läser in alla delade instrumentpaneler nedan, så var klok med att dela instrumentpaneler.

Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]**.

| Element | Beskrivning |
|--- |--- |
| Delad | Visar om instrumentpanelen delas. |
| Schemalagd | Här kan du schemalägga kontrollpanelen för leverans. |
| Visa arkiv | Den här funktionen är inte längre tillgänglig. |
| Skicka till användare | Här kan du dela en instrumentpanel. |
| Hantera | Gör att du kan redigera, kopiera och ta bort en kontrollpanel. |

## Hantera delade instrumentpaneler

Så här hanterar du delade instrumentpaneler:

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], leta reda på den delade kontrollpanelen (eller den äldre kontrollpanelen) som du vill hantera och välj ett eller flera av följande alternativ:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Alternativ </th> 
  <th class="chdeschd"> Beskrivning </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Visa arkiv</strong></td> 
  <td class="chdesc stentry"> Den här funktionen är inte längre tillgänglig. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Instrumentpanelsspelare</strong></td> 
  <td class="chdesc stentry"> <p>SiteCatalyst 14-servrar kommer inte längre att svara på dataförfrågningar från Dashboard Player. Alla instrumentpaneler som för närvarande visas i Dashboard Player kan nås via standardgränssnittet Rapporter och analyser eller skapas om som en realtidsinstrumentpanel. Kontrollpaneler i realtid är särskilt utformade för kontinuerlig visning och har helskärmsläge så att du kan visa dem på tv-apparater eller andra stora skärmar. </p> <p>Användaråtgärd krävs: Du måste sluta använda Dashboard Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Copy Me</strong></td> 
  <td class="chdesc stentry"> Lägger till en kopia i din lista med kontrollpaneler med samma namn som originalet. Du kan dock inte se några uppdateringar eller ändringar som görs av instrumentpanelens ägare. Om du kopierar en äldre kontrollpanel öppnas en tom kontrollpanel där du kan lägga till äldre innehåll. <p>Viktigt: Om de delade användarna på din instrumentpanel inte kan se de ändringar du har gjort på instrumentpanelen, bör du kontrollera Instrumentpanelshanteraren för att se om användarna har valt <span class="uicontrol"> Copy Me </span> alternativ. Om de gjorde det kan de inte se de uppdateringar/ändringar som du har gjort. Om du vill se alla ändringar/uppdateringar måste delade användare välja <span class="uicontrol"> På menyn </span> i Kontrollpanelshanteraren. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>På menyn</strong></td> 
  <td class="chdesc stentry"> Gör att du kan se ändringar/uppdateringar som görs av instrumentpanelens ägare. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Sluta dela</strong></td> 
  <td class="chdesc stentry"> Tar bort instrumentpanelen från listan med delade instrumentpaneler. </td> 
 </tr> 
</table>

## Migrera en äldre instrumentpanel

Befintliga gamla kontrollpaneler kommer att fortsätta att köras och du kan fortfarande redigera, hämta och schemalägga dem; Du kan dock inte längre skapa nya gamla kontrollpaneler. Vi rekommenderar att du uppgraderar befintliga gamla kontrollpaneler till det nyare instrumentpanelsformatet.

>[!NOTE]
>
>Flytta framåt, överväg att använda [Analysis Workspace-projekt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) och möjligheten att ladda ned och schemalägga dem.

När du kopierar den äldre kontrollpanelen öppnas den äldre kontrollpanelen för redigering, där du kan lägga till äldre innehåll eller nytt innehåll. När du kopierar en äldre kontrollpanel bevaras originalet i listan med äldre kontrollpaneler.

>[!NOTE]
>
>När du lägger till äldre innehåll på en kontrollpanel skapas en kontrollpanel som baseras på den senaste kontrollpanelsfunktionen. Den äldre rapportleten kan dock innehålla data som baseras på den tidigare dataplattformen.

**Så här migrerar du en äldre kontrollpanel i version 14.x**

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. I [!UICONTROL Manage] kolumn, under [!UICONTROL Legacy Dashboards], klicka **[!UICONTROL Copy to New Dashboard]**.

   Den kopierade kontrollpanelen öppnas i kontrollpanelens layoutredigerare.

   Se [Redigera instrumentpanels- och rapportdata](/help/analyze/reports-analytics/dashboard.md).

## Dela en kontrollpanel

Analysadministratörer kan dela (eller pusha) en kontrollpanel med flera användare. När du skickar kontrollpaneler till användare blir kontrollpanelerna tillgängliga i användarens [!UICONTROL Shared Dashboards] -menyn.

Så här delar du en kontrollpanel med flera användare:

1. I [!UICONTROL Dashboard Manager], leta upp kontrollpanelen och aktivera **[!UICONTROL Shared]**.
1. Klicka på **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. På [!UICONTROL Push Dashboard] väljer du målanvändare eller klickar på **[!UICONTROL Check All]**.
1. Klicka på **[!UICONTROL Save]**.

Om de delade användarna på din instrumentpanel inte kan se de ändringar du har gjort på instrumentpanelen, bör du kontrollera Instrumentpanelshanteraren för att se om användarna har valt **[!UICONTROL Copy Me]** alternativ. Om de gjorde det kan de inte se de uppdateringar/ändringar som du har gjort. Om du vill se alla ändringar/uppdateringar måste delade användare välja **[!UICONTROL On Menu]** i Kontrollpanelshanteraren.

## Schemalägg en kontrollpanel för leverans

I [!UICONTROL Dashboard Manager]kan du se om en kontrollpanel är schemalagd för leverans och redigera schemat. Instrumentpanelens leveransalternativ är identiska med rapportleveransalternativen.

1. Öppna en instrumentpanel.
1. Klicka på **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Se [Schemaläggning och distribution](/help/analyze/reports-analytics/scheduling.md) för mer information.
