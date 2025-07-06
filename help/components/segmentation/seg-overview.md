---
description: Förstå hur segment gör att ni kan identifiera undergrupper av besökare utifrån egenskaper eller webbplatsinteraktioner.
title: Om segment
feature: Segmentation
exl-id: 11d930ca-5d59-4ea5-b6e5-fe3d57be94fd
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 1%

---

# Om segment

Med segment kan du identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner. Segmenten är utformade som målgruppsinsikter som ni kan bygga för just era behov och sedan verifiera, redigera och dela med andra teammedlemmar eller använda i andra Adobe-produkter och Analytics-funktioner.

Segmenten baseras på en [!UICONTROL Visitor]-, [!UICONTROL Visit]- och [!UICONTROL Hit]-nivåhierarki som använder en kapslad behållarmodell. Med de kapslade behållarna kan du definiera besökarattribut och åtgärder baserat på regler mellan och inom behållarna. Analyssegment kan skapas, godkännas, delas, sparas och köras för flera produkter och funktioner i [!DNL Adobe Experience Cloud]. Segment kan genereras från en rapport, byggas in i en kontrollpanelrapport eller bokmärkas för snabb åtkomst.

Du kan skapa och spara segment i segmentverktyget eller generera segment från en utfallsrapport (i [!UICONTROL Analysis Workspace]). Du kan också använda och utöka fördefinierade segment baserat på specifika regler mellan kapslade behållare, så att du kan filtrera resultaten och tillämpa dem på rapporter. Dessutom kan segment användas tillsammans som [staplade segment](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

Segment identifierar

- besökarna (land, kön, kafé),
- vilka enheter och tjänster de använder (webbläsare, sökmotor, mobil enhet),
- där de navigerar från (sökmotor, föregående avslutningssida, naturlig sökning),
- och mycket annat.

<!--![](assets/seg.png)-->

Segment kan baseras på följande värden:

- Besökare baserat på attribut: webbläsartyp, enhet, antal besök, land, kön.
- Besökare baserade på interaktioner: kampanjer, sökord, sökmotor.
- Besökare baserade på utgångar och tävlingsbidrag: besökare från Facebook, en definierad landningssida, hänvisande domän.
- Besökare baserade på anpassade variabler: formulärfält, definierade kategorier, kund-ID.

När du skapar målgruppssegment i segmentverktyget definierar du villkor med hjälp av operatorerna [!UICONTROL AND] och [!UICONTROL OR] mellan behållare.

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">OCH</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">ELLER</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>
</table>

<!--![](assets/standard_segment_containers.png)-->

Den här typen av segment filtrerar datauppsättningar baserat på egenskaper som förenats med operatorerna [!UICONTROL AND] och [!UICONTROL OR].

- Du kan [använda flera segment för en rapport eller ett projekt](/help/components/segmentation/segmentation-workflow/t-seg-apply.md).
- Segmenten är universella för alla rapportsviter.
- [Segmentverktyget](/help/components/segmentation/segmentation-workflow/seg-build.md) förenklar skapandet av segment.
- Med [segmenthanteraren](/help/components/segmentation/segmentation-workflow/seg-manage.md) kan du konfigurera [arbetsflöden](/help/components/segmentation/segmentation-workflow/seg-workflow.md) med segmentdelning, taggning, verifiering och godkännandefunktioner.
- Du kan [tagga segment](/help/components/segmentation/segmentation-workflow/seg-tag.md) om du vill ordna och söka senare i stället för att använda mappar.
- Du kan skapa [sekventiella segment](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
- Behållaren [!UICONTROL Page View] är nu [!UICONTROL Hit] som indikerar att den här behållaren segmenterar alla typer av data och inte bara sidvyer. Till exempel tas alla anrop för länkspårning och spårning av åtgärdsanrop från mobila SDK:er med eller utan av träffbehållaren.

## Segmentering i Analysis Workspace

Analysis Workspace innehåller följande funktioner:

- Du kan [jämföra segment](../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md).
- Använd segment som dimensioner i frihandsritabellvisualiseringar.
- Använd segment i [utfallsanalys](../../analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md).

## Segment som tillhandahålls av Adobe

I den vänstra delen av komponenten visas segment som har skapats av dig, ditt företag och Adobe-segment som ingår i paketet. När du klickar på **[!UICONTROL Show all]** visas dessa segment vanligtvis längst ned i listan och identifieras av ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg).

## Sekventiella segment {#sequential}

Med hjälp av sekventiella segment kan du identifiera besökare baserat på navigering och sidvisning på webbplatsen, vilket ger ett segment med definierade åtgärder och interaktioner. Sekventiella segment hjälper er att identifiera vad en besökare gillar och vad en besökare undviker. När du skapar sekventiella segment används operatorn [!UICONTROL THEN] för att definiera och beställa besöksnavigering.

| Besök en | Besök två | Besök tre |
|---|---|---|
| Vid det första besöket gick besökaren till huvudlandningssidan A, exkluderade kampanjsidan B och tittade sedan på produktsidan C. | Vid det andra besöket gick besökaren åter till huvudlandningssidan A, exkluderade kampanjsidan B, gick tillbaka till produktsidan C och sedan till en ny sida D. | Vid det tredje besöket gick besökaren in på och följde samma väg som vid det första och andra besöket och uteslöt sedan sidan F för att gå direkt till produktsidan G. |

Sekventiella segment kan baseras på följande träffvärden:

- Besökare baserade på sekvenser av sidträffar: sidvisningar vid ett enda besök, sidvisningar vid olika besök, besök där sidvisningar utesluts.
- Besökare baserat på tiden mellan och efter sidvisningar: efter en tidsgräns, mellan träffar, efter en händelse.

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">SEDAN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>OCH</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">SEDAN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>ELLER</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Träffar</td>
</tr>
</tr>
</table>

<!--![](assets/sequential_segmentation_containers_view.png)-->

Ett sekventiellt segment filtrerar datauppsättningar baserat på användaråtgärder med operatorn [!UICONTROL THEN].

## Video om hur man segmenterar {#segment-video}

Den här videon ger en kort översikt över vilka segmentbehållare som är och hur de används.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentbehållare](https://video.tv.adobe.com/v/25401?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Behörigheter {#permissions}

+++ **Vilka rättigheter och behörigheter behöver jag för att använda, skapa och hantera segment?**

Som standard kan alla användare skapa och redigera personliga segment. Administratörer kan dock bestämma vem som ska ha [behörighet att skapa segment](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=sv-SE) och kan tilldela dem till specifika grupper. Dessa segment kan delas direkt med andra Analytics-användare.

Administratörer kan redigera alla segment och dela segment med grupper och med alla i organisationen. [Segmenträttigheter efter roll](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **Kan jag se alla segment i mitt företag?**

Ja, administratörer kan se alla segment i användargränssnittet för [!DNL Analysis Workspace].

Report Builder visar segment som du äger och segment som delas med dig.

+++

+++ **Kan jag hantera alla analyssegment i segmenthanteraren?**

Ja, alla segment kan hanteras i segmenthanteraren. Segmenthanteraren visar segment som är synliga för ägaren (den användare som skapade segmentet), delade användare och adminanvändare. Segmentväljaren visar segment som ägs av och delas med användaren.

Administratörer kan se alla segment i Analysis Workspace användargränssnitt.

Report Builder visar endast segment som skapats av dig eller segment som har delats specifikt med dig.

+++

+++ **Varför kan jag inte ta bort ett segment?**

Om segmentet [publicerades i Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-workflow.md) kan du inte ta bort eller redigera segmentet. Du kan dock kopiera segmentet och redigera den kopierade versionen.

+++
