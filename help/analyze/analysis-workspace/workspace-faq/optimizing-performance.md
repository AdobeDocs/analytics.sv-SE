---
description: Faktorer som kommer att påverka Workspace prestanda och optimeringar som du kan göra
title: Analysis Workspace prestandafaktorer och optimering
feature: Workspace Basics
role: User, Admin
exl-id: 7a675f53-2774-4c7b-af1b-79e52e7d5cfb
source-git-commit: 4cbcdc1e1287c301fe4452370e3db1f4b9b3f3a1
workflow-type: tm+mt
source-wordcount: '2533'
ht-degree: 0%

---

# Optimera [!UICONTROL Analysis Workspace performance]

Olika faktorer kan påverka prestanda i ett projekt inom Analysis Workspace. Det är viktigt att du vet vad dessa medarbetare är innan du börjar bygga ett projekt, så att du kan planera och bygga projektet på det optimala sättet. Den här sidan innehåller en lista med faktorer som påverkar prestanda och optimeringar som du kan göra för att få bästa prestanda i Analysis Workspace.

## [!UICONTROL Help] > [!UICONTROL Performance] i Analysis Workspace

Under **Analysis Workspace > [!UICONTROL Help] >[!UICONTROL Performance]** kan du se faktorer som påverkar projektets prestanda, inklusive nätverk, webbläsare och projektfaktorer. Du får bäst resultat om du tillåter att projektet läses in fullständigt innan du öppnar sidan Prestanda.

* Kolumnen Aktuellt projekt visar resultaten för ditt aktuella projekt och din användarmiljö.
* I kolumnen Riktlinje visas det rekommenderade tröskelvärdet för Adobe för varje faktor.

Dessutom kan du **hämta prestandainnehållet som CSV** och enkelt dela det med Adobe kundtjänst eller dina interna IT-team.

>[!NOTE]
>
>Informationen på sidan Prestanda varierar varje gång som modalen öppnas, eftersom faktorerna kan ändras. Dessutom kommer Adobe att fortsätta att förfina riktlinjerna i takt med att mer data blir tillgängliga.

![](assets/performance-modal.png)

## Nätverksfaktorer

[!UICONTROL Help] > [!UICONTROL Performance] nätverksfaktorer omfattar:

| Faktor | Definition | Berörd av | Optimering |
| --- | --- | --- | --- |
| Anslutning till Adobe | Adobe skickar in 10 testanrop när prestandasidan öppnas. Detta motsvarar den procentandel av anropet till Adobe som lyckas. | Problem med lokala nätverk eller Adobe kommer att påverka den här faktorn. | Kontrollera status.adobe.com för att verifiera om det finns några kända serviceproblem. Validera sedan din lokala nätverksanslutning. |
| Internetbandbredd | Endast för Google Chrome. Webbläsarens uppskattning av bandbredden på din plats. Riktlinjen är 2,0 MB/s. | Din lokala nätverksanslutning kommer att påverka den här faktorn. | Verifiera din lokala nätverksanslutning. |
| Internetfördröjning | Adobe skickar in 10 testanrop när prestandasidan öppnas. Detta anger den tid det i genomsnitt tar för varje begäran att åka till Adobe och returneras. Enklare uttryckt är det ett mått på hur snabbt Internet är mellan er plats och Adobe. Riktlinjen är &lt; 1 sekund. | Problem med lokala nätverk, många öppna webbläsarflikar eller problem med Adobe påverkar detta. | Kontrollera status.adobe.com för att verifiera om det finns några kända serviceproblem. Validera sedan den lokala nätverksanslutningen och stäng webbläsarflikar som inte används. |

## Webbläsarfaktorer

[!UICONTROL Help] > [!UICONTROL Performance] webbläsarfaktorer inkluderar:

