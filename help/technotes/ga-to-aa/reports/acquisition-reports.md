---
title: Anskaffningsrapporter i Adobe Analytics
description: Lär dig hur du skapar kundvärvningsbaserade rapporter med Analysis Workspace.
feature: Third-party Integration
exl-id: 2929d34b-8eb0-4105-a49c-02d536929fe0
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 0%

---

# Anskaffningsrapporter

Anskaffningsrapporter visar hur du får besökare till din webbplats.

I Adobe Analytics kallas dessa rapporter för **marknadsföringskanaler**. De kräver en del grundläggande inställningar, men ger en mycket mer anpassad vy av kanalerna.

>[!IMPORTANT]
>
> Ställ in bearbetningsreglerna för marknadsföringskanaler för att använda dessa rapporter. Se [Komma igång med marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md) för information om hur du bäst konfigurerar marknadsföringskanaler i din organisation.

Den här sidan förutsätter att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för Google Analytics-användare](create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## All trafik - kanaler

Visar en sammanställd vy över alla kanaler som besökare använder för att nå din webbplats.

1. Leta reda på dimensionen **Marknadskanal** på komponentmenyn och dra den till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

## All trafik - Treemaps

Visar en treemap över kanaltrafik. Den här rapporten liknar All Traffic - Channels, men visas på ett annat sätt.

1. Klicka på ikonen Visualiseringar till vänster och dra Treemap-visualiseringen till arbetsytan ovanför den tomma friformstabellen.
2. Klicka på ikonen Komponenter till vänster och dra sedan dimensionen **Marknadskanal** till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
3. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).
4. Observera att ytterligare mätvärden skapar ytterligare treemaps. Om du bara vill använda en treemap:
   1. Klicka på den översta cellen i det önskade måttet för att representera treemap.
   2. Skift-klicka på den sista cellen i samma måttkolumn för att markera kolumnen som blå. Om detta görs på rätt sätt finns en treemap i visualiseringen.
   3. Klicka på den färgade punkten i det övre högra hörnet av treemap-visualiseringen och klicka sedan på kryssrutan Lås markering.

Treemaps kan tillämpas på alla dimensioner, inte bara på marknadsföringskanaler.

## All trafik - Source/Medium

Source och medierapporter visar vilka domäner som körde trafik till er webbplats.

* Den primära dimensionen **Source** är tillgänglig i Analysis Workspace som dimensionen **Refererande domän**.
* Den primära dimensionen **Medium** är tillgänglig i Analysis Workspace som dimension av typen **Referent**.
* Den primära dimensionen **Nyckelord** är tillgänglig i Analysis Workspace som dimensionen **Sök nyckelord** .

1. På komponentmenyn letar du upp den önskade dimensionen ovan och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Se följande sidor i användarhandboken för komponenter för mer information om deras respektive dimension:

* [Refererande domän](/help/components/dimensions/referring-domain.md)
* [Referenstyp](/help/components/dimensions/referrer-type.md)
* [Sök nyckelord](/help/components/dimensions/search-keyword.md)

## All trafik - referenser

* Den primära dimensionen **Source** är tillgänglig i Analysis Workspace som dimensionen **Refererande domän**.
* Den primära dimensionen för **landningssidan** är tillgänglig i Analysis Workspace som dimensionen för **anmälningssidan**.

1. Leta reda på dimensionen **Referensdomän** eller **Startsida** på komponentmenyn och dra den till det stora frihandstabellområdet med namnet &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i dimensionen [Referensdomän](/help/components/dimensions/referring-domain.md) i användarhandboken för komponenter.

## Google Ads-rapporter och Search Console-rapporter

Adobe använder en funktion i Analysis Workspace som kallas Advertising Analytics för att hämta in reklam- och sökdata från flera plattformar, inklusive Google.

Funktionen för annonsanalys kräver att konfigurationen returnerar data. Mer information om hur du aktiverar de här extra dimensionerna i Analysis Workspace finns i [hjälpen för Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md).

## Sociala rapporter

Sociala rapporter ger liknande information som deras respektive beteenderapport, utom i samband med sociala nätverk. Dessa data är tillgängliga i Analysis Workspace genom att kombinera en dimension med ett segment.

Ibland når besökarna webbplatsen via flera kanaler under samma session. En besökare kan till exempel klicka på en sida för sociala medier och sedan några minuter senare besöka en sökmotor för att nå din webbplats. I dessa fall kan icke-sociala domäner visas i den här rapporten. Om du vill utesluta icke-sociala domäner sorterar du rapporten efter besök eller skapar en kopia av segmentet som ska baseras på träffar i stället för besök. Mer information finns i [Segmenteringsbehållare](/help/components/segmentation/seg-overview.md) i användarhandboken för komponenter.

