---
description: Med segment kan du identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner. Segmenten är utformade som kodade målgruppsinsikter som ni kan bygga för era specifika behov, och sedan verifiera, redigera och dela med andra teammedlemmar eller använda i andra Adobe-produkter och Analytics-funktioner.
title: Om segment
feature: Segmentation
exl-id: 11d930ca-5d59-4ea5-b6e5-fe3d57be94fd
source-git-commit: ecb30f6eacd3eae72b6af53d40a1eb9b7187488d
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 1%

---

# Om segment

Med segment kan du identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner. Segmenten är utformade som målgruppsinsikter som ni kan bygga för era specifika behov och sedan verifiera, redigera och dela med andra teammedlemmar eller använda i andra Adobe-produkter och Analytics-funktioner.

Segmenten baseras på en [!UICONTROL Visitor], [!UICONTROL Visit]och [!UICONTROL Hit] nivåhierarki med en kapslad behållarmodell. Med de kapslade behållarna kan du definiera besökarattribut och åtgärder baserat på regler mellan och inom behållarna. Analyssegment kan byggas, godkännas, delas, sparas och köras på flera produkter och funktioner i [!DNL Adobe Experience Cloud]. Segment kan genereras från en rapport, byggas in i en kontrollpanelrapport eller bokmärkas för snabb åtkomst.

Du kan skapa och spara segment i segmentbyggaren eller generera segment från en utfallsrapport (i [!UICONTROL Analysis Workspace]). Du kan också använda och utöka fördefinierade segment baserat på specifika regler mellan kapslade behållare, så att du kan filtrera resultaten och tillämpa dem på rapporter. Dessutom kan segment användas tillsammans som [staplade segment](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

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

När du skapar målgruppssegment i Segment Builder definierar du villkor med hjälp av [!UICONTROL AND] och [!UICONTROL OR] operatorer mellan behållare.

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

Den här typen av segment filtrerar datauppsättningar baserat på egenskaper som förenats med [!UICONTROL AND] och [!UICONTROL OR] operatorer.

- Du kan [använda flera segment i en rapport eller ett projekt](/help/components/segmentation/segmentation-workflow/seg-workflow.md).
- Segmenten är universella för alla rapportsviter.
- The [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-workflow.md) gör det enklare att skapa segment.
- The [Segmenthanteraren](/help/components/segmentation/segmentation-workflow/seg-workflow.md) gör att du kan konfigurera [arbetsflöden](/help/components/segmentation/segmentation-workflow/seg-workflow.md) med segmentdelning, taggning, verifiering och godkännandefunktioner.
- Du kan [taggsegment](/help/components/segmentation/segmentation-workflow/seg-workflow.md) om du vill ordna och söka senare i stället för att använda mappar.
- Du kan [Sekventiella segment](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
- The [!UICONTROL Page View] behållaren är nu [!UICONTROL Hit] behållare som anger att den här behållaren segmenterar alla typer av data och inte bara sidvyer. Till exempel tas alla anrop för länkspårning och trackAction-anrop från de mobila SDK:erna med eller utan av träffbehållaren.

## Segmentering i Analysis Workspace

Analysis Workspace innehåller följande funktioner:

- Du kan [jämföra segment](../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md).
- Använd [segment som dimensioner](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) i en jämförelse.
- Använd segment i [fallanalys](../../analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md).

## Segment som tillhandahålls av Adobe

Komponentspåret till vänster på skärmen visar segment som har skapats av dig och ditt företag samt segment Adobe som ingår i paketet. När du klickar **[!UICONTROL Show all]**, visas dessa segment oftast längst ned i listan och identifieras av Adobe-logotypen till höger.

## Sekventiella segment {#sequential}

Med hjälp av sekventiella segment kan du identifiera besökare baserat på navigering och sidvisning på webbplatsen, vilket ger ett segment med definierade åtgärder och interaktioner. Sekventiella segment hjälper er att identifiera vad en besökare gillar och vad en besökare undviker. När du skapar sekventiella segment [!UICONTROL THEN] -operatorn används för att definiera och beställa besöksnavigering.

<!--![](assets/sequential_seg.png)-->

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

Ett sekventiellt segment filtrerar datauppsättningar baserat på användaråtgärder med [!UICONTROL THEN] -operator.

## Video om hur man segmenterar {#segment-video}

Den här videon ger en kort översikt över vilka segmentbehållare som är och hur de används:

>[!VIDEO](https://video.tv.adobe.com/v/25401/?quality=12&learn=on)


## Öppna segmenteringsverktygen {#access}

+++ **Hur når jag segmentbyggaren?**

Du kommer åt segmentbyggaren genom att:

- Visa en befintlig rapport och klicka på segmentikonen  ![Segmentikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) i den vänstra navigeringen. Klicka på i segmentlisten som visas **[!UICONTROL Add]**, eller

- Överst i segmenthanteraren klickar du på **[!UICONTROL + Add]**.  ![Knappen Lägg till](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg)

  eller

- Klicka på en befintlig segmenttitel i segmenthanteraren för att redigera segmentet i segmentbyggaren.

+++

+++ **Hur når jag segmenthanteraren?**

Öppna segmenthanteraren genom att:

- Går till  **[!UICONTROL Analytics]** > **[!UICONTROL Components]** i den övre navigeringen. Klicka sedan på **[!UICONTROL Segments]**, eller

- Visa en befintlig rapport och klicka på segmentikonen  ![Segmentikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) i den vänstra navigeringen. Klicka sedan på **[!UICONTROL Manage]**, eller

- Tryck på snedstreckstangenten &#39;/&#39; var som helst i gränssnittet och sök efter segmenthanteraren.

+++

## Behörigheter {#section_648DFA3A882146C485A84ED014EEC707}

+++ **Vilka rättigheter och behörigheter behöver jag för att använda, skapa och hantera segment?**

Som standard kan alla användare skapa och redigera personliga segment. Administratörer kan dock bestämma vilka som ska ha [behörighet att skapa segment](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html) och kan tilldela dem till specifika grupper. Dessa segment kan delas direkt med andra Analytics-användare.

Administratörer kan redigera alla segment och dela segment med grupper och med alla i organisationen. [Mer...](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **Kan jag se alla segment i mitt företag?**

Ja, administratörer kan se alla segment i [!DNL Analysis Workspace] användargränssnitt.

Report Builder visar segment som du äger och segment som delas med dig.

+++

+++ **Kan jag hantera alla analyssegment i segmenthanteraren?**

Ja, alla segment kan hanteras i segmenthanteraren. Segmenthanteraren visar segment som är synliga för ägaren (den användare som skapade segmentet), delade användare och adminanvändare. Segmentväljaren visar segment som ägs av och delas med användaren.

Administratörer kan se alla segment i Analysis Workspace användargränssnitt.

I Report Builder visas endast segment som du har skapat eller segment som har delats specifikt med dig.

+++

+++ **Varför kan jag inte ta bort det här segmentet?**

Om segmentet var [publicerade i Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-workflow.md)kan du inte ta bort eller redigera den. Du kan dock kopiera den och redigera den kopierade versionen.

+++
