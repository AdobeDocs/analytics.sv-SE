---
description: Med kolumninställningar kan du konfigurera kolumnformatering, som vissa kan vara villkorliga.
title: Kolumninställningar
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
feature: Frihandstabeller
role: User, Admin
exl-id: 82034838-b015-4ca2-adb6-736f20a478d8
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 20%

---

# [!UICONTROL Column Settings]

[!UICONTROL Column Settings] gör att du kan konfigurera kolumnformatering, som vissa kan vara villkorliga.

## Redigera [!UICONTROL Column Settings] {#edit-column-settings}

Om du vill komma åt [!UICONTROL Column Settings] drar du en frihandstabell till projektet och klickar sedan på kugghjulsikonen i kolumnrubriken.

![](assets/column_settings.png)

Du kan redigera inställningar **för flera kolumner samtidigt**. Markera bara flera kolumner och klicka på inställningsikonen för någon av dessa kolumner. Alla ändringar du gör gäller för alla kolumner där celler är markerade.

| Element | Beskrivning |
| --- | --- |
| **Totalt antal celler** |  |
| Visa summor | Denna summa är vanligtvis lika med eller en delmängd av [!UICONTROL Grand Total]. Alla tabellfilter som används i friformstabellen, inklusive alternativet [!UICONTROL Include None], visas. |
| Visa totalsumma | Denna summa representerar alla träffar som har samlats in, ibland kallade&quot;rapportsvitsummor&quot;. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla träffar som matchar segmentvillkoren visas. Summan stöds inte för tabeller eller uppdelningar med [statiska rader](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| **Tabellceller** |  |
| Nummer | Avgör om en cell visar/döljer det numeriska värdet för måttet. Om måttet till exempel är Sidvyer är det numeriska värdet antalet sidvyer för radobjektet. |
| Procent | Avgör om en cell visar/döljer procentvärdet för måttet. Om måttet till exempel är Sidvyer är procentvärdet antalet sidvyer för radobjektet delat med de totala sidvyerna för kolumnen.  Obs!  Vi kan visa procenttal större än 100 % för att vara mer korrekta. Vi flyttar också det övre gränsvärdet till 1 000 % för att säkerställa att kolumnerna kan växa i för stora bredder. |
| Anomalier | Avgör om avvikelseidentifiering körs på värdena i den här kolumnen. |
| Radbryt rubriktext | Gör att du kan radbryta rubriktexten i frihandstabeller så att rubrikerna blir mer läsbara och tabellerna mer delbara. Detta är användbart för .pdf-återgivning och för mått med långa namn. Aktiverat som standard. |
| Tolka noll som inget värde | För celler med värdet 0 anger om en 0-cell eller en tom cell ska visas. Det här är användbart när du tittar på data för varje dag i en månad, och vissa dagar har inte inträffat än.  I stället för att visa 0 för framtida datum kan tomma celler visas i stället. Diagram följer även den här inställningen (d.v.s. de visar inte en linje eller en stapel med 0 värden när den här inställningen är markerad). |
| Bakgrund | Anger om en cell visar/döljer all cellformatering, inklusive stapeldiagrammet och villkorsstyrd formatering. |
| Stolpdiagram | Visar ett vågrätt stolpdiagram som representerar cellens värde i förhållande till totalvärdet för kolumnen. |
| Villkorsstyrd formatering | Se avsnittet nedan. |
| Förhandsgranskning av tabellcell | Visar en förhandsvisning av hur varje cell visas med de valda formateringsalternativen. |

## Villkorsstyrd formatering {#conditional-formatting}

Villkorsstyrd formatering tillämpar formatering på övre, mellersta och nedre gränser som du kan definiera. Om du använder villkorsstyrd formatering (färger o.s.v.) i frihandstabeller aktiveras även automatiskt vid uppdelning, såvida inte &quot;Anpassade&quot; gränser har valts.

![](assets/conditional-formatting.png)

| Element | Beskrivning |
| --- | --- |
| Villkorsstyrd formatering | Använder följande färger på celler baserat på datavärden: <ul><li>Grön: höga värden</li><li>Gul: mittpunktsvärden</li><li>Röd: låga värden</li></ul> <br> Om du ersätter ett mått i tabellen återställs gränserna för villkorsstyrd formatering. Om du ersätter ett mätvärde räknas gränserna för den kolumnen om (där ett mätvärde finns på X-axeln och ett mått på Y-axeln). |
| Använd procentgränser | Ändra gränsintervallet så att det baseras på procentvärden i stället för absoluta värden. Detta fungerar för mätvärden som endast är procentbaserade (som Studsfrekvens) samt för mätvärden som har ett antal och ett procenttal (som sidvyer). |
| Automatiskt genererad | Beräkna automatiskt övre/mellersta/nedre gränser baserat på data. Den övre gränsen är det största värdet i den här kolumnen. Den undre gränsen är det lägsta och mittpunkten är medelvärdet av de övre och nedre gränserna. |
| Anpassad | Tilldela manuellt övre/mellersta/nedre gränser. Då får du den flexibilitet du behöver för att avgöra när ett kolumnvärde blir bra, medelbra eller dåligt. |

## Använd en attribueringsmodell som inte är standard {#attribution}

Analysis Workspace stöder [attribuering](/help/analyze/analysis-workspace/attribution/overview.md) för nästan alla mätvärden.

1. Klicka på ikonen Inställningar (kugghjulet) i en kolumn i frihandstabellen.

   ![Kryssrutan Attribut](assets/attribution-checkbox.png)

1. Markera **[!UICONTROL Use non-default attribution model]** under **[!UICONTROL Data Settings]**. Mer information om olika attribueringsmodeller finns i [Attribution models](/help/analyze/analysis-workspace/attribution/models.md).

   ![Välj attribueringsmodell](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Hantera datakällor](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)