### Socialt - nätverksreferenser

Rapporten Nätverksreferenser visar vilka sociala nätverksdomäner som körde trafik till din plats. Dessa data är tillgängliga i Analysis Workspace med segmentet **Referensdomän** och **Besök från sociala webbplatser**.

1. Leta reda på dimensionen **Referensdomän** på komponentmenyn och dra den till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. På menyn Komponenter letar du reda på segmentet **Besök från sociala webbplatser** och drar in det lilla området precis ovanför frihandstabellen med namnet &#39;Släpp ett segment här&#39;.
3. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

### Sociala - landningssidor

Rapporten Landningssidor visar vilka sidor besökare fick ta del av efter att ha klickat på en länk via ett socialt nätverk. Dessa data är tillgängliga i Analysis Workspace med segmentet **Inmatningssida** och **Besök från sociala webbplatser**.

1. På menyn Komponenter letar du upp dimensionen **Inmatningssida** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. På menyn Komponenter letar du reda på segmentet **Besök från sociala webbplatser** och drar in det lilla området precis ovanför frihandstabellen med namnet &#39;Släpp ett segment här&#39;.
3. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

### Sociala - konverteringar

Rapporten Conversions visar e-handelsdata i samband med sociala nätverk. Det krävs ytterligare implementering för att rapporterna ska kunna användas på båda plattformarna. Adobe rekommenderar att man samarbetar med en implementeringskonsult för att säkerställa att dessa data är korrekt konfigurerade för Analysis Workspace.

### Socialt - plugin-program

Pluginrapporten visar hur besökare interagerar med inbäddade plugin-program för sociala medier på din webbplats. Ytterligare implementering krävs för Analysis Workspace. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att dessa data samlas in korrekt.

### Socialt - användarflöde

Flödesrapporten Användare visar kunddata i samband med besökare som kommer via ett socialt nätverk.

1. Klicka på visualiseringsikonen till vänster och dra en Flow-visualisering till arbetsytan ovanför frihandstabellen
2. Klicka på ikonen Komponenter till vänster och dra sedan segmentet **Besök från sociala webbplatser** till det lilla området precis ovanför flödesvisualiseringen med namnet &#39;Släpp ett segment här&#39;.
3. Leta reda på dimensionen **Sidor** och klicka sedan på pilikonen för att visa sidvärden. Dimension-objekt är gulfärgade.
4. Leta reda på det sidvärde du vill börja med och dra det till det utrymme som heter Dimension eller objekt i mitten
5. Den här flödesrapporten är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

## Kampanjer - alla

Kampanjrapporten är tillgänglig i Analysis Workspace med dimensionen **Spårningskod**. Observera att det krävs ytterligare implementering för att samla in data när du använder spårningskod.

Det går att samla in UTM-parametrar i Adobe Analytics med hjälp av anpassade variabler (eVars). Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att spårningskodvärden samlas in korrekt i Adobe Analytics.

1. Leta reda på dimensionen **Spårningskod** på menyn Komponenter och dra den till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

## Kampanjer - Betalda nyckelord

Rapporten med betalda nyckelord visar hur varje nyckelord fungerar när en besökare klickar på en betalsöklänk från en sökmotor. Dimensionen **Söknyckelord - betald** är tillgänglig i Analysis Workspace, men kräver en engångsinställning av betald sökidentifiering för att samla in data. Se [Betalsökningsidentifiering](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) i användarhandboken för administratörer för mer information om inställningarna.

1. Leta reda på dimensionen **Sök nyckelord - Betald** på komponentmenyn och dra den till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

## Kampanjer - Organiska nyckelord

Rapporten med organiska nyckelord visar hur varje nyckelord fungerar när en besökare klickar på en organisk söklänk från en sökmotor. Dimensionen **Sök efter nyckelord - naturligt** är tillgänglig i Analysis Workspace. Observera att om betald sökidentifiering inte är inställd samlar den här dimensionen in både betalda och naturliga nyckelord.

1. Leta reda på dimensionen **Sök efter nyckelord - naturligt** på komponentmenyn och dra den till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

## Kostnadsanalys

Den här rapporten visar besöks-, kostnads- och intäktsresultatdata för era betalda marknadsföringskanaler. Adobe tillhandahåller en dedikerad produkt som ger insikt i Adobe Advertising Cloud. Om din organisation är intresserad av att använda den här produkten kontaktar du ditt Adobe-kontoteam.
