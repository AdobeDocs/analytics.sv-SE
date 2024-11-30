---
description: Översikt över hur du använder mallar i Analysis Workspace.
title: Använd mallar
feature: Analysis Workspace
role: User, Admin
hide: true
hidefromtoc: true
exl-id: 9e5d1b35-e2b3-4fa5-af12-67bb913675bc
source-git-commit: 3eb996179b359bc77e04cdc8a469b79a9b2cc621
workflow-type: tm+mt
source-wordcount: '18027'
ht-degree: 0%

---

# Använd mallar

Mallar (eller företagsmallar) i Analysis Workspace ger snabba insikter i de vanligaste rapportscenarierna. Nedan följer några exempel på frågor som du kan besvara med mallar:

* Hur många personer besöker er webbplats
* Hur många av dessa besökare är unika besökare (räknas bara en gång)
* Hur de kom till webbplatsen (t.ex. om de följde en länk eller kom dit direkt)
* Vilka nyckelord besökarna använde för att söka efter webbplatsinnehåll
* Hur länge besökarna var kvar på en viss sida eller på hela webbplatsen
* Vilka länkar besökarna klickade på och när de lämnade webbplatsen
* Vilka marknadsföringskanaler är mest effektiva för att generera intäkter eller konverteringshändelser?
* Hur mycket tid de tillbringade med att titta på en video
* Vilka webbläsare och enheter de använde för att besöka din webbplats

Följande information beskriver hur du får åtkomst till och använder mallar från fliken [!UICONTROL Templates] i Analysis Workspace.

## Öppna och köra en mall

1. I Analysis Workspace väljer du fliken [!UICONTROL **Workspace**].

   <!--update screenshot -->

   ![Fliken Rapporter](assets/view-prebuilt-templates.png)

1. Välj någon av följande flikar i avsnittet [!UICONTROL **Mallar**]:

   * **[!UICONTROL Adobe templates]**: Visar alla mallar som tillhandahålls av Adobe.

   * **[!UICONTROL _login_company_name _-mallar]**: Visar alla företagsmallar som har skapats för din organisation.

     Företagsmallar kan bara skapas av en administratör. Mer information om hur du skapar en företagsmall finns i [Skapa och hantera mallar](/help/analyze/analysis-workspace/reports/create-company-reports.md).

1. Välj om du vill visa mallar i en kolumnvy eller i en kortvy genom att antingen markera kolumnvyikonen ![kolumnvy](assets/column-view-icon.png) eller kortvyikonen ![kortvy](assets/card-view-icon.png) .

1. I sökfältet börjar du skriva namnet på mallen som du vill söka efter och väljer den sedan i listan med mallar. Du kan också söka i malllistan efter hjälp, eVar och händelsenummer. <!-- still true? -->

   eller

   Välj den mallkategori som du vill visa och välj sedan mallen i listan med mallar.

   >[!TIP]
   >
   >Om du vill navigera på menyn med piltangenterna trycker du på snedstreck (/) och sedan på nedpilen. Tryck på Retur för att läsa in den valda mallen.

   En lista över tillgängliga mallar finns i avsnittet [Tillgängliga mallar](#available-reports) nedan.

1. (Valfritt) Visa och använd mallar som innehåller komponenter som inte är tillgängliga i rapportsviten. (Som standard är de enda mallarna som visas de som använder komponenter som är tillgängliga i din rapportserie.) <!--does this apply to AA? -->

## Skapa ett projekt baserat på en mall {#use-reports}

En mall kanske inte passar dina behov exakt, men den kan göra att du kommer nära. I dessa fall kan du använda mallen som utgångspunkt och sedan anpassa den så att den passar dina specifika syften.

Om du navigerar bort från en mall efter att ha gjort ändringar uppmanas du att spara eller ignorera ändringarna. Om du sparar ändringar i en mall sparas mallen som ett nytt projekt.

Så här anpassar du en mall och sparar den som ett projekt:

1. I Adobe Analytics väljer du fliken [!UICONTROL **Workspace**].

1. Välj fliken [!UICONTROL **Mallar**].

1. Markera den mall som du vill visa. Välj till exempel mallen [!UICONTROL **Sidor**] under [!UICONTROL **Mest populära**].

   ![Sidrapport](assets/pages-report.png)

1. Sidmallen, som den visas i Analysis Workspace, visar två [visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([stapeldiagram](/help/analyze/analysis-workspace/visualizations/bar.md) och [sammanfattningsnummer](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) samt en [friformstabell](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). Det mätvärde som används är förekomster.
1. Gör något av följande:

   * Visa mallen.
   * Dra ett eller flera segment till segmentsläppzonen längst upp. Dra till exempel segmentet [!UICONTROL **Mobila kunder**] och visa resultatet.
   * Ändra datumintervallet genom att gå till kalendern längst upp till höger.
   * Lägg in dimensionsanalyser, dra in andra mätvärden och anpassa mallen efter behov.

1. (Valfritt) Spara mallen som ett projekt genom att välja [!UICONTROL **Projekt**] > [!UICONTROL **Spara**].

   Mallen sparas som ett nytt projekt. Den ändrar inte den befintliga mallen. Mer information om hur du sparar projekt finns i [Spara projekt](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

## Tillgängliga mallar

Så här kommer du åt alla tillgängliga färdiga mallar:

1. I Adobe Analytics väljer du fliken [!UICONTROL **Workspace**] och sedan fliken [!UICONTROL **Mallar**] .

   Fördefinierade mallar ordnas efter kategori.

   <!--add screenshot-->

1. Välj en kategori om du vill visa mallarna i den.

   Följande avsnitt motsvarar de tillgängliga kategorierna och ger information om varje mall.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

### Mest populära {#most-popular}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--training"
>title="Mall för självstudiekurser"
>abstract="Lär dig vanliga Analysis Workspace-termer och steg för att skapa din första analys."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--pagesRankedReport"
>title="Identifiera de mest populära och minst populära sidorna."
>abstract="**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.<br/>Den här mallen använder måtten Siddimension och Sidvyer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--pageViewsOvertimeReport"
>title="Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. "
>abstract="**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.<br/>Den här mallen använder måtten Dag och Sidvisning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitsOvertimeReport"
>title="Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.<br/>Den här mallen använder måtten Dag och Besök."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitorsOvertimeReport"
>title="Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. "
>abstract="**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.<br/>Den här mallen använder måtten Dag och Unika besökare. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--keyMetricsReport"
>title="Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. <br/>Den här mallen använder måtten Dag, Sidvisning, Besök och Unika besökare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--siteSectionRankedReport"
>title="Se de populäraste eller mest högpresterande avsnitten på webbplatsen."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.<br>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.<br/>Den här mallen använder dimensionen Platsavsnitt och Visits-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--next-page-report"
>title="Se de vanligaste platserna där man besöker en viss plats omedelbart efter besök eller omedelbart."
>abstract="**Detta kan hjälpa dig** att förstå hur trafiken flyttas från en viss sida till andra delar av webbplatsen och förstå de sökvägar som användarna tar för att komma fram till en viss sida.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning. Eller utvärdera om informationen på den aktuella sidan kan ge den riktning eller de åtgärder som folk vill ha när de kommer från föregående sidor. Du kan också bedöma om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan.<br/>Den här mallen använder panelen Nästa eller Föregående objekt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--campaignRankedReport"
>title="Visa länkarna som lyckades mest när det gällde att köra trafik till er webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka spårningskoder (och de länkar de är kopplade till) som var de mest använda för att komma åt din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att justera din strategi för var du lägger till länkar till din webbplats.<br/>Den här mallen använder spårningskoddimensionen och Visits-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--productsRankedReport"
>title="Visa antalet order per produkt. Data visas över en tidsperiod."
>abstract="**Detta kan hjälpa dig** att förstå vilka produkter som har störst eller lägst efterfrågan.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera dina marknadsföringsstrategier för att marknadsföra högpresterande produkter eller för att förbättra eller avbryta underpresterande produkter. Du kan också justera produktlagret baserat på din analys av data.<br/>Den här mallen använder produktdimensionen och ordermåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--lastTouchChannelRankedReport"
>title="Visa de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att förstå vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.<br/>Den här mallen använder dimensionen Senaste beröringskanal och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--lastTouchChannelDetailRankedReport"
>title="Visa information om de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att förstå inte bara vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar, utan även information om dessa marknadsföringskanaler. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.<br/>Den här mallen använder dimensionen Senaste beröringskanaldetalj och det unika besökarmåttet. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--revenueOvertimeReport"
>title="Visa det monetära beloppet för produkter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att förstå hur intäkterna ökar eller minskar över tid. Du kan kombinera det här måttet med vilken dimension som helst för att lära dig vilka dimensionsobjekt som har bidragit till intäkterna.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel framtida projektintäkter baserade på tidigare trender. Ni kan också lägga till ytterligare en dimension, som spårningskoddimensionen, för att lära er vilka kampanjer som genererar störst intäkter.<br/>Den här mallen använder måtten Dag och Intäkter."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--ordersOvertimeReport"
>title="Visa det totala antalet inköpshändelser. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur intresset för dina produkter och tjänster ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som gör mest beställningar och hur dessa beställningar trendar över tid.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra order före och efter det att kampanjen har startats. Eller så kan du jämföra årsavgiftsbeställningar.<br/>Den här mallen använder måtten Dag och Order."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--unitsOvertimeReport"
>title="Visa det totala antalet enheter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur enhetsförsäljningen ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som köper flest enheter och hur enhetsförsäljningen trendar över tid.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra enhetsförsäljningen före och efter att kampanjen har startats. Du kan också jämföra försäljningen per år under helger.<br/>Den här mallen använder måtten Dag och Enheter."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Utbildning - självstudiekurs**] | Lär dig vanliga Analysis Workspace-termer och steg för att bygga din första analys |
| [!UICONTROL **Sidor**] | <!--duplicated in Engagement section--> Identifiera de mest populära och minst populära sidorna. <p>**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.</p><p>Den här mallen använder måtten [Siddimension](/help/components/dimensions/page.md) och [Sidvisning](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Sidvyer**] | <!--duplicated in Engagement section--> Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>Den här mallen använder måtten [Dag](/help/components/dimensions/day.md) och [Sidvisning](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Besök**] | <!--duplicated in Engagement section--> Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md) och [Besök](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Besökare**] | <!--duplicated in Engagement section--> Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.</p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Nyckeltal**] | <!--duplicated in Engagement section--> Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. </p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md), [Sidvisning](/help/components/metrics/page-views.md), [Besök ](/help/components/metrics/visits.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Webbplatsavsnitt**] | Se de populäraste eller mest högpresterande avsnitten på webbplatsen. <p>**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.</p> <p>Den här mallen använder dimensionen [Platsavsnitt](/help/components/dimensions/site-section.md) och [Besök ](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Nästa och Föregående sida**] | Se de vanligaste platserna där man besöker en viss plats omedelbart efter besök eller omedelbart. <p>**Detta kan hjälpa dig** att förstå hur trafiken flyttas från en viss sida till andra delar av webbplatsen och förstå de sökvägar som användarna tar för att komma fram till en viss sida.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning. Eller utvärdera om informationen på den aktuella sidan kan ge den riktning eller de åtgärder som folk vill ha när de kommer från föregående sidor. Du kan också bedöma om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan.</p><p>Den här mallen använder panelen [Nästa eller Föregående objekt](/help/analyze/analysis-workspace/c-panels/next-previous.md).</p> |
| [!UICONTROL **Kampanjer (spårningskod)**] | Visa länkarna som lyckades mest när det gällde att köra trafik till er webbplats. <p>**Detta kan hjälpa dig** att bättre förstå vilka spårningskoder (och de länkar de är kopplade till) som var de mest använda för att komma åt din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att justera din strategi för var du lägger till länkar till din webbplats.</p><p>I den här mallen används måtten [Spårningskod](/help/components/dimensions/tracking-code.md) och [Besök](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Produkter**] | Visa antalet order per produkt. Data visas över en tidsperiod. <p>**Detta kan hjälpa dig** att förstå vilka produkter som har störst eller lägst efterfrågan.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera dina marknadsföringsstrategier för att marknadsföra högpresterande produkter eller för att förbättra eller avbryta underpresterande produkter. Du kan också justera produktlagret baserat på din analys av data.</p><p>Den här mallen använder [produktdimensionen](/help/components/dimensions/product.md) och [ordermåttet](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Senaste beröringskanal**] | Visa de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att förstå vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.</p><p>I den här mallen används måtten [Senaste beröringskanal](/help/components/dimensions/last-touch-channel.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Senaste beröringskanaldetalj**] | Visa information om de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att förstå inte bara vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar, utan även information om dessa marknadsföringskanaler. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.</p><p>Den här mallen använder dimensionen [Senaste beröringskanaldetalj](/help/components/dimensions/last-touch-detail.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Intäkter**] | Visa det monetära beloppet för produkter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder.<p>**Detta kan hjälpa dig** att förstå hur intäkterna ökar eller minskar över tid. Du kan kombinera det här måttet med vilken dimension som helst för att lära dig vilka dimensionsobjekt som har bidragit till intäkterna.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel framtida projektintäkter baserade på tidigare trender. Ni kan också lägga till ytterligare en dimension, som spårningskoddimensionen, för att lära er vilka kampanjer som genererar störst intäkter.</p><p>I den här mallen används [dagdimensionen](/help/components/dimensions/day.md) och [intäktsmåttet](/help/components/metrics/revenue.md).</p> |
| [!UICONTROL **Beställningar**] | Visa det totala antalet inköpshändelser. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur intresset för dina produkter och tjänster ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som gör mest beställningar och hur dessa beställningar trendar över tid.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra order före och efter det att kampanjen har startats. Eller så kan du jämföra årsavgiftsbeställningar.</p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md) och [Beställningar](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Enheter**] | Visa det totala antalet enheter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur enhetsförsäljningen ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som köper flest enheter och hur enhetsförsäljningen trendar över tid.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra enhetsförsäljningen före och efter att kampanjen har startats. Du kan också jämföra försäljningen per år under helger.</p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md) och [Enheter](/help/components/metrics/units.md).</p> |

