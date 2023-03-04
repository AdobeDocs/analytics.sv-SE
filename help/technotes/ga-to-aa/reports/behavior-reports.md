---
title: Beteenderapporter i Adobe Analytics
description: Lär dig hur du skapar beteenderapporter i Adobe Analytics
feature: Third-party Integration
exl-id: ea441afa-e595-4ffa-b446-d67e87f8a7c9
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---

# Beteenderapporter

Beteenderapporter visar information om hur användare interagerar med webbplatsen.

Den här sidan förutsätter att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för användare av Google Analytics](create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## Beteendeflöde

Beteendeflödesrapporten kan återskapas med Flow-visualisering.

1. Klicka på visualiseringsikonen till vänster och dra en Flow-visualisering till arbetsytan ovanför frihandstabellen
2. Leta reda på **Sida** dimension och klicka sedan på pilikonen för att visa sidvärden. Dimensionen är gul.
3. Leta reda på det sidvärde du vill börja med och dra det till utrymmet&quot;Dimension or item&quot; i mitten
4. Denna flödesrapport är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

![Flödesrapport](/help/technotes/ga-to-aa/assets/flow.png)

## Webbplatsinnehåll - alla sidor

Sidrapporten visar prestanda för enskilda sidor på webbplatsen.

1. På menyn Komponenter letar du reda på **Sidor** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

Ett annat alternativ är att Adobe tillhandahåller flera färdiga arbetsytor som kallas mallar. Mallen Innehållskonsumtion (webb) ger ett liknande värde som rapporten för alla sidor.

1. Klicka *[!UICONTROL Project]>[!UICONTROL New]*, som öppnar ett modalt fönster med projektalternativ.
2. Klicka på mallen Innehållsförbrukning (webb) och sedan på Skapa.

## Webbplatsinnehåll - detaljerat innehåll

Med detaljrapporten för innehåll kan du ta en titt på sidtrafik efter URL-struktur. Ytterligare implementering krävs för användning i Analysis Workspace. Adobe rekommenderar att man samarbetar med en implementeringskonsult för att säkerställa att dessa data samlas in korrekt.

## Webbplatsinnehåll - landningssidor

Rapporten om landningssidor visar de översta landningssidorna på er webbplats. Landningssidor är tillgängliga i Analysis Workspace som **Startsida** dimension.

1. På menyn Komponenter letar du reda på **Startsida** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

Adobe rekommenderar att du använder **Besök** mått för den här dimensionen.

## Webbplatsinnehåll - Avsluta sidor

Rapporten om avslutningssidor visar de översta sidorna som blev den sista sidan vid en persons besök. Det finns i Analysis Workspace under samma namn.

1. På menyn Komponenter letar du reda på **Avsluta sidan** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

Adobe rekommenderar att du använder **Besök** mått för den här dimensionen.

## Site Speed-rapporter

Platshastighetsrapporter visar hur snabbt sidorna läses in och visar möjligheter att öka sidans laddningstider.

Den här funktionen kräver ytterligare implementering på båda plattformarna. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att dessa data är korrekt konfigurerade för Analysis Workspace. The [getPageLoadTime, plugin](/help/implement/vars/plugins/getpageloadtime.md) tilldelas vanligtvis till en eVar för att få prestandadata i Adobe Analytics.

## Webbplatssökningsrapporter

Webbplatssökningsrapporter ger insikt i hur besökarna använder webbplatsens interna sökfunktioner.

Den här funktionen kräver ytterligare implementering på båda plattformarna. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att dessa data är korrekt konfigurerade för Analysis Workspace. Vanligtvis hämtas en intern sökterm från en frågesträngsparameter och placeras i en eVar för rapportering.

## Händelserapporter

Händelser har stora strukturella skillnader mellan Google och Adobe Analytics. Båda kräver ytterligare implementeringsändringar för att fungera korrekt på respektive plattform.

* I Google Analytics definieras händelser i implementeringen som text. Händelser har kategorier, åtgärder och etiketter.
* I Adobe Analytics konfigureras händelser först i Admin Console där de tilldelas en identifierare. Den identifieraren används i implementeringskoden. Exempel:
   1. Du kan ange event1 i Admin Console som Registreringar.
   2. I implementeringen tar du med event1 i händelsvariabeln på bekräftelsesidan för registrering. Varje gång registreringsbekräftelsesidan visas ökar händelse1.
   3. I Analysis Workspace visas&quot;Registreringar&quot; som ett mått som kan användas i alla rapporter.

Eftersom den här funktionen kräver implementeringsändringar rekommenderar Adobe att man samarbetar med en implementeringskonsult för att säkerställa att data är korrekt konfigurerade för Analysis Workspace.

## Utgivarrapporter

På samma sätt som Google kräver en anslutning till Google Ad Manager erbjuder Adobe en dedikerad produkt som ger insikt i Adobe Advertising Cloud. Om din organisation är intresserad av att använda den här produkten kontaktar du ditt Adobe-kontoteam.
