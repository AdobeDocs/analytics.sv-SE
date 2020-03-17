---
title: Anskaffningsrapporter i Adobe Analytics
description: Lär dig hur du skapar förvärvsbaserade rapporter med Analysis Workspace.
translation-type: tm+mt
source-git-commit: 2e3896501a036e20f9f392c325e0c8ff1d586fba

---


# Anskaffningsrapporter

Anskaffningsrapporter visar hur du får besökare till din webbplats.

I Adobe Analytics kallas dessa rapporter för **marknadsföringskanaler**. De kräver en del grundläggande inställningar, men ger en mycket mer anpassad vy av kanalerna.

> [!IMPORTANT]
>
> Ställ in bearbetningsreglerna för marknadsföringskanaler för att använda dessa rapporter. Se [Komma igång med marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md) för information om hur du bäst konfigurerar marknadsföringskanaler i din organisation.

På den här sidan förutsätts att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för Google Analytics-användare](create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## All trafik - kanaler

Visar en sammanställd vy över alla kanaler som besökare använder för att nå din webbplats.

1. På menyn Komponenter letar du reda på dimensionen för **marknadsföringskanalen** och drar den till det stora frihandsritabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

## All trafik - Treemaps

Visar en treemap över kanaltrafik. Den här rapporten liknar All Traffic - Channels, men visas på ett annat sätt.

1. Klicka på ikonen Visualiseringar till vänster och dra Treemap-visualiseringen till arbetsytan ovanför den tomma friformstabellen.
2. Klicka på ikonen Komponenter till vänster och dra sedan dimensionen för **marknadsföringskanalen** till det stora frihandsritabellområdet med etiketten &#39;Släpp en dimension här&#39;.
3. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.
4. Observera att ytterligare mätvärden skapar ytterligare treemaps. Om bara en treemap önskas:
   1. Klicka på den översta cellen i det önskade måttet för att representera treemap.
   2. Skift-klicka på den sista cellen i samma måttkolumn för att markera kolumnen som blå. Om detta görs på rätt sätt finns en treemap i visualiseringen.
   3. Klicka på den färgade punkten i det övre högra hörnet av treemap-visualiseringen och klicka sedan på kryssrutan Lås markering.

Treemaps kan tillämpas på alla dimensioner, inte bara på marknadsföringskanaler.

## All trafik - källa/medel

Källrapporter och medierapporter visar vilka domäner som körde trafiken till er plats.

* Den primära dimensionen **Källa** är tillgänglig i Analysis Workspace som dimensionen **Refererande domän** .
* Den primära **medeldimensionen** är tillgänglig i Analysis Workspace som dimension för **referenstyp** .
* Den primära **nyckelordsdimensionen** är tillgänglig i Analysis Workspace som **söknyckelordsdimension** .

1. På komponentmenyn letar du upp den önskade dimensionen ovan och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Se följande sidor i användarhandboken för komponenter för mer information om deras respektive dimension:

* [Refererande domän](/help/components/c-variables/dimensionslist/reports-referring-domains.md)
* [Referenstyp](/help/components/c-variables/dimensionslist/reports-ref-types.md)
* [Sök nyckelord](/help/components/c-variables/dimensionslist/reports-search-keywords.md)

## All trafik - referenser

* Den primära dimensionen **Källa** är tillgänglig i Analysis Workspace som dimensionen **Refererande domän** .
* Den primära dimensionen för **landningssidan** är tillgänglig i Analysis Workspace som dimension för **startsidan** .

1. På komponentmenyn letar du upp **referensdomänen** eller **startsidan** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [Refererande domän](/help/components/c-variables/dimensionslist/reports-referring-domains.md) i användarhandboken för komponenter.

## Google Ads-rapporter och Search Console-rapporter

Adobe använder en funktion i Analysis Workspace som kallas Advertising Analytics för att hämta annons- och sökdata från flera plattformar, inklusive Google.

Funktionen för annonsanalys kräver att konfigurationen returnerar data. Mer information om hur du aktiverar de här ytterligare dimensionerna i Analysis Workspace finns i hjälpen [om](/help/integrate/c-advertising-analytics/overview.md) annonsanalys.

## Sociala rapporter

Sociala rapporter ger liknande information som deras respektive beteenderapport, utom i samband med sociala nätverk. Dessa data är tillgängliga i Analysis Workspace genom att en dimension kombineras med ett segment.

Ibland når besökarna webbplatsen via flera kanaler under samma session. En besökare kan till exempel klicka på en sida för sociala medier och sedan några minuter senare besöka en sökmotor för att nå din webbplats. I dessa fall kan icke-sociala domäner visas i den här rapporten. Om du vill utesluta icke-sociala domäner sorterar du rapporten efter besök eller skapar en kopia av segmentet som ska baseras på träffar i stället för besök. Mer information finns i [Segmenteringsbehållare](/help/components/c-segmentation/seg-overview.md) i användarhandboken för komponenter.

### Socialt - nätverksreferenser

Rapporten Nätverksreferenser visar vilka sociala nätverksdomäner som körde trafik till din plats. Dessa data är tillgängliga i Analysis Workspace med hjälp av dimensionen **Refererande domän** och **besök från sociala webbplatser** .

1. På menyn Komponenter letar du upp dimensionen **Referensdomän** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. På menyn Komponenter letar du upp **Besök från sociala webbplatser** och drar in det lilla området precis ovanför frihandstabellen med namnet &#39;Släpp ett segment här&#39;.
3. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

### Sociala - landningssidor

Rapporten Landningssidor visar vilka sidor besökare fick ta del av efter att ha klickat på en länk via ett socialt nätverk. Dessa data är tillgängliga i Analysis Workspace med hjälp av **Entry Page** -dimensionen och **Besök från Social Sites** .

1. På menyn Komponenter letar du upp dimensionen **Inmatningssida** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. På menyn Komponenter letar du upp **Besök från sociala webbplatser** och drar in det lilla området precis ovanför frihandstabellen med namnet &#39;Släpp ett segment här&#39;.
3. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

### Sociala - konverteringar

Rapporten Conversions visar e-handelsdata i samband med sociala nätverk. Det krävs ytterligare implementering för att dessa rapporter ska kunna användas på båda plattformarna. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att dessa data är korrekt konfigurerade för Analysis Workspace.

### Socialt - plugin-program

Pluginrapporten visar hur besökare interagerar med inbäddade plugin-program för sociala medier på din webbplats. Ytterligare implementering krävs för användning i Analysis Workspace. Adobe rekommenderar att ni samarbetar med en implementeringskonsult för att säkerställa att dessa data samlas in korrekt.

### Socialt - användarflöde

Flödesrapporten Användare visar kunddata i samband med besökare som kommer via ett socialt nätverk.

1. Klicka på visualiseringsikonen till vänster och dra en Flow-visualisering till arbetsytan ovanför frihandstabellen
2. Klicka på ikonen Komponenter till vänster och dra sedan segmentet **Besök från sociala webbplatser** till det lilla området precis ovanför flödesvisualiseringen med namnet &#39;Släpp ett segment här&#39;.
3. Leta reda på **siddimensionen** och klicka sedan på pilikonen för att visa sidvärden. Dimensionsvärden är gula.
4. Leta reda på det önskade sidvärdet som du vill börja med och dra det till utrymmet som är märkt &quot;Dimension eller item&quot; i mitten
5. Den här flödesrapporten är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

## Kampanjer - alla

Kampanjrapporten är tillgänglig på Analysis Workspace med dimensionen **Tracking Code** . Observera att det krävs ytterligare implementering för att samla in data när du använder spårningskod.

Det går att samla in UTM-parametrar i Adobe Analytics med anpassade variabler (eVars). Adobe rekommenderar att ni samarbetar med en implementeringskonsult för att säkerställa att era kodvärden samlas in korrekt i Adobe Analytics.

1. På menyn Komponenter letar du upp dimensionen **Spårningskod** och drar den till det stora frihandsritabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

## Kampanjer - Betalda nyckelord

Rapporten med betalda nyckelord visar hur varje nyckelord fungerar när en besökare klickar på en betalsöklänk från en sökmotor. Dimensionen **Söknyckelord - betald** är tillgänglig i Analysis Workspace, men kräver en engångsinställning för betald sökidentifiering för att samla in data. Se [Betalsökningsidentifiering](/help/admin/admin/paid-search-detection/paid-search-detection.md) i användarhandboken för Admin för mer information om inställningarna.

1. På menyn Komponenter letar du upp **söknyckelordet - Betald** dimension och drar det till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

## Kampanjer - Organiska nyckelord

Rapporten med organiska nyckelord visar hur varje nyckelord fungerar när en besökare klickar på en organisk söklänk från en sökmotor. Dimensionen **Söknyckelord - naturligt** finns på arbetsytan för analyser. Observera att om betald sökidentifiering inte är inställd samlar den här dimensionen in både betalda och naturliga nyckelord.

1. På menyn Komponenter letar du reda på **söknyckelordet - Naturlig** dimension och drar det till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

## Kostnadsanalys

Den här rapporten visar besöks-, kostnads- och intäktsresultatdata för era betalda marknadsföringskanaler. Adobe tillhandahåller en dedikerad produkt som ger insikter som kallas Adobe Advertising Cloud. Om din organisation är intresserad av att använda den här produkten kontaktar du din organisations Account Manager.
