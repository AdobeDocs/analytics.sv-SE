---
title: Termer som används i Adobe Analytics
description: Ordlista för Adobe Analytics, definiera vanliga termer som används.
exl-id: 07507ba1-a512-48d9-8022-6084de4ae262
feature: Implementation Basics
source-git-commit: f68cf0de5e7689d8245572b060a3d81c3bf85072
workflow-type: tm+mt
source-wordcount: '2528'
ht-degree: 0%

---

# Termer som används i Adobe Analytics

Använd den här ordlistan för att förstå sammanhanget för många termer som Adobe Analytics använder.

* **Aktivitetskarta:** En webbläsarplugin som visar vilka områden på webbplatsen som du klickade mest på. Se [Activity Map](/help/analyze/activity-map/activity-map.md) i användarhandboken för Analysera.
* **Admin Console:** Kan avse:
   * Äldre administrationsverktyg, där rapportsvitens inställningar i Adobe Analytics hanteras. I tidigare versioner av Adobe Analytics hanterades även användarbehörigheter här. Se [Administratörsverktyg](/help/admin/admin/c-admin-tools.md) i användarhandboken för Admin.
   * Admin Console i Adobe, där produktåtkomst tillhandahålls och användarbehörigheter hanteras. Se [Admin Console](/help/admin/admin-console/home.md) i användarhandboken för Admin.
