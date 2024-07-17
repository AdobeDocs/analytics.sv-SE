---
description: Lär dig schemalägga rapporter.
title: Schemalägg en databegäran
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
feature: Report Builder
role: User, Admin
exl-id: 6aaadaa8-d68f-4a03-8838-53a61b152e31
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 0%

---

# Schemalägg arbetsböcker

Du kan schemalägga arbetsböcker, ange avancerade leveransalternativ, ange mottagare och visa schemahistoriken. Med avancerade leveransalternativ kan du konfigurera arbetsböcker som du vill skicka vid en viss tidpunkt eller i intervall. Du kan också ange i vilket filformat arbetsboken ska skickas.

Du kan till exempel schemalägga att arbetsböcker ska levereras omedelbart eller enligt ett återkommande schema, och ange filformatet i [!DNL Advanced Delivery Options]. Filstorleksgränsen är 5 MB för överföring av arbetsbok.

>[!NOTE]
>
>Du måste ha Excel 2007 eller kompatibilitetspaketet installerat för att kunna schemalägga en arbetsbok. Du kan ha högst 10 schemalagda arbetsböcker per licens för Report Builder. Du kan dock öka antalet genom att subtrahera från andra licenser. Gå till **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]** > **[!UICONTROL Report Builder Reports]** om du vill göra det. En arbetsbok som har schemalagts (eller överförts till arbetsboksbiblioteket) och som inte har ändrats (uppdaterats, ersatts) på mer än 28 månader kommer att tas bort.

>[!NOTE]
>
>&quot;Leveranstid&quot;/&quot;Dagtid&quot; som anges av användaren anger den tid som arbetsboken ska påbörja bearbetningen, inte den tid som den faktiskt kommer att levereras. Den faktiska tiden som arbetsboken levereras baseras främst på hur lång tid det tar att bearbeta (komplexa och stora arbetsböcker tar längre tid att bearbeta än enklare arbetsböcker). Om en arbetsbok t.ex. tar 15 minuter att bearbeta, kommer den faktiska leveranstiden att vara minst 15 minuter efter den ursprungligen angivna leveranstiden/&quot;Dagtid&quot;.
>Det finns dessutom ett antal andra faktorer som kan öka fördröjningen innan arbetsboken levereras ytterligare:
>
> * **Om du kör många olika scheman av samma typ samtidigt** kan systemet överbelastas. Schemaläggningssystemet tillåter endast ett fåtal (5-10) arbetsböcker av någon typ att köras samtidigt, så när fler än 5-10 är schemalagda samtidigt måste vissa vänta på att andra arbetsböcker ska avslutas innan de kan börja bearbeta. Problemet kan åtgärdas genom att man schemalägger ett företags arbetsböcker vid olika tidpunkter under dygnet eller timmen i stället för samtidigt.
> * Förutom den specifika arbetsbokstypen väntar arbetsböcker också i rad om företaget har **fler än 15-20 arbetsbokstyper som schemalagts samtidigt (för alla olika arbetsbokstyper)**. Detta kan minskas genom att tidsintervallen ökas i stället för att många körs exakt samtidigt.
> * **Problem i underordnade tjänster** som schemaläggaren förlitar sig på kan också påverka leveransen av arbetsböcker. Om du t.ex. använder API:erna separat för att köra arbetsböcker och fylla i API-begärandekön kan dina schemalagda arbetsböcker leverera långsamt medan du konkurrerar om den resursen.
> * **Rapportsvitens latens** (en fördröjning i datainsamlingen) kan även fördröja vissa schemalagda arbetsböcker.

## Schemalägg en arbetsbok

1. Generera och spara en arbetsbok.
1. Klicka på **[!UICONTROL Schedule]** i verktygsfältet Report Builder.

   Fliken [!UICONTROL Scheduled Reports] sammanfattar alla uppgifter som du har skapat samt antalet återstående uppgifter.