| Faktor | Definition | Berörd av | Optimering |
| --- | --- | --- | --- |
| Beräkningshastighet | Hur snabbt datorn utför ett behandlingstest. Riktlinjen är &lt; 750 ms. | Din maskinvara och samtidiga program kommer att påverka den här faktorn. | Öppna Aktivitetshanteraren (PC) eller Aktivitetsövervakaren (Mac) för att avgöra om några program kan stängas. Stäng sedan webbläsarflikarna eller andra program som inte används. <br><br>Om de här åtgärderna inte hjälper dig, diskutera maskinvaruinformation med IT-teamet. |
| Minne som används | Endast för Google Chrome. Alla Workspace-flikar i en webbläsare i Google Chrome delar totalt 4 GB minne. Detta motsvarar den procentandel av minnestilldelningen som används av det aktuella projektet. Riktlinjen är 3 500 MB, vilket är den punkt där Workspace börjar få minnesfel. | Att arbeta på flera flikar eller hämta 50000 rader data bidrar till ökad minnesanvändning. | Om du får ett minnesfel stänger du andra Workspace-flikar och/eller kör 50000-radnedladdningar en i taget. |
| Lokalt lagringsutrymme används | Data som lagras lokalt på datorn för användning i webbläsaren. Varje ursprung (t.ex. experience.adobe.com) har en tolerans på 10 MB. | Analysis Workspace använder lokal lagring för flera funktioner, bland annat för att lagra automatiskt sparade (befintliga) projekt, användarinställningar och funktionsflaggor. | För att säkerställa att Analysis Workspace funktioner inte störs bör du rensa den lokala lagringen för domänen experience.adobe.com. |
| Återgivningshastighet | FPS står för bildrutor per sekund, vilket är hur många gånger per sekund webbläsaren ritar sidan på skärmen. 24 bildrutor/s är det som det mänskliga ögat vanligen kan se. Om antalet bildrutor/s är lägre än så kommer du att upptäcka återgivningsproblem i Workspace. | FPS påverkas av multikörning i många Workspace-projekt samtidigt och storleken på det projekt som visas är större. Andra program som körs på datorn kan ha en effekt, t.ex. strömning, bakgrundsskannrar m.m. Dessutom kommer maskinvaran att påverka den här faktorn. | Öppna Aktivitetshanteraren (PC) eller Aktivitetsövervakaren (Mac) för att avgöra om några program kan stängas. Stäng sedan webbläsarflikarna eller andra program som inte används. <br><br>Om de här åtgärderna inte hjälper dig, diskutera maskinvaruinformation med IT-teamet. |

## Projektfaktorer

[!UICONTROL Help] > [!UICONTROL Performance] projektfaktorer inkluderar:

