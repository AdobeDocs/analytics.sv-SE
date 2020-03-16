---
description: Använd Kontrollpanelshanteraren för att kopiera, dela, arkivera och schemalägga kontrollpaneler för leverans.
subtopic: Dashboards
title: Kontrollpanelshanteraren
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 92eaaeafdd587febcfe7fe60f696baca0691b4bc

---


# Kontrollpanelshanteraren

Använd Kontrollpanelshanteraren för att kopiera, dela, arkivera och schemalägga kontrollpaneler för leverans.

>[!IMPORTANT]
>
>Det bästa sättet att använda kontrollpanelshanteraren är att inte ha fler än 300 kontrollpaneler för en enskild användare. Observera även att hanteraren läser in alla delade instrumentpaneler nedan, så var klok med att dela instrumentpaneler.

## Kontrollpanelshanteraren

Använd Kontrollpanelshanteraren för att kopiera, dela, arkivera och schemalägga kontrollpaneler för leverans.

Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Element | Beskrivning |
|--- |--- |
| Delad | Visar om instrumentpanelen delas. |
| Schemalagd | Här kan du schemalägga kontrollpanelen för leverans. |
| Visa arkiv | Den här funktionen är inte längre tillgänglig. |
| Skicka till användare | Här kan du dela en instrumentpanel. |
| Hantera | Gör att du kan redigera, kopiera och ta bort en kontrollpanel. |

## Hantera delade instrumentpaneler

Steg som beskriver hur du använder alternativen för hantering av delade instrumentpaneler.

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards]hittar du den delade instrumentpanel (eller äldre kontrollpanel) som du vill hantera och väljer ett eller flera av följande alternativ:

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
  <td class="chdesc stentry"> Lägger till en kopia i din lista med kontrollpaneler med samma namn som originalet. Du kan dock inte se några uppdateringar eller ändringar som görs av instrumentpanelens ägare. Om du kopierar en äldre kontrollpanel öppnas en tom kontrollpanel där du kan lägga till äldre innehåll. <p>Viktigt:  Om de delade användarna av din instrumentpanel inte kan se ändringar som du har gjort på instrumentpanelen, kontrollerar du din instrumentpanelshanterare för att se om användarna har valt <span class="uicontrol"> alternativet </span> Kopiera mig. Om de gjorde det kan de inte se de uppdateringar/ändringar som du har gjort. Om du vill se alla ändringar/uppdateringar måste delade användare markera <span class="uicontrol"> alternativet </span> På meny i Kontrollpanelshanteraren. </p> </td> 
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

> [!NOTE] Gå vidare, överväg att använda [Analysis Workspace-projekt](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) och möjligheten att hämta och schemalägga dem.

När du kopierar den äldre kontrollpanelen öppnas den äldre kontrollpanelen för redigering, där du kan lägga till äldre innehåll eller nytt innehåll. När du kopierar en äldre kontrollpanel bevaras originalet i listan med äldre kontrollpaneler.

> [!NOTE] När du lägger till äldre innehåll på en kontrollpanel skapas en kontrollpanel som baseras på den senaste kontrollpanelsfunktionen. Den äldre rapportleten kan dock innehålla data som baseras på den tidigare dataplattformen.

**Så här migrerar du en äldre kontrollpanel i version 14.x**

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Klicka under i [!UICONTROL Manage] kolumnen [!UICONTROL Legacy Dashboards]på **[!UICONTROL Copy to New Dashboard]**.

   Den kopierade kontrollpanelen öppnas i kontrollpanelens layoutredigerare.

   Se [Redigera instrumentpanel och Rapporteringsdata](/help/analyze/reports-analytics/dashboard.md).

## Dela en kontrollpanel

Steg som beskriver hur en administratör kan dela (eller överföra) en kontrollpanel till flera användare. När du skickar kontrollpaneler till användare blir kontrollpanelerna tillgängliga på användarens [!UICONTROL Shared Dashboards] meny.

1. Gå till [!UICONTROL Dashboard Manager]kontrollpanelen och aktivera **[!UICONTROL Shared]**.
1. Klicka på **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Markera målanvändarna på [!UICONTROL Push Dashboard] sidan eller klicka på **[!UICONTROL Check All]**.
1. Klicka på **[!UICONTROL Save]**.

Om de delade användarna av din instrumentpanel inte kan se ändringar som du har gjort på instrumentpanelen, kontrollerar du din instrumentpanelshanterare för att se om användarna har valt **[!UICONTROL Copy Me]** alternativet. Om de gjorde det kan de inte se de uppdateringar/ändringar som du har gjort. För att se alla ändringar/uppdateringar måste delade användare välja **[!UICONTROL On Menu]** alternativet i Kontrollpanelshanteraren.

## Schemalägg en kontrollpanel för leverans

I [!UICONTROL Dashboard Manager]kan du se om en kontrollpanel är schemalagd för leverans och redigera schemat. Instrumentpanelens leveransalternativ är identiska med rapportleveransalternativen.

1. Öppna en instrumentpanel.
1. Klicka på **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Mer information finns i [Schemalägg och distribution](/help/analyze/reports-analytics/scheduling.md) .

## Arkivera en kontrollpanel

> [!NOTE] Den här funktionen kommer inte längre att vara tillgänglig i januari 2020.

Steg som beskriver hur du arkiverar skickade kontrollpaneler som PDF-filer. Den arkiverade filen lagras i två år, eller tills du når en gräns på 4 GB för arkiverade rapporter, beroende på vilket som inträffar först.

1. Öppna en instrumentpanel.
1. Klicka på **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Aktivera i [!UICONTROL Email Report] gruppen **[!UICONTROL Archive]**.
1. Ange leveransalternativ och klicka sedan på **[!UICONTROL Send]**.

   Du kan visa arkiverade instrumentpaneler i Dashboard Manager. Du kan också öppna en kontrollpanel och klicka **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