1. Klicka på **[!UICONTROL New]** på fliken **[!UICONTROL Scheduled Reports]**. I guiden Grundläggande schemaläggning visas de alternativ som används för att definiera den schemalagda rapporten.

   ![Skärmbild som visar guiden Grundläggande schemaläggning.](assets/simple-schedule-wizard.png)

1. Konfigurera följande alternativ i [!UICONTROL Basic Scheduling Wizard]:

| Fält | Beskrivning |
|--- |--- |
| Välj rapport | Arbetsbokens namn. För nya schemalagda rapporter fylls det här fältet i med det aktiva arbetsboksnamnet. |
| Välj | Visar sidan Välj rapport. Du kan välja en rapport från servern (där alla dina tidigare schemalagda arbetsböcker lagras) eller från den lokala datorn. Om du väljer en arbetsbok från den lokala enheten i .xls-format konverteras filen till .xlsx. Som en del av konverteringen öppnas filen i Excel och aktiveras. Om den markerade arbetsboken för den schemalagda rapporten har samma filnamn som arbetsboken som är öppen i Excel, väljs den lokala filen i stället för den fil som överfördes tidigare. Om du väljer en rapport från schemaläggningsdatabasen skapas en kopia av arbetsboken på servern med dess filnamn uppdaterat med 1. Den nyligen skapade schemalagda rapporten använder den kopierade arbetsboken. |
| Anpassa | Här kan du anpassa datumformatet. |
| Till | Visar adressboken i Outlook, om tillämpligt. |
| Skicka till: E-post | E-postmottagaren för arbetsboken. |
| Power BI | Mer information finns i [Publish Workbook till Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md). |
| Ämne | En användardefinierad beskrivning. |
| Schemaläggning | Här kan du ange när arbetsboken ska skickas. (Omedelbart, varje timme, varje dag, varje vecka, varje månad och varje år.) |

## Avancerade leveransalternativ

1. Klicka på **[!UICONTROL Advanced Delivery Options]** för att konfigurera fil- och publiceringsalternativ:

| Fält | Beskrivning |
|--- |--- |
| **Fliken Schemaläggning** |  |
| Leveranstid | Här kan du schemalägga arbetsboken direkt eller vid ett senare tillfälle. Tidpunkten på dagen är relativ till den tidszon som har angetts på datorn. |
| Återkommande mönster | Skickar arbetsboken baserat på dina val. |
| Intervall för återkommande | Här kan du ange när arbetsboken ska börja och sluta tas emot.   Obs! När du schemalägger en arbetsbok den första dagen i en aktuell period (vecka, månad, kvartal eller år) returneras endast data för den första dagen. |
| **Fliken Filalternativ** |  |
| Filformat | Gör att du kan välja ett leveransformat för Excel 2007 (.xlsx) eller 2003 (.xls), .pdf, .csv, .mht, .txt och .xml. |
| Filmål | Anger e-post eller FTP. Alternativen på sidan ändras beroende på vad du väljer. För FTP måste du se till att värden är tillgänglig externt. |
| Språk för filinnehåll | Anger det språk som du vill använda för omslagsbrevet. Du kan välja kinesiska (förenklad eller traditionell), tyska, franska, japanska, koreanska, portugisiska (Brasilien) eller spanska. |
| **Fliken Publiceringsalternativ** |  |
| Publicera på Power BI | <ul><li>Publish Workbook till Power BI</li><li>Publish Alla Report Builder begär som Power BI-datauppsättningar</li><li>Publish Alla formaterade tabeller som Power BI-datauppsättningar</li></ul> |
| Ange etiketten för den här Power BIET som | Etikettinformation |

1. Klicka på **[!UICONTROL OK]** och sedan på **[!UICONTROL Exit]**.

   Report Builder visar den schemalagda arbetsboken i [Schemalagd aktivitetshanterare](/help/analyze/report-builder/r-arb-scheduled-reports.md).