| Faktor | Definition | Optimering |
| --- | --- | --- |
| Antal begäranden | Det totala antalet begäranden som gjorts till Adobe för att hämta data som visas i projektet. Frågorna innehåller rankade begäranden om tabeller, avvikelseidentifiering, miniatyrbilder, komponenter som visas i den vänstra listen med mera. Exkluderar komprimerade paneler och visualiseringar. Riktlinjen är 100. | Förenkla projektet där det är möjligt genom att dela upp data i flera projekt som har ett specifikt syfte eller en grupp intressenter. Använd taggar för att ordna projekt i teman och använd [direktlänkar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) för att skapa en intern innehållsförteckning så att intressenter enklare kan hitta det de behöver. |
| Utökade paneler (av totalt antal paneler) | Antalet expanderade paneler av det totala antalet paneler i projektet. Riktlinjen är 5. | När du har vidtagit åtgärder för att förenkla ditt projekt kan du komprimera paneler i projektet som inte behöver visas vid inläsning. När projektet öppnas bearbetas bara expanderade paneler. Komprimerade paneler bearbetas inte förrän användaren expanderar dem. |
| Utökade visualiseringar (av totalt antal visualiseringar) | Antalet utökade tabeller och visualiseringar av den totala mängden i projektet, inklusive dolda datakällor. Riktlinjen är 15. | När du har vidtagit åtgärder för att förenkla ditt projekt kan du komprimera visualiseringar i ditt projekt som inte behöver visas vid inläsning. Prioritera de bilder som är viktigast för konsumenten av rapporten och dela upp stödet till bilder i en separat, mer detaljerad panel eller projekt vid behov. |
| Antal frihandsceller | Det totala antalet frihandstabellceller i projektet, beräknat med rader * kolumner i alla tabeller. Utesluter dolda datakällor. Riktlinjen är 4000. | Minska antalet kolumner i tabellen till de mest relevanta datapunkterna. Minska antalet rader i tabellen genom att justera antalet rader som visas, använda ett tabellfilter eller använda ett segment. |
| Tillgängliga komponenter | Det totala antalet komponenter som har hämtats i projektets vänstra del i alla rapportsviter i projektet. Detta påverkar hastigheten som den vänstra listen läses in i och hur snabbt sökresultaten returneras i den. Riktlinjen är 2000. | Tala med produktadministratören om hur du skapar en välstrukturerad virtuell rapportsvit med en mer skräddarsydd uppsättning komponenter. |
| Använda komponenter | Det totala antalet komponenter som används i projektet. Riktlinjen är 100. | Antalet använda komponenter påverkar inte prestandan direkt. Komplexiteten hos dessa komponenter kommer dock att bidra till projektets prestanda. Se optimeringarna i avsnittet&quot;Ytterligare faktorer&quot; nedan. |
| Senaste datumintervall | Den här faktorn visar det längsta datumintervallet som används i projektet. Riktlinjen är ett år. | Dra inte in mer data än du behöver när det är möjligt. Begränsa panelkalendern till relevanta datum för analysen eller använd datumintervallkomponenter (lila komponenter) i frihandstabellerna. Datumintervall som används i en tabell åsidosätter panelens datumintervall. Du kan till exempel lägga till sista månaden, sista veckan och igår i tabellkolumnerna för att begära dessa specifika dataintervall. Titta på [den här videon](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html) om du vill ha mer information om hur du arbetar med datumintervall i Analysis Workspace. <br><br>Minimera dessutom antalet jämförelser mellan år och år som används i projektet. När en jämförelse mellan år och år beräknas, utförs en genomgång av alla 13 månaders data mellan de givna månaderna. Detta har samma effekt som att ändra panelens datumintervall till de senaste 13 månaderna. |

## Begärandefaktorer

[!UICONTROL Help] > [!UICONTROL Performance] förfrågningsfaktorer

Använd följande diagram och termer för att lära dig hur begäranden behandlas och de olika faktorer som påverkar bearbetningstiderna:

>[!NOTE]
>
>Rekommenderade riktlinjer för dessa faktorer baseras på Medium komplexitetspoäng för att rapportera förfrågningar.


### Bearbetningsdiagram för begäran

![Begär bearbetning](assets/request-processing.png)

### Bearbetningsvillkor för begäran

