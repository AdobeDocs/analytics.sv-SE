---
title: Komma igång med datakällor
description: Överför exempeldata till en utvecklingsrapportsserie.
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Komma igång med datakällor

Du kan följa de här stegen för att enkelt överföra exempeldata till en utvecklingsrapportsserie för att se hur arbetsflödet fungerar. När ni förstår processen kan ni utöka och anpassa den efter er organisations implementering.

>[!IMPORTANT]
>
>Följ de här stegen med hjälp av en utvecklings- eller testrapportsserie. Data som överförs via datakällor är **permanent**. Det påverkar produktionsrapportens data om de överförs där.

1. Logga in på Adobe Analytics via [https://experience.adobe.com](https://experience.adobe.com).
1. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL All Admin]** > **[!UICONTROL Data sources]**.
1. Välj en utvecklingsrapportsserie i listrutan högst upp till höger.
1. Klicka på **[!UICONTROL Create]** i det övre vänstra hörnet.
1. Under [!UICONTROL Select Category], välj &quot;[!UICONTROL Generic]&quot;, och under [!UICONTROL Select Type], välj &quot;[!UICONTROL Generic Data Source (Summary Data Only)]&quot;.
1. Klicka på **[!UICONTROL Activate]**. Ett popup-fönster öppnas som visar [!UICONTROL Data Source Activation Wizard].
   1. Steg 1: Ge datakällan ett namn och klicka på kryssrutan Ansvarsfriskrivning.
   1. Steg 2: Det här steget har varit mer användbart i tidigare versioner av Adobe Analytics. Klicka på en kryssruta och skriv sedan ett värde i textfältet bredvid den.
   1. Steg 3: Välj det mätvärde som ska inkluderas i datakällans mallfil. Välj Händelse 1 i listrutan.
   1. Steg 4: Det här steget har varit mer användbart i tidigare versioner av Adobe Analytics. Klicka på en kryssruta och skriv sedan ett värde i textfältet bredvid den.
   1. Steg 5: Välj den dimension som ska inkluderas i datakällans mallfil. Välj &quot;eVar1&quot; i listrutan.
   1. Steg 6: Granska sammanfattningen och visa de dimensioner och mått som ingår i mallfilen.
   1. Steg 7: Klicka på **[!UICONTROL Download]** för att hämta datakällans mallfil. Observera också inloggningsuppgifterna för FTP-webbplatsen, eftersom de används inom kort.
1. Datakällan har nu skapats. nästa steg är att ge den data som ska bearbetas. Öppna den hämtade filen i textredigeraren.
1. Mallfilen innehåller tre rader; två kommentarsrader (som börjar med &quot;`#`&quot;) och en rubrikrad:

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. Ange data på flera rader, där varje post avgränsas med en tabb. Använd inte blanksteg eller kommatecken för att avgränsa värden.
   * Den första kolumnen är datumet i följande format: `MM/DD/YYYY/HH/mm/SS`.
   * Den andra kolumnen är textvärdet som du vill ta med i eVar1.
   * Den tredje kolumnen är den mängd som du vill öka händelse 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. Spara filen. Om du vill kan du ge den ett annat filnamn. När filen har sparats kan du stänga textredigeraren.
1. I Utforskaren, Finder eller den FTP-klient du vill använda navigerar du till [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. När du uppmanas att ange inloggningsuppgifter använder du det användarnamn och lösenord som anges i det sista steget i guiden Skapa datakälla. Du kan referera till den igen genom att gå till [!UICONTROL Data sources] och klicka **[!UICONTROL FTP Info]** bredvid datakällan som du skapade.
1. När du har autentiserat drar du filen som du redigerade till det autentiserade FTP-fönstret.
1. Skapa en tom textfil på valfri plats utanför FTP-fönstret. Ge den samma filnamn som datakällfilen som du överförde till FTP-platsen, med ett undantag. I stället för en `.txt` filtyp, ge den en `.fin` filtyp. Kontrollera att operativsystemets inställningar tillåter dig att se och ändra filtyper.
1. Dra det tomma `.fin` till samma FTP-plats som datakällfilen. Förekomsten av `.fin` filen talar om för Adobe att datakällfilen är helt överförd och klar att importeras.
1. Efter flera minuter försvinner filen från FTP-platsen och visas i rapporter.
1. Uppdatera sidan Datakällor och validera att filen har importerats.
1. Navigera till Analysis Workspace och skapa ett projekt.
1. Dra eVar1 som en dimension till arbetsytan och händelse 1 som ett mått. Kontrollera att datumintervallet för arbetsytan innehåller de datum som du angav i datakällan.

   ![Exempel på rapport](assets/success-report.png)

## Nästa steg

[Filformat](file-format.md): Lär dig mer om hur du skapar en datakällfil som är anpassad efter din organisation.