### Engagemang {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.<br/>Den här mallen använder måtten Dag och Tid per besök (sekunder)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Visa den genomsnittliga tiden som användare tillbringar före en lyckad händelse."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur lång tid det tar för besökarna att utföra en önskad åtgärd, till exempel göra ett köp.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om ändringar av din webbplats förbättrar besökarens förmåga att snabbt nå en lyckad händelse.<br/>Den här mallen använder dimensionen Tid före händelse och måttet för unika besökare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-content-consumption"
>title="Se vilket webbinnehåll som konsumeras mest och engagerande användare."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen.<br/>I den här mallen används måtten Siddimension och Sidvisning, Visits-måttet, det unika besökarmåttet, starthastighetsmåttet, avhoppsfrekvensen, avslutningsmåttet och innehållshastighetsmåttet. Flödesvisualiseringar används också för in-, avslutnings- och toppavsnitt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-content-consumption"
>title="Se vilket medieinnehåll som konsumeras mest och engagerande användare."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen.<br/>I den här mallen används måtten Siddimension och Sidvisning, Visits-måttet, det unika besökarmåttet, starthastighetsmåttet, avhoppsfrekvensen, avslutningsmåttet och innehållshastighetsmåttet. Flödesvisualiseringar används också för in-, avslutnings- och toppsektioner, en satsytevisualisering som visar sidvyer för de vanligaste sidorna, en streckvisualisering som visar sidvisningar efter paketerad tid och en linjevisualisering som visar en trendvy över den genomsnittliga tiden som har tillbringats på webbplatsen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Visa var personer lämnar eller fortsätter via en fördefinierad sidsekvens."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer faller bort från användarresan.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera konverteringsgraden via specifika processer på webbplatsen (till exempel en köp- eller registreringsprocess) eller analysera korrelationer mellan händelser på webbplatsen. (Exempel: hur många procent av de personer som tittade på din integritetspolicy gick vidare till att köpa en produkt.) Du kan också använda den här mallen för att utföra jämförelser sida vid sida av två olika segment i samma rapport.<br/>Den här mallen använder utfallsvisualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Se vilka enheter som används i alla delar av resan."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur många som interagerar med ert varumärke, vilka typer av enheter de använder och hur deras användning av flera enheter påverkar deras upplevelse. Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra en uppgift? Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de? Och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera vissa delar av användarresan för en mobil upplevelse.<br/>Den här mallen använder värdena för Flödesvisualisering, Utfallsvisualisering, Kohortanalys, Personmått och Unika enheter."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Se vilka era lojala användare är och vad de gör på er webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur många gånger den genomsnittliga personen besöker din webbplats, hur ofta personer återvänder till webbplatsen och hur många dagar som förflutit mellan återkomstbesöken.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som är mest effektivt för att ta personer tillbaka till webbplatsen.<br/>Den här mallen använder Visits-måttet och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Se trender och de viktigaste mätvärdena för medieanvändning på alla digitala enheter."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur besökare konsumerar ljudinnehåll på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som konsumeras mest.<br/>Den här mallen använder Visits-måttet och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Se trender och de viktigaste mätvärdena för mediekonsumtion på alla digitala enheter."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur många gånger den genomsnittliga personen besöker din webbplats, hur ofta personer återvänder till webbplatsen och hur många dagar som förflutit mellan återkomstbesöken.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som är mest effektivt för att ta personer tillbaka till webbplatsen.<br/>Den här mallen använder Visits-måttet och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--page-summary-report"
>title="Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.<br/>Den här mallen använder måtten Dag och Tid per besök (sekunder)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Visa det antal gånger en dimensionsobjekt fanns under en omladdning. En besökare som uppdaterar sin webbläsare är det vanligaste sättet att utlösa en omladdning."
>abstract="**Detta kan hjälpa dig** att identifiera när det kan uppstå problem på en viss sida som uppmanar en besökare att läsa in sidan igen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sidor som har problem som behöver åtgärdas.<br/>Den här mallen använder måttet Läs in igen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.<br/>Den här mallen använder måtten Dag och Tid per besök (sekunder)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageRankedReport"
>title="Visa de översta sidorna som andra kommer åt när de besöker webbplatsen första gången."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Visa de populäraste sidorna som andra kommer åt när de besöker webbplatsen för första gången under besökarens livstid."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Visa antalet besök som bestod av en enda unik sida."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.<br/>Den här mallen använder dimensionen för besök på en sida."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--exitPageRankedReport"
>title="Visa de översta sidorna som andra kommer åt direkt innan de lämnar din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka sidor som leder personer bort från webbplatsen. <br/>**Baserat på vad du lär dig kan du** göra något av följande, till exempel uppdatera vanliga avslutssidor för att optimera upplevelsen som andra får innan de lämnar webbplatsen, eller inkludera innehåll eller länkar för att uppmuntra andra att stanna kvar på webbplatsen.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Visa prestandadata för din Adobe Experience Manager-webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå värdeberäkning från Adobe Experience Manager.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera inställningarna för Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Visa och analysera effekterna av ITP (Intelligent Tracking Prevention) på datainsamling och rapportering."
>abstract="**Detta kan hjälpa dig** att bättre förstå potentiella dataförluster på grund av cookie-begränsningar som ITP har infört.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att anpassa analysinställningarna för att minimera effekten av ITP."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Nyckeltal**] | <!--duplicated in Most popular section--> Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. </p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md), [Sidvisning](/help/components/metrics/page-views.md), [Besök ](/help/components/metrics/visits.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Sidvyer**] | <!--duplicated in Most popular section-->Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>Den här mallen använder måtten [Dag](/help/components/dimensions/day.md) och [Sidvisning](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Sidor**] | <!--duplicated in Most popular section-->Identifiera de mest populära och minst populära sidorna. <p>**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.</p><p>Den här mallen använder måtten [Siddimension](/help/components/dimensions/page.md) och [Sidvisning](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Besök**] | <!--duplicated in Most popular section-->Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md) och [Besök](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Besökare**] | <!--duplicated in Most popular section-->Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.</p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Tid per besök**] | Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.</p><p>Den här mallen använder måtten [Dag](/help/components/dimensions/day.md) och [Tid per besök (sekunder) ](/help/components/metrics/time-spent-per-visit.md).</p> |
| [!UICONTROL **Tid före händelse**] | Visa den genomsnittliga tiden som användare tillbringar före en lyckad händelse. <p>**Detta kan hjälpa dig** att bättre förstå hur lång tid det tar för besökarna att utföra en önskad åtgärd, till exempel göra ett köp.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om ändringar av din webbplats förbättrar besökarens förmåga att snabbt nå en lyckad händelse.</p><p>I den här mallen används måtten [Tid före händelse](/help/components/dimensions/time-prior-to-event.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Webbplatsavsnitt**] | <!--duplicated in Most popular section-->Se de populäraste eller mest högpresterande avsnitten på webbplatsen. <p>**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.</p> <p>Den här mallen använder dimensionen [Platsavsnitt](/help/components/dimensions/site-section.md) och [Besök ](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Realtid**] | Visa de dimensioner och mätvärden som samlas in på din webbplats. <p>**Det här kan hjälpa dig** att bättre förstå vad som är trender på din webbplats.</p><p>**Baserat på vad du lär dig kan du** svara på och aktivt hantera prestandan för ditt aktuella marknadsföringsinnehåll och -kampanjer.</p> <p>Den här mallen använder [realtidsrapporten](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> |
| [!UICONTROL **Webbinnehållsförbrukning**] | Se vilket webbinnehåll som konsumeras mest och engagerande användare.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen <!-- not sure about these takeaways... -->.</p> <p>I den här mallen används måtten [Siddimension](/help/components/dimensions/page.md) och [Sidvisning](/help/components/metrics/page-views.md), [Besök-måttet](/help/components/metrics/visits.md), [Unika besökare](/help/components/metrics/unique-visitors.md), [Ankomsthastighetsmätningen](/help/components/metrics/entries.md), [avhoppsfrekvensen](/help/components/metrics/bounce-rate.md) och [Avsluta hastighetsmätningen](/help/components/metrics/exits.md) och måttet [Innehållshastighet ](/help/components/metrics/content-velocity.md) . [Flödesvisualiseringar](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) används också för in-, avslutnings- och toppavsnitt.</p> |
| [!UICONTROL **Medieinnehållsförbrukning**] | Se vilket medieinnehåll som konsumeras mest och engagerande användare.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen <!-- not sure about these takeaways... -->.</p> <p>I den här mallen används måtten [Siddimension](/help/components/dimensions/page.md) och [Sidvisning](/help/components/metrics/page-views.md), [Besök-måttet](/help/components/metrics/visits.md), [Unika besökare](/help/components/metrics/unique-visitors.md), [Ankomsthastighetsmätningen](/help/components/metrics/entries.md), [avhoppsfrekvensen](/help/components/metrics/bounce-rate.md) och [Avsluta hastighetsmätningen](/help/components/metrics/exits.md) och måttet [Innehållshastighet ](/help/components/metrics/content-velocity.md) . [Flödesvisualiseringar](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) används också för avsnitt som ska anges, avslutas och för avsnitt som ska visas överst. [Satterplot-visualisering](/help/analyze/analysis-workspace/visualizations/scatterplot.md) visar sidvisningar för de vanligaste sidorna. [Bar-visualisering](/help/analyze/analysis-workspace/visualizations/bar.md) visar sidvisningar efter paketerad tid och en [linjevisualisering](/help/analyze/analysis-workspace/visualizations/line.md) som visar en trendvy över den genomsnittliga tiden på webbplatsen.</p> |
| [!UICONTROL **Nästa och föregående sidflöde**] | Se de vanligaste platserna där man besöker en viss plats.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att besöka innan de lämnar webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen <!-- not sure about these takeaways... -->.</p> <p>I den här mallen används måtten [Siddimension](/help/components/dimensions/page.md) och [Sidvisning](/help/components/metrics/page-views.md), [Besök-måttet](/help/components/metrics/visits.md), [Unika besökare](/help/components/metrics/unique-visitors.md), [Ankomsthastighetsmätningen](/help/components/metrics/entries.md), [avhoppsfrekvensen](/help/components/metrics/bounce-rate.md) och [Avsluta hastighetsmätningen](/help/components/metrics/exits.md) och måttet [Innehållshastighet ](/help/components/metrics/content-velocity.md) . [Flödesvisualiseringar](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) används också för avsnitt som ska infogas, avslutas och för avsnitt som ska placeras överst. [Scatterplot-visualisering](/help/analyze/analysis-workspace/visualizations/scatterplot.md) visar sidvisningar för de vanligaste sidorna, en [Bar-visualisering](/help/analyze/analysis-workspace/visualizations/bar.md) som visar sidvisningar efter paketerad tid och en [Line-visualisering](/help/analyze/analysis-workspace/visualizations/line.md) som visar en trendvy över den genomsnittliga tiden på webbplatsen.</p> |
| [!UICONTROL **Utfall**] | Visa var personer lämnar eller fortsätter via en fördefinierad sidsekvens.<p>**Det här kan hjälpa dig** att bättre förstå var personer faller bort från användarresan.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera konverteringsgraden via specifika processer på webbplatsen (till exempel en köp- eller registreringsprocess) eller analysera korrelationer mellan händelser på webbplatsen. (Exempel: hur många procent av de personer som tittade på din integritetspolicy gick vidare till att köpa en produkt.) Du kan också använda den här mallen för att utföra jämförelser sida vid sida av två olika segment i samma rapport.</p> <p>Den här mallen använder [Utfallsvisualisering](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> |
| [!UICONTROL **Enhetsövergripande analys**] | Se vilka enheter som används i alla delar av resan.<p>**Detta kan hjälpa dig** att bättre förstå hur många som interagerar med ert varumärke, vilka typer av enheter de använder och hur deras användning av flera enheter påverkar deras upplevelse. Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra en uppgift? Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de? Och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera vissa delar av användarresan för en mobil upplevelse.</p> <p>Den här mallen använder [Flödesvisualisering](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Utfallsvisualisering](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Kohortanalys](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [personmätningen](/help/components/metrics/people.md) och [det unika enhetsmåttet](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Webbbevarande**] | Se vilka era lojala användare är och vad de gör på er webbplats.<p>**Detta kan hjälpa dig** att bättre förstå hur många gånger den genomsnittliga personen besöker din webbplats, hur ofta personer återvänder till webbplatsen och hur många dagar som förflutit mellan återkomstbesöken.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som är mest effektivt för att ta personer tillbaka till webbplatsen.<p>I den här mallen används måtten [Besök](/help/components/metrics/visits.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Medieljudförbrukning**] | Se trender och de viktigaste mätvärdena för medieanvändning på alla digitala enheter.<p>**Det här kan hjälpa dig** att bättre förstå hur besökare konsumerar ljudinnehåll på din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som konsumeras mest.<p>I den här mallen används måtten [Besök](/help/components/metrics/visits.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Medieåtergivning, frekvens, lojalitet**] | Se trender och de viktigaste mätvärdena för mediekonsumtion på alla digitala enheter.<p>**Detta kan hjälpa dig** att bättre förstå hur många gånger den genomsnittliga personen besöker din webbplats, hur ofta personer återvänder till webbplatsen och hur många dagar som förflutit mellan återkomstbesöken.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som är mest effektivt för att ta personer tillbaka till webbplatsen.<p>I den här mallen används måtten [Besök](/help/components/metrics/visits.md) och [Unika besökare](/help/components/metrics/unique-visitors.md).</p> |
| **[!UICONTROL Page Analysis]** > [!UICONTROL **Sidsammanfattning**] | Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.</p><p>Den här mallen använder måtten [Dag](/help/components/dimensions/day.md) och [Tid per besök (sekunder) ](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Page Analysis]** > [!UICONTROL **Läs in igen**] | Visa det antal gånger en dimensionsobjekt fanns under en omladdning. En besökare som uppdaterar sin webbläsare är det vanligaste sättet att utlösa en omladdning. <p>**Detta kan hjälpa dig** att identifiera när det kan uppstå problem på en viss sida som uppmanar en besökare att läsa in sidan igen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sidor som har problem som behöver åtgärdas.</p><p>Den här mallen använder måttet [Läser in igen](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/reloads).</p> |
| **[!UICONTROL Page Analysis]** > [!UICONTROL **Tid som använts på sidan**] | Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.</p><p>Den här mallen använder måtten [Dag](/help/components/dimensions/day.md) och [Tid per besök (sekunder) ](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Startsidor**] | Visa de översta sidorna som andra kommer åt när de besöker webbplatsen för en viss session. <p>**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.</p><p>Den här mallen använder måttet Sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering.</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Ursprungliga anmälningssidor**] | Visa de populäraste sidorna som andra kommer åt när de besöker webbplatsen för första gången under besökarens livstid. <p>**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.</p><p>Den här mallen använder måttet Sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering.</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Besök enstaka sidor**] | Visa antalet besök som bestod av en enda unik sida. <p>**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.</p><p>Den här mallen använder dimensionen [Enkelsidiga besök](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/single-page-visits).</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Avsluta sidor**] | Visa de översta sidorna som andra kommer åt direkt innan de lämnar din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka sidor som leder personer bort från webbplatsen. </p><p>**Baserat på vad du lär dig kan du** göra något av följande, till exempel uppdatera vanliga avslutssidor för att optimera upplevelsen som andra får innan de lämnar webbplatsen, eller inkludera innehåll eller länkar för att uppmuntra andra att stanna kvar på webbplatsen.</p><p>Den här mallen använder måttet Sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering.</p> |
| [!UICONTROL **AEM**] > [!UICONTROL **Webbplatsprestanda**] > [!UICONTROL **AEM Webbplatsprestanda**] | Visa prestandadata för din Adobe Experience Manager-webbplats.  <p>**Det här kan hjälpa dig** att bättre förstå värdeberäkning från Adobe Experience Manager.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera inställningarna för Experience Manager.</p> |
| [!UICONTROL **ITP-effekt**] | Visa och analysera effekterna av ITP (Intelligent Tracking Prevention) på datainsamling och rapportering. <p>**Detta kan hjälpa dig** att bättre förstå potentiella dataförluster på grund av cookie-begränsningar som ITP har infört.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att anpassa analysinställningarna för att minimera effekten av ITP.</p> |