| Faktor | Definition | Optimering |
| --- | --- | --- |
| [!UICONTROL **Genomsnittlig begärandetid**] | Den tid som krävs från det att begäran initieras till dess att den är slutförd. Riktlinjen är 15 sekunder. <p>I diagrammet [Begäranbearbetning](#request-processing-diagram) ovan representerar begärandetiden hela processen, från **Analysis Workspace-begäran initierad** till **Analysis Workspace-begäran slutförd**.</p> |  |
| [!UICONTROL **Senaste begärandetid**] | Den tid som krävs från det att begäran initieras till dess att den är slutförd. <p>I diagrammet [Begäranbearbetning](#request-processing-diagram) ovan representerar begärandetiden hela processen, från **Analysis Workspace-begäran initierad** till **Analysis Workspace-begäran slutförd**.</p> |  |
| [!UICONTROL **Genomsnittlig sökningstid**] | Eftersom Analysis Workspace endast lagrar hash-värdet för strängar som används i något segment utförs **Lookups** varje gång du bearbetar ett projekt för att matcha hash-värdena med rätt värden. Riktlinjen är under 2 sekunder.<p>Detta kan vara en resurskrävande process, beroende på antalet värden som eventuellt matchar hash-värdet. </p><p>I diagrammet [Bearbetning av begäran](#request-processing-diagram) ovan visas uppslagstiden i fasen **Uppslag** (vid tiden för **Bearbetning av begärandemotor**).</p> | Om förfrågningar går långsammare här beror det förmodligen på att du har för många strängsegment i ditt projekt, eller på att du har strängar med för många generiska värden som har för många möjliga matchningar. |
| [!UICONTROL **Genomsnittlig kötid**] | Den totala väntetiden i kön innan begäranden bearbetas. Riktlinjen är 5 sekunder.<p>I diagrammet [Begäranbearbetning](#request-processing-diagram) ovan visas kötiden i fasen **Begär motorkö** och **Serverkö**.</p> | Om förfrågningar går långsammare här kan det bero på att för många förfrågningar körs samtidigt i organisationen. Försök köra begäran vid låg belastning. |
| [!UICONTROL **Genomsnittlig serverbearbetningstid**] | Genomsnittlig tid det tar att behandla begäran.<p>I diagrammet [Begäranbearbetning](#request-processing-diagram) ovan visas den genomsnittliga serverbearbetningstiden i fasen **Serverkö** och **Serverbearbetning**. Riktlinjen är tio sekunder | Om förfrågningar går långsammare här är det troligt att projektet har för långa datumintervall eller komplexa visualiseringar. Prova att korta ned projektets datumintervall för att minska bearbetningstiden. |
| [!UICONTROL **Komplexitet**] | Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran. Riktlinjen är Medium eller lägre. <p>Möjliga värden är:</p> <ul><li>[!UICONTROL **Låg**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **Hög**]</li></ul>Värdet påverkas av värdena i följande kolumner:<ul><li>[!UICONTROL **Månadsgränser**]</li><li>[!UICONTROL **Kolumner**]</li><li>[!UICONTROL **Segment**]</li></ul> |  |
| [!UICONTROL **Månadsgränser**] | Antalet månader som ingår i en begäran. Fler månadsgränser gör begäran ännu mer komplex. Riktlinjen är 6 eller färre. | Om förfrågningar går långsammare här kan det bero på att månadsgränserna i ditt projekt är för stora. Försök att minska antalet månader. |
| [!UICONTROL **Kolumner**] | Antalet mått och uppdelningar i begäran. Fler kolumner ökar komplexiteten i begäran. Riktlinjen är 10 eller färre. | Om förfrågningar går långsammare här kan det bero på att det finns för många kolumner i projektet. Försök att minska antalet kolumner. |
| [!UICONTROL **Segment**] | Antalet segment som används i begäran. Fler segment ökar komplexiteten i begäran. Riktlinjen är 5 eller färre. | Om förfrågningar går långsammare här kan det bero på att det finns för många segment i projektet. Försök att minska antalet segment. |

## Ytterligare faktorer

Ytterligare faktorer som inte finns med i Hjälp > Prestanda är:

| Faktor | Definition | Berörd av | Optimering |
| --- | --- | --- | --- |
| Segmentkomplexitet | Integrerade segment kan ha en betydande inverkan på projektresultatet. | Faktorer som ökar komplexiteten i ett segment (i fallande effektordning) är bland annat: <ul><li>Operatorer för &quot;contains&quot;, &quot;contains any of&quot;, &quot;match&quot;, &quot;starting with&quot; eller &quot;ends with&quot; </li><li>Sekventiell segmentering, särskilt när dimensionsbegränsningar (inom/efter) används </li><li>Antal unika dimensionsobjekt inom dimensioner som används i segmentet (t.ex. Sida = &#39;A&#39; när sidan har 10 unika objekt blir snabbare än Sida = &#39;A&#39; när sidan har 100000 unika objekt) </li><li>Antal olika dimensioner som används (t.ex. Sida = &quot;Hem&quot; och Sida = &quot;Sökresultat&quot; blir snabbare än eVar 1 = &quot;Rödt&quot; och eVar 2 = &quot;Blått&quot;)</li><li>Många OR-operatorer (i stället för AND)</li><li>Kapslade behållare som varierar i omfång (t.ex. &quot;Träff&quot; inuti &quot;Besök&quot; inuti &quot;Besök&quot;)</li></ul> | Vissa av komplexitetsfaktorerna kan inte förhindras, men leta efter möjligheter att minska komplexiteten i era segment. Ju mer specifik du kan vara med dina segmentkriterier, desto bättre. Exempel:<ul><li>Med behållare blir det snabbare att använda en enda behållare högst upp i segmentet än en serie kapslade behållare.</li><li>Med operatorer blir&quot;lika&quot; snabbare än&quot;innehåller&quot;, och&quot;är lika med&quot; är snabbare än&quot;innehåller något av&quot;.</li><li>Med många kriterier blir AND-operatorer snabbare än en serie OR-operatorer.</li></ul> Leta efter möjligheter att reducera många OR-satser till en enda &quot;motsvarar&quot;-programsats.<br><br>[Klassificeringar](/help/components/classifications/c-classifications.md) kan också hjälpa till att konsolidera många värden till koncisa grupper som du sedan kan skapa segment från. Segmentering i klassificeringsgrupper ger prestandafördelar jämfört med segment som innehåller många OR-satser eller&quot;contains&quot;-kriterier. |
| Visualiseringskomplexitet (segment, mätvärden, filter) | Den typ av visualisering (t.ex. bortfall jämfört med frihandstabell) som läggs till i ett projekt påverkar inte projektets prestanda särskilt mycket. Det är komplexiteten i den visualisering som kommer att öka bearbetningstiden. | Faktorer som gör en visualisering mer komplicerad:<ul><li>Intervall med begärda data</li><li>Antal segment som används, t.ex. segment som används som rader i en frihandstabell</li><li>Användning av komplexa segment</li><li>[Statiskt objekt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.html) rader eller kolumner i frihandstabeller</li><li>Filter som används på rader i frihandstabeller</li><li>Antal mätvärden som ingår, särskilt beräknade mätvärden som använder segment</li></ul> | Om du märker att dina projekt inte läses in så snabbt du vill kan du ersätta vissa segment med eVars och Filter där det är möjligt.<br><br>Om du märker att du använder segment och beräknade värden för datapunkter som är viktiga för din verksamhet bör du förbättra implementeringen för att hämta in dessa datapunkter mer direkt. Om du använder taggar i Adobe Experience Platform- och Adobe-bearbetningsregler kan implementeringsändringarna göras snabbt och enkelt. |
| Rapportsvitens storlek | Mängden data som samlas in i rapportsviten. | - | Kontakta ditt implementeringsteam eller en Adobe-expert för att ta reda på om det finns implementeringsförbättringar som kan göras för att förbättra den övergripande upplevelsen i Adobe Analytics. |
| Samtidiga frågor | Antalet frågor som din organisation begär till Adobe samtidigt. Varje organisation har rätt till minst fem samtidiga frågor. | Om en rapport tar lång tid beror det oftast på att den är i kö tillsammans med andra rapporter. Det innebär att din organisation försöker köra många samtidiga begäranden mot en viss rapportserie. Frågor kan komma från API-begäranden, rapportgränssnitt (Analysis Workspace, Report Builder, osv.), schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapportförfrågningar. | Sprid era förfrågningar och scheman för rapportsviten jämnare under hela dagen. Du kan även ändra dina förfrågningar till lågbelastningstider när det är möjligt. Månadsmorgar, tisdagsmorgon och den första varje månad är de bästa rapporteringstiderna. |

## Tips för att öka produktiviteten i Analysis Workspace

Här är en video om ämnet:

>[!VIDEO](https://video.tv.adobe.com/v/31157/?quality=12)
