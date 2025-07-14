---
description: Rankar länkaktivitet med visuella övertäckningar för att övervaka målgruppernas engagemang på dina webbsidor.
title: Activity Map - översikt
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: dee8f0a13a159f4c7902d2ccddd8848c4016b471
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 0%

---

# Activity Map - översikt

Adobe Analytics Activity Map är en funktion i Adobe Analytics som ger en visuell representation av användarinteraktionen på webbsidor och mobilappar. Det gör det möjligt för marknadsförare och analytiker att spåra och analysera användarinteraktioner som klickningar och rullningsbeteende. Activity Map genererar värmekartor och överläggsrapporter som visar de vanligaste elementen på en webbsida, vilket hjälper dig att optimera de digitala upplevelserna.

Det här avsnittet av dokumentationen fokuserar på Activity Map-övertäckningen. Det finns dock andra viktiga saker att göra med Activity Map:

* **Rapportsvitens inställning**: Activity Map måste vara aktiverat för en rapportserie. Se [Activity Map Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) i inställningarna för rapportsviten.
* **Implementering**: De flesta Activity Map-rapporter är tillgängliga direkt. Vissa webbplatser kan dock behöva implementeras ytterligare för att få ut så mycket som möjligt av länkspårningen. Följande implementeringsvariabler är tillgängliga:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filtrera klickdata efter länknamn.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filtrera klickdata efter regionnamn.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): Ändra attributet som fyller i Activity Map regiondimension.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): Anpassa logiken som används i Activity Map för att fylla i Activity Map Link-dimensionen.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): Anpassa logiken som används i Activity Map för att fylla i Activity Map regiondimension.
* **Dimensioner**: Förutom övertäckningstillägget har Activity Map flera dimensioner som du kan använda i Analysis Workspace.
   * [Activity Map Link](/help/components/dimensions/activity-map-link.md): Det länknamn som klickades på.
   * [Activity Map-region](/help/components/dimensions/activity-map-region.md): Regionnamnet som klickades på.
   * [Activity Map-sida](/help/components/dimensions/activity-map-page.md): Sidnamnet när användaren klickar på länken.
   * [Activity Map Link By Region](/help/components/dimensions/activity-map-link-by-region.md): Ett sammanfogat värde för Activity Map Link och Activity Map Region.

## Funktioner och fördelar

* **Visualisering av användarinteraktion**: Activity Map erbjuder en dynamisk visuell representation av användarbeteende, så att du kan se exakt var användarna klickar. Dessa visuella data gör det enklare att identifiera mönster, trender och intresseområden. Du kan sedan fatta välgrundade beslut om design, innehållsplacering och användarflöde.

* **Värmekartor**: Activity Map genererar värmekartor som visar de mest klickade eller interaktiva områdena på en webbsida. Värmekartor använder färgkodning för att representera engagemangsnivån, vilket gör att du kan identifiera hotspot-områden och prioritera uppmärksamhet för högkvalitativa områden. Den här informationen kan vara värdefull när du vill optimera knappar, länkar, formulär eller andra interaktiva element i call-to-action.

* **Överläggsrapporter**: Överläggsrapporter i Activity Map innehåller detaljerade klickvärden för specifika element på en webbsida. Genom att förstå klickfrekvensen och engagemangsnivåerna för enskilda element kan ni finjustera design- och innehållsstrategierna för att förbättra användarupplevelserna.

* **Segmentanalys**: Du kan analysera användarbeteenden baserat på olika segment, t.ex. trafikkällor, demografiska data eller personas. Genom att segmentera data kan ni identifiera värdefulla insikter i specifika användargrupper, vilket möjliggör personaliserade upplevelser och riktade marknadsföringsstrategier.

## Praktiska program

* **Webbplatsoptimering**: Activity Map hjälper dig att optimera dina webbplatser genom att identifiera underpresterande element, förbättra navigeringen och förbättra den övergripande användarupplevelsen. Genom att analysera användarinteraktioner kan ni fatta datadrivna beslut som effektiviserar användarflödena, förenklar formulären eller justerar innehållsplaceringen för maximal effekt.

* **Optimering av konverteringsgraden**: Genom att visualisera användarinteraktionen och analysera klickfrekvensen spelar Activity Map en viktig roll i arbetet med CRO. Ni kan identifiera hinder för konvertering och experimentera med olika designvarianter för att optimera konverteringsflöden, landningssidor och utcheckningsprocesser.

* **A/B-testning**: Activity Map kan kombineras med A/B-testning för att mäta effekten av design- eller innehållsändringar. Genom att jämföra interaktionsstatistik mellan olika versioner av en webbsida kan ni avgöra vilka variationer som leder till ökat användarengagemang, konverteringsgrader eller intäkter.