Ignorera under detta

| Menyalternativ | Rapporter under det här menyobjektet |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Självstudiekurs (befintlig Workspace-mall)</li><li>Sidor (Vad är mina översta sidor?)</li><li>Sidvyer (hur många sidvyer skapar jag?)</li><li>Besök (hur många besök får jag?)</li><li>Besökare (hur många besökare får jag?)</li><li>Viktiga mätvärden (Hur fungerar mina viktigaste mätvärden?)</li><li>Webbplatsavsnitt (Vilka avsnitt på min webbplats genererade de flesta sidvyerna?)</li><li>Realtid (vad är trender på min webbplats och varför?)</li><li>Nästa sida (Vilka är de nästa sidor som besökarna går till?)</li><li>Föregående sida (Vilka är de föregående sidorna som mina besökare gick till?)</li><li>Kampanjer (Vilka kampanjer driver på min nyckelstatistik?)</li><li>Produkter (Vilka produkter driver på min nyckelstatistik?)</li><li>Senaste beröringskanal (Vilken senaste beröringskanal fungerar bäst?</li><li>Senaste beröringskanaldetalj (Vilken specifik sista beröringskanal presterar bättre än andra?)</li><li>Intäkter (hur fungerar mina intäkter?)</li><li>Beställningar (Hur fungerar mina order?)</li><li>Enheter (hur många enheter säljer jag?)</li></ul> |
| **[!UICONTROL Engagement]** | <ul><li>Viktiga mätvärden (Hur fungerar mina viktigaste mätvärden?)</li><li>Sidvyer (hur många sidvyer skapar jag?)</li><li>Sidor (Vad är mina översta sidor?)</li><li>Besök (hur många besök får jag?)</li><li>Besökare (hur många besökare får jag?)</li><li>Tid per besök (hur mycket tid tillbringar mina användare per besök?)</li><li>Tid före händelse (Hur mycket tid tillbringar mina användare före en lyckad händelse?)</li><li>Webbplatsavsnitt (Vilka avsnitt på min webbplats genererade de flesta sidvyerna?</li><li>Konsumtion av webbinnehåll (Vilket innehåll konsumeras mest och engagerar användarna)?</li><li>Förbrukning av mediematerial (vilket innehåll konsumeras mest och engagerar användarna)?</li><li>Nästa och föregående sidflöde (Vilka är/var nästa/föregående sökvägar som mina besökare tar/tog?)</li><li>Utfall (Var ser jag utfall från mina digitala resurser?)</li><li>Enhetsövergripande analys (Använda enhetsövergripande analys i Analysis Workspace)</li><li>Webbbevarande (Vilka är mina lojala användare och vad gör de?)</li><li>Medieljudförbrukning (Vad är trender och de viktigaste mätvärdena för ljudförbrukning?)</li><li>Media Recency, frequency, loyalty (Vilka är mina lojala läsare?)</li><li>Sidanalys > Läs in igen (vilka sidor genererar de mest laddade)?</li><li>Sidanalys > Tidsåtgång för sidan (hur mycket tid lägger mina användare på mina sidor?)</li><li>Poster och utträde > Startsidor (Vad är mina övre startsidor?)</li><li>Poster och utträden > Ursprungliga startsidor (Vilken sida angav min besökare ursprungligen från?)</li><li>Poster och avslutningar > Enkelsidiga besök (Vilka sidor genererade de mest enkelsidiga besöken?)</li><li>Poster och avslutningar > Avsluta sidor (Vad är mina översta avslutssidor?)</li><li>Sidanalys > Sidsammanfattning</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Produkter > Produkter (Vilka produkter påverkar min nyckelstatistik?)</li><li>Produkter > Produktprestanda (Vilka produkter fungerar bäst?)</li><li>Produkter > Kategorier (Vilka är mina mest framgångsrika produktkategorier?</li><li>Kundvagn > Korgar (hur många användare har lagt till en produkt i kundvagnen?</li><li>Kundvagn > Vyer av kundvagn (hur många gånger såg mina besökare sina kundvagnar?)</li><li>Kundvagn > Tillägg av kundvagn (Hur ofta lägger användare till en produkt i kundvagnen?)</li><li>Kundvagn > Ta bort kundvagn (Hur ofta tar användarna bort en produkt från kundvagnen?)</li><li>Inköp > Inkomster (hur fungerar mina intäkter?)</li><li>Inköp > Beställningar (hur fungerar mina order?)</li><li>Inköp > Enheter (hur många enheter säljer jag?)</li><li>[Magento: marknadsföring och handel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
| **[!UICONTROL Audience]** | <ul><li>Personmätvärden (hur många interagerar med mitt varumärke?)</li><li>Besökarprofil > Platsöversikt (vilka platser som används mest av användarna)</li><li>Besökarprofil > Geosegmentering > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Vilka platser besöker mina användare?)</li><li>Besökarprofil > Språk (vilket språk föredrar mina användare?)</li><li>Besökarprofil > Tidszoner (vilka tidszoner besöker mina användare?)</li><li>Besökarprofil > Domäner (Vilka internetleverantörer använder mina besökare för att komma åt min webbplats?)</li><li>Besökarprofil > Domäner på översta nivån (Vilka domäner kör trafik till min webbplats?)</li><li>Besöksprofil > Teknik > Teknik - översikt (Vilka tekniker använder människor för att komma åt min webbplats?)</li><li>Besökarprofil > Teknik > Webbläsare, webbläsartyp, webbläsarbredd, webbläsarhöjd (vilket företags webbläsare, webbläsarversion och dess bredd och höjd använder någon för att komma åt min webbplats?)</li><li>Besökarprofil > Teknik > Operativsystem, operativsystemtyper (vilket operativsystem och vilken version av det använder mina besökare?)</li><li>Besöksprofil > Teknik > Mobiloperatör (Vilka mobiloperatörer använder mina besökare för att besöka min webbplats?)</li><li>Bevarande av besökare > Returfrekvens (hur lång tid går det mellan min användares aktuella besök och tidigare besök?)</li><li>Bevarande av besökare > Returbesök (hur många av mina besök returnerar användare?)</li><li>Bevarande av besökare > Besök nummer (som besöks av sifferhaken styr de flesta av mina nyckeltal)</li><li>Besökarlojalitet > Försäljningscykel > Kundlojalitet (vilket lojalitetssegment tillhör mina användare?)</li><li>Bevarande av besökare > Försäljningscykel > Dagar före första köp (hur många dagar gick det mellan mitt användares första besök och deras första inköp?)</li><li>Bevarande av besökare > Försäljningscykel > Dagar sedan senaste köp (hur många dagar har gått mellan mitt användarbesök och det senaste köpet? )</li><li>Bevarande av besökare > Mobil > Enheter och enhetstyper (vilka enheter och enhetstyper använder mina besökare?)</li><li>Bevarande av besökare > Mobil > Tillverkare (Vilken mobilenhetstillverkare använder mina besökare?)</li><li>Bevarande av besökare > Mobil > Skärmstorlek, Skärmhöjd, Skärmbredd (Vilken mobilskärmstorlek/-höjd/bredd har mina besökare?)</li><li>Behåll besökare > Mobil > [Användning av mobilapp](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Bevarande av besökare > Mobil > [Resor för mobilappar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behålla besökare > Mobil > [Mätvärden för mobilappar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökare > Mobil > [Meddelanden för mobilappar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökare > Mobil > [Mobilappsprestanda](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökare > Mobil > [Behåll mobilappar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** | <ul><li>Marknadskanaler > Första beröringskanalen, Första beröringskanalen (Vilken första beröringskanal och vilken specifik första beröringskanal fungerar bäst?)</li><li>Marknadsföringskanaler > Första sista kanalen, Första sista kanalinformationen (Vilken sista beröringskanal och vilken specifik sista beröringskanal fungerar bäst?)</li><li>Campaigns > Campaigns (Vilka kampanjer driver min nyckelstatistik?)</li><li>Kampanjer > Kampanjresultat (Vilka kampanjer genererar störst intäkter?)</li><li>Kampanjer > Spårningskod (Vilka kampanjspårningskoder fungerar bäst?)</li><li>[Webbförvärv](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobilförvärv](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: betalsökning](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Söknyckelord - alla, betalda, naturliga (vilka söknyckelord och betalda/naturliga söknyckelord ger bäst nyckeltal?)</li><li>Sökmotorer - alla, betalda, naturliga (vilka sökmotorer och betalsökmotorer/naturliga sökmotorer ger mina nyckeltal bäst resultat?)</li><li>All rankning av söksidor (Vilken söksida besöker mina användare?)</li><li>Referensdomäner (Vilka domäner driver trafik till min plats?)</li><li>Ursprungliga refererande domäner (Vad var de första domänanvändarna var på innan de besökte min webbplats?)</li><li>Referenter (Vilka URL:er var mina användare på innan de klickade igenom till min webbplats?)</li><li>Refererartyper (vilken kategori tillhör mina refererande URL:er?)</li></ul> |

### Konvertering {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--productConversionReport"
>title="Produktkonverteringstrattmall"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--retail-products-template"
>title="Se vilka produkter som ger bäst resultat."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.<br/>Den här mallen använder måtten Produktvyer, kundvagnstillägg, Beställningar, Intäkter och Enheter. Det använder också produktdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="."
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartConversionReport"
>title="Visa hur många gånger personer har utfört utcheckningshändelser, t.ex. lagt till artiklar i kundvagnen, visat kundvagnen, tagit bort artiklar från kundvagnen och checkat ut."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka delar av processen som leder till konvertering och vilka som löper större risk att överge kundvagnen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att minska friktionen i vissa steg i utcheckningsprocessen.<br/>Den här mallen använder"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartsOvertimeReport"
>title="Visa antalet personer som har lagt till en produkt i kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå antalet personer som lägger till en produkt i kundvagnen, till skillnad från det totala antalet produkter som läggs till i en kundvagn.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att mäta effektiviteten hos dina produktsidor.<br/>Den här mallen använder Carts-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartViewsOvertimeReport"
>title="Se hur många gånger kunderna har sett sin kundvagn."
>abstract="**Det här kan hjälpa dig** att bättre förstå utcheckningsupplevelsen i ett försök att minska antalet kundvagnsavhoppningar eller analysera tiden mellan kundvagnstillägg och utcheckning av olika produkter.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, till exempel erbjuda kampanjer för produkter som ligger längst i varukorgar och som löper störst risk att överges.<br/>Den här mallen använder måttet för kundvagnsvyer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartAdditionsOvertimeReport"
>title="Se hur många gånger någon har lagt till något i kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kundintresset för en produkt är tillräckligt högt för att de ska kunna lägga till den i kundvagnen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra produktrekommendationerna för alla kunder. Detta kan göras genom att analysera vilka produkter som ofta läggs till i samma varukorgar och föreslå relaterade produkter som baseras på artiklar som redan finns i varukorgen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartRemovalsOvertimeReport"
>title="Se hur många gånger någon har tagit bort något från kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt, eller så kan det hjälpa dig att förstå var det kan finnas problem i utcheckningsprocessen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel ta bort eventuella hinder som kan finnas i utcheckningsprocessen, till exempel en komplicerad användarupplevelse.<br/>Den här mallen använder måttet för kundvagnsborttagning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--purchaseConversionReport"
>title="Inköpskonverteringstrattmall"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Visa fördefinierade insikter för återförsäljare om era handelsaktiviteter för att förbättra försäljningen. Detta riktar sig till användare av Magento, men kan utnyttjas av alla webbutiker."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur dina handelsaktiviteter bidrar till försäljningssiffror.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera budgeten efter aktiviteter som får störst avkastning."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Produktkonverteringstratt**] | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Produkter** | Se vilka produkter som genererar nyckeltal, t.ex. de främsta säljarna eller de mest visade. <p>**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.</p><p>I den här mallen används ordermåttet och produktdimensionen. |
| **Produktprestanda** | Se vilka produkter som ger bäst resultat.<p>**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.</p><p>I den här mallen används måtten för produktvyer, kundvagnstillägg, beställningar, intäkter och enheter. Det använder också produktdimensionen. |
| **Kategorier** |  |
| **Konverteringsfunktioner för kundvagn** | Visa hur många gånger personer har utfört utcheckningshändelser, t.ex. lagt till artiklar i kundvagnen, visat kundvagnen, tagit bort artiklar från kundvagnen och checkat ut. <p>**Detta kan hjälpa dig** att bättre förstå vilka delar av processen som leder till konvertering och vilka som löper större risk att överge kundvagnen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att minska friktionen i vissa steg i utcheckningsprocessen.</p><p>Den här mallen använder |
| **KARTOR** | Visa antalet personer som har lagt till en produkt i kundvagnen.<p>**Detta kan hjälpa dig** att bättre förstå antalet personer som lägger till en produkt i kundvagnen, till skillnad från det totala antalet produkter som läggs till i en kundvagn.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att mäta effektiviteten hos dina produktsidor.</p><p>I den här mallen används Carts-måttet. |
| **Kundvagnsvisningar** | Se hur många gånger kunderna har sett sin kundvagn. <p>**Det här kan hjälpa dig** att bättre förstå utcheckningsupplevelsen i ett försök att minska antalet kundvagnsavhoppningar eller analysera tiden mellan kundvagnstillägg och utcheckning av olika produkter.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, till exempel erbjuda kampanjer för produkter som ligger längst i varukorgar och som löper störst risk att överges.</p><p>I den här mallen används måttet för kundvagnsvyer. |
| **Tillägg i kundvagn** | Se hur många gånger någon har lagt till något i kundvagnen. <p>**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kundintresset för en produkt är tillräckligt högt för att de ska kunna lägga till den i kundvagnen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra produktrekommendationerna för alla kunder. Detta kan göras genom att analysera vilka produkter som ofta läggs till i samma varukorgar och föreslå relaterade produkter som baseras på artiklar som redan finns i varukorgen. |
| **Raderingar i kundvagn** | Se hur många gånger någon har tagit bort något från kundvagnen.<p>**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt, eller så kan det hjälpa dig att förstå var det kan finnas problem i utcheckningsprocessen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel ta bort eventuella hinder som kan finnas i utcheckningsprocessen, till exempel en komplicerad användarupplevelse.</p><p>I den här mallen används måttet för kundvagnsborttagning. |
| **Inköpskonverteringstru** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Intäkter** | <!--duplicated in Most popular section-->Visa det monetära beloppet för produkter som köpts i alla order.<p>**Detta kan hjälpa dig** att bättre förstå vilka dimensionsobjekt som har bidragit till intäkterna genom att kombinera intäktsmåtten med valfri dimension. Du kan till exempel se de främsta kampanjerna (med hjälp av spårningskoddimensionen) som har bidragit till intäkterna. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel justera kampanjer som inte uppfyller de intäktsmål du kan förvänta dig.</p><p>I den här mallen används intäktsmåttet. |
| **Beställningar** | <!--duplicated in Most popular section-->Visa det totala antalet inköpshändelser som har gjorts på din webbplats. <p>**Det här kan hjälpa dig** att bättre förstå vilka dimensionsobjekt som har bidragit till en ordning genom att kombinera Orders-måttet med valfri dimension. Du kan till exempel se de främsta kampanjerna (med hjälp av spårningskoddimensionen) som har bidragit till inköp.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel justera kampanjer som inte uppfyller de inköpsmål som du skulle kunna förvänta dig. </p><p>I den här mallen används måttet för beställningar. |
| [!UICONTROL **Enheter**] | Visa det totala antalet enheter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur enhetsförsäljningen ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som köper flest enheter och hur enhetsförsäljningen trendar över tid.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra enhetsförsäljningen före och efter att kampanjen har startats. Du kan också jämföra försäljningen per år under helger.</p><p>I den här mallen används måtten [Dag](/help/components/dimensions/day.md) och [Enheter](/help/components/metrics/units.md).</p> |
| [!UICONTROL **Magento: Marknadsföring och Commerce**] | Visa fördefinierade insikter för återförsäljare om era handelsaktiviteter för att förbättra försäljningen. Detta riktar sig till användare av Magento, men kan utnyttjas av alla webbutiker. <p>**Detta kan hjälpa dig** att bättre förstå hur dina handelsaktiviteter bidrar till försäljningssiffror.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera budgeten efter aktiviteter som får störst avkastning.</p> |

### Målgrupp {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Se det land som besökarna kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå vad de populäraste länderna besökarna kommer från när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i dessa länder, eller se till att webbplatsupplevelsen är optimal i länder som har olika primära språk.<br/>Den här mallen använder dimensionen Länder."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Visa det tillstånd (i USA) som folk från webbplatsen har sitt ursprung i. Detta liknar mallen Geo Regions, förutom att den är specifik för USA."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste amerikanska delstatsbesökarna som kommer från de som besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa lägen.<br/>Den här mallen använder dimensionen USA."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Visa det geografiska område som personer som besöker webbplatsen kommer från. En region är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. "
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de här regionerna, eller se till att webbplatsupplevelsen är optimal i regioner som har olika primära språk. <br/>Den här mallen använder dimensionerna ID(variabler/geocountry) och Region. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Se den stad som folk från webbplatsen kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste städer som besökarna kommer från när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa städer. <br/>Den här mallen använder dimensionen Städer"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Se vilka områden i USA som besökarna kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de mest framgångsrika regionerna. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Se vilka språk besökarna föredrar att se innehåll på."
>abstract="**Det här kan hjälpa dig** att bättre förstå besökarnas vanligaste språk.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som fokuslokaliseringsaktiviteter eller marknadsföringsaktiviteter för de vanligaste språken.<br/>Den här mallen använder språkdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Visa de översta tidszonerna för besökare som kommer åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå i vilka tidszoner besökarna bor.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera webbplatsunderhåll ibland, vilket påverkar så få personer som möjligt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Visa de vanligaste domänerna för besökare som kommer åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka organisationer dina besökare kommer ifrån.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel rikta ditt innehåll mot dina största kunder."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Visa de vanligaste domänerna för besökare som kommer åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka organisationer dina besökare kommer ifrån.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel rikta ditt innehåll mot dina största kunder."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Teknik - översikt"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Visa namn och version för de webbläsare som användarna använder mest för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder.<br/>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen.<br/>Den här mallen använder webbläsardimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Visa namnen på de organisationer som har skapat de vanligaste webbläsarna som användarna använder för att komma åt webbplatsen. Detta skiljer sig från webbläsarmallen på så sätt att olika versioner av samma webbläsare inte listas som separata dimensionsobjekt."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder <br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen. <br/>Den här mallen använder dimensionen för webbläsartypen. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Visa de vanligaste webbläsarbredderna som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarbredderna. Om du gör det kan du maximera kvalitetskontrollen.<br/>Den här mallen använder webbläsardimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Visa de topphöjder i webbläsaren som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarhöjderna. Om du gör det kan du maximera kvalitetskontrollen.<br/>Den här mallen använder webbläsardimensionen. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Visa namnet på de operativsystem och den version som andra använder för att komma åt din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste operativsystemen och versionerna som besökarna använder.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de viktigaste operativsystemen och versionerna. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Visa namnet på de operativsystem som användarna använder för att komma åt din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste operativsystemen som besökarna använder.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de vanligaste operativsystemen. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileCarrierRankedReport"
>title="Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder dimensionen Mobiloperatör."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder dimensionen Mobiloperatör."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder dimensionen Mobiloperatör."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Visa hur många gånger en besökare har besökt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur engagerade besökare är när de återvänder till din webbplats. Detta gäller besökarens livstid, oavsett projektets datumintervall.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att justera marknadsföringsaktiviteter för besökare som ofta är besökare.<br/>Den här mallen använder dimensionen för besöksnumret."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Visa antalet besökare på din webbplats som har gjort 0 tidigare inköp, 1 tidigare inköp, 2 tidigare inköp eller 3+ tidigare inköp."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur din webbplats påverkar köpbeteendet. .<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att fokusera på besökare som kommer tillbaka för att göra ett köp, så att du kan uppmuntra till liknande beteende för nya besökare.<br/>Den här mallen använder kundlojalitetsdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Se hur många dagar det är mellan första gången en besökare kommer till er webbplats och när de gör ett köp. Om en besökare till exempel gör ett köp en dag efter första besök, tillhör alla efterföljande besök eller evenemang dimensionsposten 1 dag."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur lång tid det tar för besökarna att göra ett köp.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att uppdatera din webbplats för att uppmuntra till snabbare förvärv.<br/>Den här mallen använder dimensionen Dagar före första inköp."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Se hur lång tid det tar mellan besökarens aktuella träff och det senaste köpet vid den tidpunkten."
>abstract="**Detta kan hjälpa dig** att förstå besökarnas beteende bättre efter att ha köpt något på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att uppdatera din webbplats för att uppmuntra uppföljningsköp.<br/>Den här mallen använder Dagar sedan den senaste inköpsdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileDeviceNameRankedReport"
>title="Visa märke och modell för mobila enheter som används för att komma åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobila enheter som är populärast bland dina användare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera återgivningen av din webbplats för de vanligaste mobila enheterna.<br/>Den här mallen använder dimensionen Mobilenhetsnamn."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileDeviceTypeRankedReport"
>title="Visa de mobila enhetstyper som användare använder för att få tillgång till din webbplats, t.ex. telefoner och surfplattor."
>abstract="**Detta kan hjälpa dig** att bättre förstå de olika typer av mobila enheter som används för att komma åt din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera webbplatsen för de typer av mobila enheter som används mest.<br/>Den här mallen använder dimensionen Mobilenhetstyp."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileManufacturerRankedReport"
>title="Se vilka tillverkare som producerar de mobila enheter som användarna använder för att få tillgång till er webbplats, som Apple och Samsung."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka tillverkare som är populärast bland dina användare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att skräddarsy innehållsleveransen baserat på kapaciteten hos olika tillverkare för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder Mobile Manufacturer-dimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Visa de populäraste skärmstorlekarna för mobila enheter som användare använder för att komma åt din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de vanligaste mobilskärmstorlekarna. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Visa höjder på mobilskärmen som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatskvaliteten genom att testa nya versioner av din webbplats med de vanligaste höjderna för mobilskärmar. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Visa bredder för den övre mobilskärmen som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatskvaliteten genom att testa nya versioner av webbplatsen med de vanligaste mobilskärmsbredderna. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-lifecycle-metrics-app-usage-template"
>title="Visa antalet användare, starter och första starter för appen samt den genomsnittliga sessionslängden."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur mycket appen används. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra appprestanda så att den kan anpassas till användningsmängden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-journeys"
>title="Visa de framträdande användningsmönstren för din mobilapp."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur andra använder din app. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra hur användare kan komma från en skärm till en annan och anpassa sig till de vanligaste arbetsflödena."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-key-metrics"
>title="Visa några av de vanligaste mätvärdena för mobilappar."
>abstract="**Detta kan hjälpa dig** att bättre förstå grundläggande prestanda i din mobilapp.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att utvärdera den övergripande hälsan och prestandan för din app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-messaging"
>title="Visa prestandadata för meddelanden i appen och push-meddelanden för appen."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur användare använder meddelandefunktioner i appen samt hur effektivt push-meddelanden genererar trafik till din app.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra push-meddelandefunktionen i appen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-performance-template"
>title="Se hur appen fungerar och var användarna har problem."
>abstract="**Detta kan hjälpa dig** att bättre förstå om användare som använder din app stöter på långsamhet eller försämrade prestanda. <br/>**Baserat på vad du lär dig kan du** göra flera saker, som att åtgärda befintliga problem eller förbättra appprestanda innan problem uppstår."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-retention"
>title="Visa vilka användare som är de mest lojala användarna av appen och vad de gör i appen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur dina mest lojala användare använder din app.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra marknadsföringen för de funktioner som de mest lojala användarna använder."

<!-- markdownlint-enable MD034 -->


Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Personmått**] | Se hur många som interagerar med ert varumärke. <p>**Det här kan hjälpa dig** att bättre förstå användningsmönster på din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att mäta hur effektiv marknadsföringen nyligen har varit när det gäller att skapa nya besökare på din webbplats.</p> |
| **Besökarprofil** > **Platsöversikt** | Visa en översikt över besökarnas plats i en kartvisualisering.<p>**Det här kan hjälpa dig** att bättre förstå var besökarna finns som besöker din webbplats. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringsresurser på de platser där du ser störst intresse och möjlighet.</p><!-- This template uses the --> |
| **Besöksprofil** > **Geografiska länder** | Se det land som besökarna kommer ifrån.<p>**Det här kan hjälpa dig** att bättre förstå vad de populäraste länderna besökarna kommer från när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i dessa länder, eller se till att webbplatsupplevelsen är optimal i länder som har olika primära språk.</p><p>Den här mallen använder dimensionen Länder. </p> |
| **Besökarprofil** > **Geo US-lägen** | Visa det tillstånd (i USA) som folk från webbplatsen har sitt ursprung i. Detta liknar mallen Geo Regions, förutom att den är specifik för USA.<p>**Det här kan hjälpa dig** att bättre förstå de populäraste amerikanska delstatsbesökarna som kommer från de som besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa lägen.</p><p>I den här mallen används dimensionen USA. </p> |
| **Besökarprofil** > **Geografiska områden** | Visa det geografiska område som personer som besöker webbplatsen kommer från. En region är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. <p>**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de här regionerna, eller se till att webbplatsupplevelsen är optimal i regioner som har olika primära språk. </p><p>I den här mallen används dimensionerna ID (variabler/geoland) och Region. </p> |
| **Besökarprofil** > **Geo-städer** | Se den stad som folk från webbplatsen kommer ifrån. <p>**Det här kan hjälpa dig** att bättre förstå de populäraste städer som besökarna kommer från när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa städer. </p><p>Den här mallen använder dimensionen Städer. </p> |
| **Besökarprofil** > **Geo US DMA** | Se vilka områden i USA som besökarna kommer ifrån.<p>**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de mest framgångsrika regionerna. </p><!-- This template uses the --> |
| **Besökarprofil** > **Språk** | Se vilka språk besökarna föredrar att se innehåll på. <p>**Det här kan hjälpa dig** att bättre förstå besökarnas vanligaste språk.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som fokuslokaliseringsaktiviteter eller marknadsföringsaktiviteter för de vanligaste språken.</p><p>Den här mallen använder dimensionen Språk.</p> |
| **Besökarprofil** > **Tidszoner** | Visa de översta tidszonerna för besökare som kommer åt din webbplats. <p>**Det här kan hjälpa dig** att bättre förstå i vilka tidszoner besökarna bor.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera webbplatsunderhåll ibland, vilket påverkar så få personer som möjligt.</p> |
| **Besökarprofil** > **Domäner** | Visa de vanligaste domänerna för besökare som kommer åt din webbplats. <p>**Det här kan hjälpa dig** att bättre förstå vilka organisationer dina besökare kommer ifrån.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel rikta ditt innehåll mot dina största kunder.</p> |
| **Besökarprofil** > **Domäner på översta nivån** | Visa de översta domänerna för besökare som kommer åt din webbplats. <p>**Det här kan hjälpa dig** att bättre förstå vilka organisationer dina besökare kommer ifrån.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel rikta ditt innehåll mot dina största kunder.</p> |
| **Besökarprofil** > **Teknik** > **Tekniköversikt** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder </p> |
| **Besökarprofil** > **Teknik** > **Webbläsare** | Visa namn och version för de webbläsare som användarna använder mest för att komma åt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen.</p><p>Den här mallen använder dimensionen Webbläsare. </p> |
| **Besökarprofil** > **Teknik** > **Webbläsartyper** | Visa namnen på de organisationer som har skapat de vanligaste webbläsarna som användarna använder för att komma åt webbplatsen. Detta skiljer sig från webbläsarmallen på så sätt att olika versioner av samma webbläsare inte listas som separata dimensionsobjekt.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder</p><p>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen. </p><p>Den här mallen använder dimensionen för webbläsartyp. </p> |
| **Besökarprofil** > **Teknik** > **Webbläsarbredd** | Visa de vanligaste webbläsarbredderna som andra använder för att komma åt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarbredderna. Om du gör det kan du maximera kvalitetskontrollen.</p><p>Den här mallen använder dimensionen Webbläsare. </p> |
| **Besökarprofil** > **Teknik** > **Webbläsarhöjd** | Visa de topphöjder i webbläsaren som andra använder för att komma åt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarhöjderna. Om du gör det kan du maximera kvalitetskontrollen.</p><p>Den här mallen använder dimensionen Webbläsare. </p> |
| **Besökarprofil** > **Teknik** > **Operativsystem** | Visa namnet på de operativsystem och den version som andra använder för att komma åt din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste operativsystemen och versionerna som besökarna använder.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de viktigaste operativsystemen och versionerna. Om du gör det kan du maximera kvalitetskontrollen.</p> |
| **Besökarprofil** > **Teknik** > **Operativsystemstyper** | Visa namnet på de operativsystem som användarna använder för att komma åt din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste operativsystemen som besökarna använder.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de vanligaste operativsystemen. Om du gör det kan du maximera kvalitetskontrollen.</p> |
| **Besökarprofil** > **Teknik** > [!UICONTROL **Mobiloperatör**] | Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används mobiloperatörsdimensionen.</p> |
| **Bevarandefrekvens för besökare** > **Returfrekvens** | Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används mobiloperatörsdimensionen.</p> |
| **Behåll besökare** > **Återvänd besök** | Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används mobiloperatörsdimensionen.</p> |
| **Behåll besökare** > **Besök nummer** | Visa hur många gånger en besökare har besökt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå hur engagerade besökare är när de återvänder till din webbplats. Detta gäller besökarens livstid, oavsett projektets datumintervall.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att justera marknadsföringsaktiviteter för besökare som ofta är besökare.</p><p>Den här mallen använder dimensionen för besöksnumret.</p> |
| **Behåll besökare** > **Försäljningscykel** > **Kundlojalitet** | Visa antalet besökare på din webbplats som har gjort 0 tidigare inköp, 1 tidigare inköp, 2 tidigare inköp eller 3+ tidigare inköp. <p>**Detta kan hjälpa dig** att bättre förstå hur din webbplats påverkar köpbeteendet. .</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att fokusera på besökare som kommer tillbaka för att göra ett köp, så att du kan uppmuntra till liknande beteende för nya besökare.</p><p>Den här mallen använder kundlojalitetsdimensionen.</p> |
| **Behåll besökare** > **Försäljningscykel** > **Dagar före första köp** | Se hur många dagar det är mellan första gången en besökare kommer till er webbplats och när de gör ett köp. Om en besökare till exempel gör ett köp en dag efter första besök, tillhör alla efterföljande besök eller evenemang dimensionsposten&quot;1 dag&quot;.<p>**Det här kan hjälpa dig** att bättre förstå hur lång tid det tar för besökarna att göra ett köp.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att uppdatera din webbplats för att uppmuntra till snabbare förvärv.</p><p>Den här mallen använder dimensionen Dagar före första inköp.</p> |
| **Behåll besökare** > **Försäljningscykel** > **Dagar sedan senaste köp** | Se hur lång tid det tar mellan besökarens aktuella träff och det senaste köpet vid den tidpunkten.<p>**Detta kan hjälpa dig** att förstå besökarnas beteende bättre efter att ha köpt något på webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att uppdatera din webbplats för att uppmuntra uppföljningsköp.</p><p>Den här mallen använder dimensionen Dagar sedan senaste köp.</p> |
| **Mobil** > **Mobila enheter** | Visa märke och modell för mobila enheter som används för att komma åt din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobila enheter som är populärast bland dina användare.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera återgivningen av din webbplats för de vanligaste mobila enheterna.</p><p>Den här mallen använder dimensionen Mobilenhetsnamn.</p> |
| **Mobil** > **Mobilenhetstyp** | Visa de mobila enhetstyper som användare använder för att få tillgång till din webbplats, t.ex. telefoner och surfplattor.<p>**Detta kan hjälpa dig** att bättre förstå de olika typer av mobila enheter som används för att komma åt din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera webbplatsen för de typer av mobila enheter som används mest.</p><p>Den här mallen använder dimensionen för mobilenhetstyp.</p> |
| **Mobil** > **Tillverkare** | Se vilka tillverkare som producerar de mobila enheter som användarna använder för att få tillgång till er webbplats, som Apple och Samsung.<p>**Det här kan hjälpa dig** att bättre förstå vilka tillverkare som är populärast bland dina användare.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att skräddarsy innehållsleveransen baserat på kapaciteten hos olika tillverkare för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används Mobile Manufacturer-dimensionen.</p> |
| **Mobil** > **Skärmstorlek** | Visa de populäraste skärmstorlekarna för mobila enheter som användare använder för att komma åt din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de vanligaste mobilskärmstorlekarna. Om du gör det kan du maximera kvalitetskontrollen.</p> |
| **Mobil** > **Skärmhöjd** | Visa höjder på mobilskärmen som andra använder för att komma åt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatskvaliteten genom att testa nya versioner av din webbplats med de vanligaste höjderna för mobilskärmar. Om du gör det kan du maximera kvalitetskontrollen.</p> |
| **Mobil** > **Skärmbredd** | Visa bredder för den övre mobilskärmen som andra använder för att komma åt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatskvaliteten genom att testa nya versioner av webbplatsen med de vanligaste mobilskärmsbredderna. Om du gör det kan du maximera kvalitetskontrollen.</p> |
| **Mobil** > **Användning av mobilappar** | Visa antalet användare, starter och första starter för appen samt den genomsnittliga sessionslängden.<p>**Det här kan hjälpa dig** att bättre förstå hur mycket appen används. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra appprestanda så att den kan anpassas till användningsmängden.</p><!-- This template uses the --> |
| **Mobiler** > **Mobilappsresor** | Visa de framträdande användningsmönstren för din mobilapp. <p>**Detta kan hjälpa dig** att bättre förstå hur andra använder din app. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra hur användare kan komma från en skärm till en annan och anpassa sig till de vanligaste arbetsflödena. </p><!-- This template uses the --> |
| **Mobiler** > **Mobilappsmått** | Visa några av de vanligaste mätvärdena för mobilappar. <p>**Detta kan hjälpa dig** att bättre förstå grundläggande prestanda i din mobilapp.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att utvärdera den övergripande hälsan och prestandan för din app.</p><!-- This template uses the --> |
| **Mobil** > **Meddelanden för mobilappar** | Visa prestandadata för meddelanden i appen och push-meddelanden för appen.<p>**Det här kan hjälpa dig** att bättre förstå hur användare använder meddelandefunktioner i appen samt hur effektivt push-meddelanden genererar trafik till din app.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra push-meddelandefunktionen i appen.</p><!-- This template uses the --> |
| **Mobiler** > **Mobilappsprestanda** | Se hur appen fungerar och var användarna har problem. <p>**Detta kan hjälpa dig** att bättre förstå om användare som använder din app stöter på långsamhet eller försämrade prestanda. </p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att åtgärda befintliga problem eller förbättra appprestanda innan problem uppstår.</p><!-- This template uses the --> |
| **Mobil** > **Behåll mobilappar** | Visa vilka användare som är de mest lojala användarna av appen och vad de gör i appen. <p>**Detta kan hjälpa dig** att bättre förstå hur dina mest lojala användare använder din app.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra marknadsföringen för de funktioner som de mest lojala användarna använder.</p><!-- This template uses the --> |

### Förvärv {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="När du använder anpassad attribuering visar den här mallen hur besökare kommer till din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka av era marknadsföringskanaler som är mest effektiva.<br/>**Baserat på vad du lär dig kan du** göra många saker, som att investera mer i effektiva marknadsföringskanaler och ta bort från mindre effektiva marknadsföringskanaler.<br/>Den här mallen använder dimensionerna ID(variabler/marketingchannel) och Intäktsmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Visa den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver den inledande trafiken till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.<br/>Den här mallen använder dimensionen Första beröringskanalen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Visa information om den första marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.<br/>Den här mallen använder dimensionen Första beröringskanaldetalj."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Kampanjkonverteringstratt"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Visa detaljerad information om hur era marknadsföringskampanjer fungerar."
>abstract="**Det här kan hjälpa dig** att bättre förstå olika indikatorer för att lyckas med kampanjer, t.ex. intäkter, produktvisningar, beställningar och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter. <br/>I den här mallen används måtten Intäktssiffror, Produktvyer, Cart Additions, Orders och Units. Den använder även spårningskoddimensionen och referensdomändimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Se hur er webbplats får besökare på mobila enheter."
>abstract="**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.<br/>Den här mallen använder Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-acquisition-template"
>title="Se hur er webbplats får besökare."
>abstract="**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.<br/>Den här mallen använder Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Visa alla dina Google- och Bing betalsökdata sida vid sida."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur mycket trafik som skickas till din webbplats och om kunderna konverterar.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att uppskatta kostnadseffektiviteten för en annonskampanj."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik. <br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.<br/>Den här mallen använder dimensionen Sök nyckelord."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken. <br/>Den här mallen använder dimensionen Söknyckelord - Betald. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.<br/>Den här mallen använder söknyckelordet - naturlig dimension. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Visa sökmotorerna som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.<br/>Den här mallen använder dimensionen Sökmotor. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Visa sökmotorerna som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen. <br/>Den här mallen använder sökmotorn - betaldimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.<br/>Den här mallen använder sökmotorn - naturlig dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Visa vilken sida av sökresultat en besökare klickade igenom till din webbplats. Om din webbplats till exempel visas på den andra sidan av sökresultatet i en sökmotor är dimensionsobjektet för den här variabeln Söksida 2."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur högt dina sidor rankas i sökresultaten.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, förbättra SEO-strategin för att se till att ditt innehåll visas på första sidan i sökresultaten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Visa vilka domäner som användare klickar igenom för att nå din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som genererar mest trafik till din. (En länk måste finnas på den externa platsen och en besökare måste klicka på den för att dimensionsposten ska kunna visas.)<br/>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande toppdomänerna. <br/>Den här mallen använder dimensionen Refererande domän."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Visa den första refererande domänen som personer klickat igenom för att nå din webbplats. (När det har angetts innehåller det samma värde för hela besökar-ID:t.)"
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som ursprungligen kör trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande huvuddomänerna. <br/>Den här mallen använder dimensionen Ursprunglig referensdomän."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Visa vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. (En länk måste finnas på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.)"
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka specifika URL:er som genererar mest trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de översta URL:erna. <br/>Den här mallen använder dimensionen Refererande domän.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Visa vilka generiska kanaler besökarna klickade igenom för att komma till er webbplats. Adobe bibehåller reglerna för varje kanal. Möjliga kanaler är sökmotorer, sociala nätverk, andra webbplatser, hårddisk eller e-post."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilken typ av referenter som leder flest trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från en viss kanal.<br/>Den här mallen använder dimensionen Refererartyp."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Översiktsrapport för marknadsföringskanaler**] | När du använder anpassad attribuering visar den här mallen hur besökare kommer till din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå vilka av era marknadsföringskanaler som är mest effektiva.</p><p>**Baserat på vad du lär dig kan du** göra många saker, som att investera mer i effektiva marknadsföringskanaler och ta bort från mindre effektiva marknadsföringskanaler.</p><p>Den här mallen använder dimensionerna ID (variabler/marketingchannel) och Intäktsmått.</p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Första beröringsmarknadsföringskanalen**] | Visa den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). <p>**Detta kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver den inledande trafiken till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>I den här mallen används dimensionen Första beröringskanalen.</p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Information om den första beröringskanalen**] | Visa information om den första marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>Den här mallen använder dimensionen Första beröringskanalen Detalj.</p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Senaste Touch Marketing Channel**] | Visa den senaste marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard).<p>**Det här kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver trafik till din webbplats som resulterar i konverteringar.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>I den här mallen används dimensionen Sista beröringskanalen.  </p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Information om senaste beröringskanal**] | Visa information om den senaste marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard)<p>**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva. </p><p>I den här mallen används dimensionen Senaste beröringskanaldetalj. </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjer (spårningskod)**] | Visa namnen på spårningskoderna på din webbplats. Du kan placera länkar med olika parametervärden för frågesträngar på olika platser på Internet.<p>**Detta kan hjälpa dig** att bättre förstå vilka länkar som var mest framgångsrika när det gäller att köra trafik till din webbplats. Att lägga till spårningskodfrågesträngar är vanligt i e-postmeddelanden, annonser, inlägg i sociala medier och andra marknadsföringsaktiviteter som används i organisationen</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter.</p><p>Den här mallen använder spårningskoddimensionen. </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjkonverteringsfunktion**] | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder  </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjresultat**] | Visa detaljerad information om hur era marknadsföringskampanjer fungerar.<p>**Det här kan hjälpa dig** att bättre förstå olika indikatorer för att lyckas med kampanjer, t.ex. intäkter, produktvisningar, beställningar och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter. </p><p>I den här mallen används måtten Intäkter, Produktvyer, Cart Additions, Orders och Units. Den använder även spårningskoddimensionen och referensdomändimensionen. </p> |
| **Mobilförvärv** | Se hur sajten får besökare på mobila enheter.<p>**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.</p><p>I den här mallen används Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension.  </p> |
| **Webbförvärv** | Se hur er webbplats får besökare.<p>**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.</p><p>I den här mallen används Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension.  </p> |
| **Advertising Analytics: Betald sökning** | Visa alla dina Google- och Bing betalsökdata sida vid sida. <p>**Detta kan hjälpa dig** att bättre förstå hur mycket trafik som skickas till din webbplats och om kunderna konverterar.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att uppskatta kostnadseffektiviteten för en annonskampanj.</p> |
| **Sök nyckelord-alla** | Visa söknyckelorden som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt. <p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik. </p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.</p><p>Den här mallen använder dimensionen Sök nyckelord. </p> |
| **Sök efter nyckelord - betald** | Visa söknyckelorden som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken. </p><p>Den här mallen använder dimensionen Söknyckelord - Betald. </p> |
| **Sök nyckelord - naturligt** | Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.</p><p>Den här mallen använder dimensionen Sök nyckelord - naturligt. </p> |
| **Sökmotorer - alla** | Visa sökmotorerna som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt. <p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.</p><p>Den här mallen använder dimensionen Sökmotor. </p> |
| **Sökmotorer - betald** | Visa sökmotorerna som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen. </p><p>I den här mallen används dimensionen Sökmotor - betald. </p> |
| **Sökmotorer - Naturliga** | Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.</p><p>Den här mallen använder sökmotorn - naturlig dimension. </p> |
| **Alla söksidrankning** | Visa vilken sida av sökresultat en besökare klickade igenom till din webbplats. Om din webbplats till exempel visas på den andra sidan av sökresultatet i en sökmotor är dimensionsobjektet för den här variabeln&quot;Söksida 2&quot;.<p>**Det här kan hjälpa dig** att bättre förstå hur högt dina sidor rankas i sökresultaten.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, förbättra SEO-strategin för att se till att ditt innehåll visas på första sidan i sökresultaten. </p> |
| **Refererande domäner** | Visa vilka domäner som användare klickar igenom för att nå din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som genererar mest trafik till din. (En länk måste finnas på den externa platsen och en besökare måste klicka på den för att dimensionsposten ska kunna visas.)</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande toppdomänerna. </p><p>Den här mallen använder dimensionen Refererande domän. </p> |
| **Ursprungliga referensdomäner** | Visa den första refererande domänen som personer klickat igenom för att nå din webbplats. (När det har angetts innehåller det samma värde för hela besökar-ID:t.)<p>**Det här kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som ursprungligen kör trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande huvuddomänerna. </p><p>Den här mallen använder dimensionen Ursprunglig referensdomän. </p> |
| **Referenter** | Visa vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. (En länk måste finnas på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.)  <p>**Det här kan hjälpa dig** att bättre förstå vilka specifika URL:er som genererar mest trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de översta URL:erna. </p><p>Den här mallen använder dimensionen Refererande domän </p><p>I den här mallen används referensdimensionen. </p> |
| **Refererartyper** | Visa vilka generiska kanaler besökarna klickade igenom för att komma till er webbplats. Adobe bibehåller reglerna för varje kanal. Möjliga kanaler är sökmotorer, sociala nätverk, andra webbplatser, hårddisk eller e-post.<p>**Det här kan hjälpa dig** att bättre förstå vilken typ av referenter som leder flest trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från en viss kanal.</p><p>Den här mallen använder dimensionen Refererartyp.</p> |
