---
title: Beteenderapporter i Adobe Analytics
description: Lär dig hur du skapar beteenderapporter i Adobe Analytics
translation-type: tm+mt
source-git-commit: e1cbdf87140b915dccbb8f64694797bb903d8ab8

---


# Beteenderapporter

Beteenderapporter visar information om hur användare interagerar med webbplatsen.

På den här sidan förutsätts att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för Google Analytics-användare](create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## Beteendeflöde

Beteendeflödesrapporten kan återskapas med Flow-visualisering.

1. Klicka på visualiseringsikonen till vänster och dra en Flow-visualisering till arbetsytan ovanför frihandstabellen
2. Leta reda på **siddimensionen** och klicka sedan på pilikonen för att visa sidvärden. Dimensionsvärden är gula.
3. Leta reda på det önskade sidvärdet som du vill börja med och dra det till utrymmet som är märkt &quot;Dimension eller item&quot; i mitten
4. Den här flödesrapporten är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

![Flödesrapport](/help/technotes/ga-to-aa/assets/flow.png)

## Webbplatsinnehåll - alla sidor

Sidrapporten visar prestanda för enskilda sidor på webbplatsen.

1. På menyn Komponenter letar du upp **siddimensionen** och drar den till det stora frihandsritabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Ett annat alternativ är att Adobe tillhandahåller flera färdiga arbetsytor som kallas mallar. Mallen Innehållskonsumtion (webb) ger ett liknande värde som rapporten för alla sidor.

1. Klicka *[!UICONTROL Project]>[!UICONTROL New]*, vilket öppnar ett modalt fönster med projektalternativ.
2. Klicka på mallen Innehållsförbrukning (webb) och sedan på Skapa.

## Webbplatsinnehåll - detaljerat innehåll

Med detaljrapporten för innehåll kan du ta en titt på sidtrafik efter URL-struktur. Ytterligare implementering krävs för användning i Analysis Workspace. Adobe rekommenderar att ni samarbetar med en implementeringskonsult för att säkerställa att dessa data samlas in korrekt.

## Webbplatsinnehåll - landningssidor

Rapporten om landningssidor visar de översta landningssidorna på er webbplats. Landningssidor är tillgängliga i Analysis Workspace som dimension för **startsidan** .

1. På menyn Komponenter letar du upp dimensionen **Inmatningssida** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Adobe rekommenderar att du använder **Visits** -måttet för den här dimensionen.

## Webbplatsinnehåll - Avsluta sidor

Rapporten om avslutningssidor visar de översta sidorna som blev den sista sidan vid en persons besök. Den är tillgänglig i Analysis Workspace under samma namn.

1. På menyn Komponenter letar du upp dimensionen **Avsluta sida** och drar den till det stora frihandsritabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Adobe rekommenderar att du använder **Visits** -måttet för den här dimensionen.

## Site Speed-rapporter

Platshastighetsrapporter visar hur snabbt sidorna läses in och visar möjligheter att öka sidans laddningstider.

Den här funktionen kräver ytterligare implementering på båda plattformarna. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att dessa data är korrekt konfigurerade för Analysis Workspace. Plugin-programmet [](/help/implement/vars/plugins/getpageloadtime.md) getPageLoadTime tilldelas vanligtvis till en eVar för att få prestandadata i Adobe Analytics.

## Webbplatssökningsrapporter

Webbplatssökningsrapporter ger insikt i hur besökarna använder webbplatsens interna sökfunktioner.

Den här funktionen kräver ytterligare implementering på båda plattformarna. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att säkerställa att dessa data är korrekt konfigurerade för Analysis Workspace. Vanligtvis hämtas en intern sökterm från en frågesträngsparameter och placeras i en eVar för rapportering.

## Händelserapporter

Händelser har stora strukturella skillnader mellan Google och Adobe Analytics. Båda kräver ytterligare implementeringsändringar för att fungera korrekt på respektive plattform.

* I Google Analytics definieras händelser i implementeringen som text. Händelser har kategorier, åtgärder och etiketter.
* I Adobe Analytics konfigureras händelser först i Admin Console där de tilldelas en identifierare. Den identifieraren används i implementeringskoden. Exempel:
   1. Du kan ange event1 i Admin Console som Registreringar.
   2. I implementeringen tar du med event1 i händelsvariabeln på bekräftelsesidan för registrering. Varje gång registreringsbekräftelsesidan visas ökar händelse1.
   3. I Analysis Workspace visas Registrations som ett mätvärde som kan användas i alla rapporter.

Eftersom den här funktionen kräver implementeringsändringar rekommenderar Adobe att du samarbetar med en implementeringskonsult för att säkerställa att data är korrekt konfigurerade för Analysis Workspace.

## Utgivarrapporter

På samma sätt som Google kräver en anslutning till Google Ad Manager erbjuder Adobe en dedikerad produkt som ger insikter som kallas Adobe Advertising Cloud. Om din organisation är intresserad av att använda den här produkten kontaktar du din organisations Account Manager.
