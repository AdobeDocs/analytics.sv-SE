---
title: Anskaffningsrapporter i Adobe Analytics
description: Lär dig hur du skapar kundvärvningsbaserade rapporter med Analysis Workspace.
feature: Third-party Integration
exl-id: 2929d34b-8eb0-4105-a49c-02d536929fe0
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 0%

---

# Anskaffningsrapporter

Anskaffningsrapporter visar hur du får besökare till din webbplats.

I Adobe Analytics kallas rapporterna för **Marknadsföringskanaler**. De kräver en del grundläggande inställningar, men ger en mycket mer anpassad vy av kanalerna.

>[!IMPORTANT]
>
> Ställ in bearbetningsreglerna för marknadsföringskanaler för att använda dessa rapporter. Se [Komma igång med marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md) om du vill ha information om hur du bäst konfigurerar marknadsföringskanaler i din organisation.

Den här sidan förutsätter att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för användare av Google Analytics](create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## All trafik - kanaler

Visar en sammanställd vy över alla kanaler som besökare använder för att nå din webbplats.

1. På menyn Komponenter letar du reda på **Marknadsföringskanal** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

## All trafik - Treemaps

Visar en treemap över kanaltrafik. Den här rapporten liknar All Traffic - Channels, men visas på ett annat sätt.

1. Klicka på ikonen Visualiseringar till vänster och dra Treemap-visualiseringen till arbetsytan ovanför den tomma friformstabellen.
2. Klicka på ikonen Komponenter till vänster och dra sedan **Marknadsföringskanal** dimensionera till det stora frihandsritningsområdet med etiketten &#39;Släpp en dimension här&#39;.
3. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.
4. Observera att ytterligare mätvärden skapar ytterligare treemaps. Om bara en treemap önskas:
   1. Klicka på den översta cellen i det önskade måttet för att representera treemap.
   2. Skift-klicka på den sista cellen i samma måttkolumn för att markera kolumnen som blå. Om detta görs på rätt sätt finns en treemap i visualiseringen.
   3. Klicka på den färgade punkten i det övre högra hörnet av treemap-visualiseringen och klicka sedan på kryssrutan Lås markering.

Treemaps kan tillämpas på alla dimensioner, inte bara på marknadsföringskanaler.

## All trafik - källa/medel

Källrapporter och medierapporter visar vilka domäner som körde trafiken till er plats.

* The **Källa** den primära dimensionen är tillgänglig i Analysis Workspace som **Refererande domän** dimension.
* The **Medel** den primära dimensionen är tillgänglig i Analysis Workspace som  **Referenstyp** dimension.
* The **Nyckelord** den primära dimensionen är tillgänglig i Analysis Workspace som **Sök nyckelord** dimension.

1. På komponentmenyn letar du upp den önskade dimensionen ovan och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

Se följande sidor i användarhandboken för komponenter för mer information om deras respektive dimension:

* [Refererande domän](/help/components/dimensions/referring-domain.md)
* [Referenstyp](/help/components/dimensions/referrer-type.md)
* [Sök nyckelord](/help/components/dimensions/search-keyword.md)

## All trafik - referenser

* The **Källa** den primära dimensionen är tillgänglig i Analysis Workspace som **Refererande domän** dimension.
* The **Landningssida** den primära dimensionen är tillgänglig i Analysis Workspace som **Startsida** dimension.

1. Gå till komponentmenyn **Refererande domän** eller **Startsida** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

Se [Refererande domän](/help/components/dimensions/referring-domain.md) dimension i användarhandboken för komponenter om du vill ha mer information.

## Google Ads-rapporter och Search Console-rapporter

Adobe använder en funktion i Analysis Workspace som kallas Advertising Analytics för att hämta in reklam- och sökdata från flera plattformar, inklusive Google.

Funktionen för annonsanalys kräver att konfigurationen returnerar data. Se [Hjälp om Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) om du vill ha mer information om hur du aktiverar dessa ytterligare dimensioner i Analysis Workspace.

## Sociala rapporter

Sociala rapporter ger liknande information som deras respektive beteenderapport, utom i samband med sociala nätverk. Dessa data är tillgängliga i Analysis Workspace genom att kombinera en dimension med ett segment.

Ibland når besökarna webbplatsen via flera kanaler under samma session. En besökare kan till exempel klicka på en sida för sociala medier och sedan några minuter senare besöka en sökmotor för att nå din webbplats. I dessa fall kan icke-sociala domäner visas i den här rapporten. Om du vill utesluta icke-sociala domäner sorterar du rapporten efter besök eller skapar en kopia av segmentet som ska baseras på träffar i stället för besök. Se [Segmenteringsbehållare](/help/components/segmentation/seg-overview.md) i användarhandboken för Komponenter om du vill ha mer information.

### Socialt - nätverksreferenser

Rapporten Nätverksreferenser visar vilka sociala nätverksdomäner som körde trafik till din plats. Dessa data är tillgängliga i Analysis Workspace med **Refererande domän** dimension och **Besök från sociala webbplatser** segment.

1. På menyn Komponenter letar du reda på **Refererande domän** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. På menyn Komponenter letar du reda på **Besök från sociala webbplatser** segmentera och dra in på det lilla området precis ovanför frihandsritbordet med etiketten &#39;Släpp ett segment här&#39;.
3. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

### Sociala - landningssidor

Rapporten Landningssidor visar vilka sidor besökare fick ta del av efter att ha klickat på en länk via ett socialt nätverk. Dessa data är tillgängliga i Analysis Workspace med **Startsida** dimension och **Besök från sociala webbplatser** segment.

1. På menyn Komponenter letar du reda på **Startsida** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. På menyn Komponenter letar du reda på **Besök från sociala webbplatser** segmentera och dra in på det lilla området precis ovanför frihandsritbordet med etiketten &#39;Släpp ett segment här&#39;.
3. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

### Sociala - konverteringar

Rapporten Conversions visar e-handelsdata i samband med sociala nätverk. Det krävs ytterligare implementering för att dessa rapporter ska kunna användas på båda plattformarna. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att dessa data är korrekt konfigurerade för Analysis Workspace.

### Socialt - plugin-program

Pluginrapporten visar hur besökare interagerar med inbäddade plugin-program för sociala medier på din webbplats. Ytterligare implementering krävs för användning i Analysis Workspace. Adobe rekommenderar att man samarbetar med en implementeringskonsult för att säkerställa att dessa data samlas in korrekt.

### Socialt - användarflöde

Flödesrapporten Användare visar kunddata i samband med besökare som kommer via ett socialt nätverk.

1. Klicka på visualiseringsikonen till vänster och dra en Flow-visualisering till arbetsytan ovanför frihandstabellen
2. Klicka på ikonen Komponenter till vänster och dra sedan **Besök från sociala webbplatser** segmentet till det lilla området precis ovanför flödesvisualiseringen med namnet &#39;Släpp ett segment här&#39;.
3. Leta reda på **Sidor** dimension och klicka sedan på pilikonen för att visa sidvärden. Dimensionen är gul.
4. Leta reda på det sidvärde du vill börja med och dra det till utrymmet&quot;Dimension or item&quot; i mitten
5. Denna flödesrapport är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

## Kampanjer - alla

Kampanjrapporten finns i Analysis Workspace med **Spårningskod** dimension. Observera att det krävs ytterligare implementering för att samla in data när du använder spårningskod.

Det går att samla in UTM-parametrar i Adobe Analytics med hjälp av anpassade variabler (eVars). Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att spårningskodvärden samlas in korrekt i Adobe Analytics.

1. På menyn Komponenter letar du reda på **Spårningskod** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

## Kampanjer - Betalda nyckelord

Rapporten med betalda nyckelord visar hur varje nyckelord fungerar när en besökare klickar på en betalsöklänk från en sökmotor. The **Söknyckelord - Betald** finns i Analysis Workspace, men kräver en engångsinstallation av betald sökidentifiering för att samla in data. Se [Betalsökningsidentifiering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) i användarhandboken för Admin om du vill ha mer information om installationen.

1. På menyn Komponenter letar du reda på **Söknyckelord - Betald** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

## Kampanjer - Organiska nyckelord

Rapporten med organiska nyckelord visar hur varje nyckelord fungerar när en besökare klickar på en organisk söklänk från en sökmotor. The **Sök nyckelord - naturligt** finns i Analysis Workspace. Observera att om betald sökidentifiering inte är inställd samlar den här dimensionen in både betalda och naturliga nyckelord.

1. På menyn Komponenter letar du reda på **Söknyckelord - naturligt** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

## Kostnadsanalys

Den här rapporten visar besöks-, kostnads- och intäktsresultatdata för era betalda marknadsföringskanaler. Adobe tillhandahåller en dedikerad produkt som ger insikt i namnet Adobe Advertising Cloud. Om din organisation är intresserad av att använda den här produkten kontaktar du din organisations Account Manager.
