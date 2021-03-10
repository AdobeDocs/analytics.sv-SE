---
title: DFA-integrering - information om slutdatum
description: Varför upphör DFA Data Connector för Adobe och vilka alternativ finns det?
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---


# DFA-integrering - information om slutdatum

Adobe presenterade nyligen [sina planer på en dataanslutning i slutet av livscykeln](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html), en äldre verktygslåda för integrering av data från tredje part (t.ex. ESP, VOC etc.) med Adobe Analytics.

## Varför går Data Connectors in i End-of-Life?

Den plattform som stöds för partnerintegrering är [Adobe Exchange](https://exchange.adobe.com/experiencecloud), som är utformad för att underlätta integrering av Adobe Digital Experience-program, integrering av CXM från tredje part och för att stödja de olika datakraven för både kunder och partners långt in i framtiden. Många partners som byggt upp sina integreringar med Data Connectors har redan migrerat integreringarna till Adobe Exchange, och fler partners planerar att göra det.

## Varför går DFA-integreringen in i End-of-Life?

I [januari 2020 meddelade Google](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html) att det kommer att fasa ut cookies från tredje part i Chrome senast 2022. Detta följer branschstandarder som Apple och Mozilla har ställt in för sina webbläsare Safari och Firefox. Integreringen av DFA är till stor del beroende av cookies från tredje part och kommer därför att bli ineffektiv och föråldrad genom att cookies från tredje part tas bort i de tre största webbläsarna. Google [förstärkte denna inställning i mars 2021](https://blog.google/products/ads-commerce/a-more-privacy-first-web) genom att meddela att de inte kommer att släppa någon alternativ lösning.

Tyvärr är det osannolikt att Google, som äger DFA-integreringen, kommer att återskapa den på Adobe Exchange-plattformen. Därför går vi framåt under antagandet att den befintliga integreringen upphör att fungera när Data Connectors kopplas från och inte har någon producerad ersättning.

En viktig och extra faktor är möjligheten att se över DFA-integreringen. Det gör att Adobe Analytics kan spåra fall där en användare såg en displayannons, inte klickade, men sedan besökte webbplatsen. &quot;Genomvisningar&quot; baseras på cookies från tredje part som kommer att fortsätta fasas ut under 2021. Detta är en marknadsfråga, inte bara ett Adobe-problem. Det finns för närvarande inga alternativ för att replikera dessa data.

## Vilka alternativ finns det för dig?

För kunder som är intresserade av att integrera data från displayannonser (utan &quot;genomgång&quot;) i Adobe Analytics har vi för närvarande följande alternativ:

* Adobe Advertising Cloud DSP-kunder kan utnyttja [en produkterad integrering med Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations) för att ange webbannonseringsdata från Google till Adobe Analytics. Denna integrering är vårt bästa alternativ och skulle vara vår rekommendation till kunderna. Med Ad Cloud DSP kan kunderna leverera sammankopplade upplevelser i alla annonskanaler, inklusive betald sökning, webbannonsering, video och andra. Läs mer [här](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction). Men Ad Cloud DSP påverkas också av att cookies från tredje part går förlorade.
* Adobe Experience Platform och [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en), som har funktioner för visning och integrering med andra datakällor. Kunderna kan hämta sina visningsdata från sin betalsökleverantör och överföra dessa data till Experience Platform. Sedan tar de in data direkt i CJA för att analysera tillsammans med andra datauppsättningar.
* Adobe Consulting (Engineering Architects) kan bygga en anpassad lösning för att importera annonsstatistik till Adobe Analytics. Den här lösningen är fortfarande under utveckling och alla kunder som är intresserade av att delta i betaversionen får gärna delta. Mer information om funktioner, tillgänglighet och kostnad visas när de blir tillgängliga.
* Du kan hantera din egen integrering av displayannonser med hjälp av funktionerna Datakällor och Klassifikationer i Adobe Analytics. Importera din betalda sökning och visa data manuellt med datakällor och klassificeringar [enligt beskrivningen här](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases). (Obs! det här dokumentet refererar till betalsökningar, men användningsfallet och konceptet är desamma och kan användas för visning).

Om du har ytterligare frågor eller support kan du kontakta [Adobe kundtjänst](https://helpx.adobe.com/se/contact/enterprise-support.ec.html).