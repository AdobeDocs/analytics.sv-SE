---
description: Du kan hämta data från Analysis Workspace genom att kopiera dem eller i PDF- och CSV-format.
title: Hämta PDF- eller CSV-filer
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: d432fd5386c89b3db82d39b0c21603d96bcf13b9
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 1%

---


# Hämta PDF- eller CSV-filer från Workspace

Det finns flera olika sätt att exportera data från Analysis Workspace, beroende på vilken datauppsättning du vill analysera utanför verktyget och vem som behöver få informationen. Exporterade data kan vara i form av kopierade data, CSV- eller PDF-filer. En PDF-fil är vanligtvis att föredra om du vill att visualiseringar ska ingå i filen, medan en CSV-fil (eller kopierade data) är att föredra om du bara vill ha oformaterade textdata.

>[!IMPORTANT]
>
> Vissa alternativ som hänvisas till på den här sidan, till exempel **Hämta objekt som CSV**, är för närvarande i begränsad testning. [Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html)

## Ladda ned projekt som CSV eller PDF {#download-project}

Du kan ladda ned ett helt projekt genom att gå till **[!UICONTROL Project > Download as PDF (or as CSV)]**. Den hämtade filen innehåller alla tabeller och visualiseringar som visas (synliga) i projektet. En PDF-fil är vanligtvis att föredra om du vill att visualiseringar ska ingå i filen, medan en CSV-fil är att föredra om du bara vill ha oformaterade textdata.

![](assets/download-project.png)

När det gäller projektnedladdningar bör du tänka på följande:

* Projektet kan sparas eller inte sparas när du begär en projekthämtning. Endast sparade projekt kan dock [schemaläggas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html).
* Det kan ta flera minuter att exportera PDF-filer som hämtats i webbläsaren eftersom projektet körs på nytt på Adobe-servrar innan det återges i PDF-format. Vi rekommenderar att du inte lämnar projektet förrän PDF-filen har laddats ned i webbläsaren. Du kan dock fortsätta att ändra projektet medan du väntar. Om en PDF tar längre tid än fem minuter att återge uppmanas du att skicka den via e-post i stället.
* PDF-nedladdningar återges som en sida utan sidnumrering.
* När ett projekt återges som PDF återger vi det som finns på sidan. Om ett projekt har visualiseringar och paneler i anpassad storlek måste du ändra dem så att de storleksändras automatiskt (knappen i det övre högra hörnet) så att det inte finns något trunkerat innehåll.

## Kopiera data till Urklipp (snabbtangent: Ctrl+C) {#copy-data}

Med högerklicksalternativet **[!UICONTROL Copy to clipboard]** kan du snabbt kopiera data från arbetsytan och klistra in dem någon annanstans.

* Om du vill att den visade tabellen ska kopieras högerklickar du på tabellrubriken och väljer **Kopiera visade data till Urklipp**.
* Om du vill att en delmängd av data ska kopieras gör du en markering i tabellen och högerklickar sedan > **Kopiera markering till Urklipp**.

Dessutom `Ctrl+C` kopierar snabbtangenten ditt val till Urklipp. När du har kopierat kan du gå till ett annat verktyg och klistra in informationen (eller trycka `Ctrl+V`).

![](assets/copy-selection.png)

## Hämta data som CSV {#download-data}

Med högerklicksalternativet **[!UICONTROL Download data as CSV]** kan du hämta en datatabell eller datakällan för en visualisering som en CSV-fil.

* Högerklicka i tabellhuvudet **[!UICONTROL Download displayed data as CSV]**. Detta hämtar visade data i tabellen som en CSV-fil.
* Om en markering görs i tabellen, så står det **[!UICONTROL Download selection as CSV]**. Endast markeringen laddas ned med det här alternativet, i motsats till den fullständiga tabellen som visas.
* Högerklicka i huvudet på en visualisering **[!UICONTROL Download data as CSV]**. Detta hämtar datakälltabellen för en visualisering som en CSV-fil. Obs! Kartvyn stöder inte det här alternativet.

![](assets/download-data-viz.png)

## Hämta objekt som CSV {#download-items}

Om du vill analysera mer än de 400 synliga dataraderna i en tabell högerklickar du på tabellrubriken eller valfri rad och väljer **Hämta objekt som CSV (Dimensionens namn)**. Med det här alternativet exporteras upp till 50 000 dimensionsobjekt för den valda dimensionen (baserat på tabellsortering) med filter och segment. Om du väljer det här alternativet överst i tabellen exporteras den första dimensionen i tabellen. Även om inga begränsningar används i friformstabellen rekommenderar vi att alternativet Hämta objekt används i tabeller med mindre än 20 kolumner för att optimera prestandan.

>[!TIP]
>
> Om din dimension överstiger 50 000 objekt hämtar du filen med olika sorteringsmått tillämpade eller använder ett filter. Du kan t.ex. sortera efter besök i en nedladdning och sedan stigande efter besök i en andra nedladdning. Det här tipset kan hjälpa dig att hämta objekt med längre svans.

Du kan utföra flera uppgifter samtidigt i projektet och till och med navigera till ett nytt Workspace-projekt på samma flik medan hämtningen pågår. Hämtningen pausas om du öppnar en ny flik i webbläsaren. Hämtningen avbryts om du lämnar arbetsytan helt eller stänger webbläsarfliken.

![](assets/download-items.png)

### Nedladdad objektfil

Tabellens funktioner kommer att tillämpas på den hämtade filen enligt följande:

* Alla panelsegment används som filter.
* Uppdelningar **ovanför** den valda dimensionen i tabellen tillämpas som filter ovanför varje kolumn.
* Uppdelningar **under** den valda dimensionen i tabellen tas bort.

I exemplet ovan hämtas sidobjekt med panelsegmentet (kunder med nya besökare) och komponenterna ovan (marknadsföringskanal = e-post) som filter, och komponenterna nedan (mobilenhetstyp) tas bort från den hämtade CSV-filen.

![](assets/downloaded-file.png)

### Hämta meddelanden

När filen hämtas visas ett informationsmeddelande med förloppet. Du kan när som helst avbryta hämtningen genom att klicka på **[!UICONTROL Cancel download]**. Om du stänger popup **avbryts inte** hämtningen.

När filen är klar visas ett meddelande om att den är klar och filen hämtas till webbläsaren.

Om du begär mer än en nedladdning åt gången får du ett meddelande om att varje ytterligare nedladdning kommer att ställas i kö tills den tidigare nedladdningen är klar.

![](assets/toast.png)

## Vanliga frågor {#faq}

| Fråga | Svar |
| --- | --- |
| Varför är min nedladdade PDF-fil en sida? | Arbetsytan sidnumrerar för närvarande inte hämtade PDF-filer. |
| Kan jag exportera mer än 50 000 objekt med alternativet &quot;Hämta objekt som CSV&quot;? | Varje nedladdning kan innehålla upp till 50 000 dimensionsobjekt, men du kan ändra sorteringsordningen i tabellen för att hämta längre slutobjekt eller använda ett filter för att hämta mer specifika objekt. |
| Vad gör **[!UICONTROL Copy visualization]** du? | **[!UICONTROL Copy visualization]** är inte ett exportalternativ. Du kan kopiera en visualisering eller panel från en plats i Workspace till en annan. Exempel: från en panel till en annan i samma projekt, eller från ett projekt till ett annat projekt. [Se videon](https://www.youtube.com/watch?v=lvmAdKNfWQw) |