* **Allokering:** Om en konverteringsvariabel påträffar mer än ett värde under ett besök avgör variabelns allokeringsinställning vilket värde som behålls. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) i användarhandboken för Admin.
* **Analysis Workspace:** Webbläsarlösning för att skapa stabila, anpassade analysprojekt och demokratisera insikter. Ger större rapportflexibilitet än Reports and Analytics.
* **Anomaly:** Identifierades med statistisk modellering för att automatiskt hitta oväntade trender i data. Modellen analyserar mätvärden och fastställer en nedre gräns, övre gräns och förväntat värdeintervall. Se [Analysidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) i användarhandboken för Analysera.
* **AppMeasurement:** Kodbiblioteket som används för att samla in data och skicka dem till Adobe. Se [Hemsida](/help/implement/home.md) i Implementera användarhandboken.
* **ASI-kortplats:** Finns inte längre. I tidigare versioner av Adobe Analytics tillhandahöll ASI-kortplatser en temporär rapportsvitsbehållare för att visa segmenterade data. I den aktuella versionen av Adobe Analytics kan segment tillämpas direkt på alla rapporter.
* **Uppdelning:** Gör att du kan visa en dimension inuti en annan dimension. Se [Dela upp dimensioner](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) i användarhandboken för Analysera.
* **Studsa:** Ett besök som består av en enda träff. Se [studsar](/help/components/metrics/bounces.md) i användarhandboken för komponenter. Se även Enkel åtkomst.
* **Beräknat mått:** Tillåter en kombination av befintliga mätvärden, statistiska funktioner och formler för rapportering. Se [Beräknade mått](/help/components/c-calcmetrics/cm-overview.md) i användarhandboken för komponenter.
* **Campaign:** Kan avse:
   * Kampanjvariabeln, som fyller i spårningskoddimensionen. Se [kampanj](../implement/vars/page-vars/campaign.md) i Implementeringshandboken.
   * En standardklassificering av spårningskoddimensionen, som skapas automatiskt för alla rapportsviter.
   * Adobe Campaign, en del av Adobe Experience Cloud. Mer information om [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **Kanal:** Kan avse:
   * Variabeln Kanal, som fyller i dimensionen Platsavsnitt. Se [Sidvariabler](/help/implement/vars/page-vars/page-variables.md) i Implementeringshandboken.
   * Marknadsföringskanaler, en komponent som hjälper er att förstå hur användarna kommer till er webbplats. Se [Marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md) i användarhandboken för komponenter.
* **Klassificering:** En funktion i Adobe Analytics som tillåter gruppering av dimensionsobjekt. Se [Klassificeringar](/help/components/classifications/c-classifications.md) i användarhandboken för komponenter.
* **Klickkarta:** Används inte längre. Ett äldre plugin-program för webbläsare som visar vilka områden på webbplatsen som du klickade mest på. Det här verktyget har tagits bort till förmån för Activity Map.
* **Klickströmsdatafeed:** Se Dataflöde.
* **Kohort:** En grupp personer som delar gemensamma egenskaper under en viss tidsperiod. Se [Vad är kohortanalys?](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) i användarhandboken för Analysera.
* **Samlingsserver:** Se Datainsamlingsserver.
* **Komponent:** Komponenterna i Analysis Workspace består av mått, mått, segment och datumintervall som du kan dra och släppa i ett projekt. Se [Komponenter - översikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) i användarhandboken för Analysera.
* **Kontextdatavariabler:** Tillfälliga variabler som endast används i bearbetningsregler. Variabelvärden för kontextdata förloras permanent om en bearbetningsregel inte kopierar dem till en konverterings- eller trafikvariabel. Se [Sammanhangsdatavariabler](../implement/vars/page-vars/contextdata.md) i Implementeringshandboken.
* **Konverteringsvariabel:** Kallas också eVars. Sparar ett anpassat värde och bevarar variabelvärdet tills det upphör att gälla. Se [eVar](/help/components/dimensions/evar.md) -dimensionen i användarhandboken för komponenter.
* **Korrelation:** Används inte längre som term; ersätts med dimensionsuppdelning. I tidigare versioner av Adobe Analytics gav korrelations möjlighet att bryta ned trafikvariabler. Se [Dela upp dimensioner](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) i användarhandboken för Analysera.
* **Egen länk:** En typ av träff som innehåller data som inte är sidvy. Se [funktionen s.tl()](../implement/vars/functions/tl-method.md) i Implementeringshandboken. Se även Träff.
* **Kundattribut:** En Experience Cloud-funktion som tillåter överföring av attributdata. Se [Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) i användarhandboken för bastjänsterna.
* **Kundsupportrepresentant:** En utsedd användare som har rätt att interagera direkt med Adobe kundtjänst. Se [Kundsupportrepresentanter](https://helpx.adobe.com/experience-cloud/supported-users.html) i Experience Cloud Knowledgebase.
* **Datainsamlingsserver:** Adobe-ägda servrar som tar emot och bearbetar data. Bildbegäranden skickas till Adobe datainsamlingsservrar för användning vid rapportering.
* **Dataanslutningar:** En pensionerad utvecklingslösning som gör att en tredje part kan automatisera överföringen av data till Adobe Analytics. Kunder från den tredje parten kan använda en dataanslutning för att förbättra sina data i Adobe Analytics. Ersatt med Adobe Exchange Marketplace.
* **Dataflöde:** En export av rådata som visar alla träffar som rader och variabler som separata kolumner. De vanligaste är att exportera Adobe Analytics-data till en tredjepartsdatabas. Se [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md) i Exportera användarhandbok.
* **Datakällor:** Användare kan överföra data från en fil till Adobe Analytics. Filen hämtas vanligtvis från en FTP-plats. Se [Datakällor](/help/import/data-sources/overview.md) i importhandboken.
* **Data Warehouse:** En funktion i Adobe Analytics som gör att du kan begära större rapporter. Se [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) i Exportera användarhandbok.
* **Data Workbench:** Tidigare Insight. Utformat för att samla in, bearbeta, analysera och visualisera data från kundinteraktioner både online och offline över flera kanaler.
* **Dimension:** En komponenttyp som innehåller variabelvärden, som text. Exempel är sidnamn, spårningskod eller referensdomän. Ett mätvärde är vanligtvis dess motsvarighet.
* **Händelseserialisering:** Processen med att vidta åtgärder för att förhindra insamling av dubbletthändelser. Se [Händelseserialisering](../implement/vars/page-vars/events/event-serialization.md) i Implementeringshandboken.
* **eVar:** Se Konverteringsvariabel.
* **Händelse:** Se Success event.
* **ExcelClient:** Används inte längre som term. Namnet på föregångaren till Report Builder.
* **Förfallodatum:** I kontexten för en konverteringsvariabel, hur länge värdet finns kvar på backend-objektet. Denna beständighet gör att händelser kan associeras med variabelvärden före händelsens träff. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) i användarhandboken för Admin.
* **Flöde:** En typ av visualisering i Analysis Workspace som visar vilka sökvägar användare har på din webbplats. Se [Flödesvisualisering](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) i användarhandboken för Analysera.
* **Genesis:** Används inte längre som term. Det tidigare namnet på Data Connectors.
* **Global rapportsvit:** En informell term som tilldelats en rapportserie som samlar in träffar från flera webbplatser.
* **H-kod:** En föregångare till AppMeasurementet. I tidigare versioner av Adobe Analytics mättes kodversionerna med&quot;H version&quot;, till exempel H.27.5, H.26 osv.
* **Träff:** En enda bildbegäran som skickas till datainsamlingsservrar i Adobe. Både sidvyer och anpassade länkar kan kallas träffar.
* **Bildbegäran:** En genomskinlig 1x1-pixelbild som används för att kommunicera med datainsamlingsservrar i Adobe. En webbplats begär den här osynliga bilden med en lång frågesträng som innehåller data. Adobe returnerar den osynliga bilden och tolkar den frågesträng som tas emot.
* **Insight:** Kan avse:
   * Datans Workbench tidigare namn.
   * Custom Insight, ett historiskt namn för en anpassad trafikvariabel.
* **KPI:** Förkortning för nyckelresultatindikator. Mätvärden som hjälper ett företag att förstå hur deras webbplats fungerar. Varje organisation har olika nyckeltal som mäter olika aspekter av sin verksamhet. Se [Skapa ett dokument för lösningsdesign](/help/implement/prepare/solution-design.md) i Implementeringshandboken.
* **Svarstid:** Fördröjningen mellan när data samlas in och när de är tillgängliga i rapporter. Vanlig fördröjning i en rapportserie är 30-90 minuter. Se [Latens](/help/technotes/latency.md) i Technotes-handboken.
* **Starta:** Används inte längre som term. Det förkortade tidigare namnet på taggar i Adobe Experience Platform, Adobe aktuella implementeringslösning. Se [Översikt över taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) i användarhandboken för Adobe Experience Platform.
* **Liststatus:** En inställning som konverterar en typisk trafikvariabel som stöder flera värden i samma träff. Alla anpassade trafikvariabler kan bli en listprop om inställningen är aktiverad. Se [prop](../implement/vars/page-vars/prop.md) i Implementeringshandboken.
* **Listvar:** En distinkt variabel som är skild från konverteringsvariabler. Listvariabler har stöd för flera värden i samma träff, och variabelvärden bevaras vid ett besök, på liknande sätt som konverteringsvariabler. Endast tre listvariabler är tillgängliga för en organisation. Se [list](/help/implement/vars/page-vars/list.md) i Implementeringshandboken.
* **Inloggningsföretag:** En samling rapportsviter som används av din organisation. Vissa organisationer har flera inloggningsföretag som gäller för olika delar av organisationen.
* **Marknadsföringskanal:** En funktion i Adobe Analytics som kategoriserar träffar efter hur de kom till din webbplats. Den logik som används för att kategorisera träffar kan anpassas med regler för bearbetning av marknadsföringskanaler. Se [Komma igång med marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md) i användarhandboken för komponenter.
* **Mått:** En komponenttyp som innehåller kvantitativa data. Mätvärden innehåller vanligtvis siffror, t.ex. sidvyer, besök och Intäkter. En dimension är vanligtvis dess motsvarighet.
* **Mobiltjänster:** En pensionerad Adobe-produkt som kombinerar funktioner för mobilmarknadsföring för mobilappar från hela Adobe Experience Cloud, så att ni kan förstå och förbättra användarinteraktionen med era program.
* **Märk flera programsviter:** Att skicka samma träff till flera rapportsviter. I och med introduktionen till virtuella rapportsviter är denna praxis i stort sett inte längre nödvändig. De flesta satsningar på taggning av flera programsviter bidrar till att ge plats åt en global rapportserie.
* **Normalisering:** Ett sätt att organisera en visualisering som tar alla mätvärden och tvingar dem till samma proportioner, vilket gör det enklare att jämföra trender.
* **Förekomster:** En typ av mätvärde som visar hur många träffar en dimensionsuppgift har angetts eller beständig. Se [Förekomster](/help/components/metrics/occurrences.md) i användarhandboken för komponenter.
* **Omniture:** Används inte längre som term. Organisationen som ägde Adobe Analytics innan Adobe förvärvades 2009.
* **Banor:** Se Flöde.
* **Sidvy:** En typ av träff som ökar sidvisningen. Se [Sidvyer](/help/components/metrics/page-views.md) i användarhandboken för komponenter. Se även Träff.
* **Persistence:** Ett abstrakt koncept för konverteringsvariabler som tillåter länkning mellan ett variabelvärde och händelser som inträffar i olika träffar. Se även Förfallotid.
* **Primärt serveranrop:** Alternativt namn för bildbegäran eller träff, används mest i samband med märkning och fakturering av flera sviter. När samma träff skickas till flera rapportsviter är den första rapportsviten ett primärt serveranrop medan resten är sekundära serveranrop. Den här regeln gäller alla träfftyper, inklusive sidvisning och länkspårning. Se även Sekundära serveranrop.
* **Bearbetar regler:** Kan avse:
   * Bearbetningsregler är ett sätt att ändra datainsamling med hjälp av vissa regler i Admin Console. Se [Bearbetar regler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) i användarhandboken för Admin.
   * Bearbetningsregler för marknadsföringskanaler, en uppsättning regler som avgör vilken marknadsföringskanal en träff tillhör. Se [Bearbetningsregler för marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) i användarhandboken för Admin.
* **Prop:** Se Trafikvariabel.
* **Rankad rapport:** Ett rapportformat som vanligtvis följer en dimension med ett mätvärde. Med den här typen av rapporter kan du se de översta objekten, till exempel de sidor som visas mest på din webbplats. Se även Trended-rapport.
* **Realtid:** Visar konfigurerade variabler så snart de samlats in med liten eller ingen fördröjning. Se [Realtidsrapporter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) i användarhandboken för Admin.
* **Report Builder:** Ett Microsoft Excel-tillägg som gör att du kan skapa anpassade förfrågningar från Adobe Analytics-data.
* **Rapportsvit:** En överliggande behållare som du skickar data till. Alla rapporter i Adobe Analytics refererar till en rapportserie.
* **Rapporter och analyser:** Tidigare SiteCatalyst. Webbläsarlösning för rapportering och analys. Startverktyget i Analytics-paketet. Det här verktyget har [slutprodukt](https://experienceleague.adobe.com/docs/discontinued/using/reports-and-analytics.html).
* **Rullningsdatumintervall:** En typ av relativt datumintervall som ändras när tiden går. En rapport som visar de senaste 7 dagarna kan till exempel betraktas som ett löpande datumintervall. Se även statiskt datumintervall.
* **RSID:** Förkortning för rapportsvitens ID. En rapportsvit har både ett eget namn och ett rapportsvit-ID.
* **s.t():** Namnet på AppMeasurementet i ett sidvisningsbildbibliotek som skickar en bildbegäran. Vissa AppMeasurement används i bibliotek `s.track()` i stället. Se [t](../implement/vars/functions/t-method.md) i Implementeringshandboken.
* **s<span>.</span>tl():** Namnet på funktionen i ett AppMeasurementen bibliotek som skickar en begäran om länkspårningsbild. Vissa AppMeasurement används i bibliotek `s.trackLink()` i stället. Se [tl](../implement/vars/functions/tl-method.md) i Implementeringshandboken.
* **s_code.js:** Namnet på JavaScript-filen som används i tidigare versioner av Adobe Analytics. Det aktuella namnet på JavaScript-filen som används är AppMeasurement.js.
* **Satellit:** Används inte längre som term. Det tidigare produktnamnet för Dynamic Tag Management.
* **Sekundärt serveranrop:** Alternativt namn för bildbegäran eller träff, används mest i samband med märkning och fakturering av flera sviter. När samma träff skickas till flera rapportsviter är alla rapportsviter efter den första listan sekundära serveranrop. Se även primära serveranrop.
* **Segment:** Gör att du kan fokusera på en viss del av dina data. Se [Segmentering](/help/components/segmentation/seg-overview.md) i användarhandboken för komponenter.
* **Segmentbehållare:** Den del av ett segment som avgör hur mycket data som ska hämtas in. Behållare kan baseras på sidvisning, besök eller besökare. Se [Segmentering](/help/components/segmentation/seg-overview.md) i användarhandboken för komponenter.
* **Serialisering:** Se Händelseserialisering.
* **Serversamtal:** Alternativt namn för en bildförfrågan eller träff, används mest i samband med fakturering.
* **Enkel åtkomst:** Ett besök där en dimension bara hade ett unikt värde. Besöken kan få flera träffar, förutsatt att det inte finns flera unika värden. Se [Enkel åtkomst](/help/components/metrics/single-access.md) i användarhandboken för komponenter. Se även Studsa.
* **SiteCatalyst:** Används inte längre som term. Ett tidigare produktnamn för Adobe Analytics.
* **Lösningsdesigndokument:** Kallas även en referens för lösningsdesign eller SDR Ett internt dokument som hanteras av en organisation och som beskriver hur anpassade variabler används och den logik som används för att fylla i dem. Se [Skapa ett dokument för lösningsdesign](/help/implement/prepare/solution-design.md) i Implementeringshandboken.
* **Underrelation:** Används inte längre som term; ersätts med dimensionsuppdelning. I tidigare versioner av Adobe Analytics gav delrelationer möjlighet att bryta ned konverteringsvariabler. Se [Dela upp dimensioner](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) i användarhandboken för Analysera.
* **Success event:** En spårad åtgärd som en användare vidtagit. Organisationen avgör vilka händelser som ska spåras och vilka variabler för lyckade händelser som du använder för att spåra dem. Se [Anpassade händelser](/help/components/metrics/custom-events.md) i användarhandboken för komponenter.
* **Användare som stöds:** Se Kundsupportrepresentant.
* **Trafikvariabel:** Kallas också för proppar. Lagrar ett anpassat värde för en enda träff. Tidigare versioner av Adobe Analytics gav ett unikt värde, men förbättringar av plattformen gör anpassade trafikvariabler i stort sett onödiga. Adobe rekommenderar att du i de flesta fall använder anpassade konverteringsvariabler (eVars). Se [Prop](/help/components/dimensions/prop.md) -dimensionen i användarhandboken för komponenter.
* **Rapport:** Ett rapportformat som vanligtvis visar flera datumintervall med ett mätvärde. Med den här typen av rapporter kan du se hur ett mätresultat fungerar över tid. Se även Rankad rapport.
* **Unik besökare**: Representerar antalet unika personer som har besökt din webbplats. En enda unik besökare kan ha flera besök. Se [Unika besökare](/help/components/metrics/unique-visitors.md) i användarhandboken för komponenter.
* **Virtuell rapportsvit:** En virtuell behållare med data som refererar till en vanlig rapportserie och som tillåter att data förfinas. Data skickas inte till ett virtuellt rapportpaket. I stället skickas data till ett vanligt rapportpaket och ett virtuellt rapportpaket bygger vidare på insamlade data. Se [Virtuella rapportsviter](/help/components/vrs/vrs-about.md) i användarhandboken för komponenter.
* **Besök:** Representerar antalet unika sessioner som har ägt rum på din webbplats. Se [Besök](/help/components/metrics/visits.md) i användarhandboken för komponenter.
* **VISTA-regel:** Anpassad logik som skapats av Adobe på kundens begäran om att kopiera, analysera eller filtrera data på serversidan. VISTA-reglerna medför normalt merkostnader. Se även Bearbetningsregler.
* **Webbfyr:** Se Bildbegäran.
