---
description: Ad Hoc Analysis kan integreras med segmenteringsmiljön i Analytics så att ni kan skapa, dela, hantera och tillämpa besökarsegment för alla Adobe-produkter. Ad Hoc Analysis har ett Java-baserat användargränssnitt för segmentbyggaren och segmenthanteraren som är identiskt med de webbaserade verktyg som används av andra analysverktyg, som matchar serveranrop och ger samma funktioner och funktionalitet från en Java-baserad konsol.
title: Skapa segment
topic: Ad hoc analysis
uuid: e14fb777-900a-4700-8dc7-56a45c678d29
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Skapa segment

Ad Hoc Analysis kan integreras med segmenteringsmiljön i Analytics så att ni kan skapa, dela, hantera och tillämpa besökarsegment för alla Adobe-produkter. Ad Hoc Analysis har ett Java-baserat användargränssnitt för segmentbyggaren och segmenthanteraren som är identiskt med de webbaserade verktyg som används av andra analysverktyg, som matchar serveranrop och ger samma funktioner och funktionalitet från en Java-baserad konsol.

Ad hoc-analys innehåller välbekanta funktioner för att bygga segment, plus nya funktionsuppgraderingar som [Segment Manager](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_manage.html) som används för att skapa ett [arbetsflöde](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_workflow.html)för segmenthantering. Som alltid kan du skapa och spara segment i [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html) eller [generera segment från en utfallsrapport](https://marketing.adobe.com/resources/help/en_US/analytics/segment/t_seg_fallout.html) från ad hoc-analyskonsolen och sedan spara de nya eller utökade segmenten i målgruppsbiblioteket för allmän åtkomst och användning. ![](assets/seg__overview_ad_hoc.png)

## Enhetlig segmentering i ad hoc-analys {#section_5FA03A06DE054448AD519CE30C39E294}

Information och instruktioner om hur du skapar och hanterar segment i den enhetliga segmenteringsmiljön, inklusive ad hoc-analysfunktioner, finns i dokumentationen för [enhetlig segmentering](https://marketing.adobe.com/resources/help/en_US/analytics/segment/index.html) .

* [Nya funktioner](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_BD58629D1A9346BF879E229FA6BEC7A2)
* [Ändringar av segmentdefinition](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_definition.html)
* [Vad hände med mina befintliga segment?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_76CF47142D1A4FB6A0718AD9073049FE)
* [Vad hände med mina befintliga segmentmappar?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_FB04DCF775694E69B761DCA53F301C30)
* [Kan jag hantera alla Analytics-segment i segmenthanteraren?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_AF5EDD72C74A4739BD40C4AF125CE489)
* [Vad är en träbehållare? Skiljer det sig från en sidvisningsbehållare?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_65BBE60A836C4001938830DDA15DC256)
* [Vilka rättigheter och behörigheter behöver jag för att använda, skapa och hantera segment?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_648DFA3A882146C485A84ED014EEC707)
* [Vad ska jag göra med duplicerade segment som har ...](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_E2C3A1B4B4274D1B86CAA9C0359D049C)
* [Hur rekommenderar Adobe att jag rensar upp segment?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_3AC2D265F9084557A24C6FB39DC6EE49)
* [Varför kan jag inte ta bort det här segmentet?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_0FEB6711031A4ABCA915CDA745ECF38D)
* [Mer information om vad som händer med befintliga segment](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_83ACAB256F394DCD8B424D8920BDD853)

## Funktioner {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* [Segmenten](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_overview.html) är universella för alla rapportsviter. Tidigare var segment specifika för rapporteringsprogram.
* Med [segmenthanteraren](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_manage.html) kan du skapa [arbetsflöden](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_workflow.html) med segmentdelning, taggning, verifiering och godkännandefunktioner.

* Segmentbyggaren [](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build_ui.html) har uppdaterats för att förenkla skapandet av segment.
* Du kan [tagga segment](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_tag.html) för att ordna och söka senare i stället för att använda mappar. Tidigare använde du mappar (i [!DNL ad hoc analysis]) för att ordna dina segment.

* Du kan skapa [sekventiella segment](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_sequential.html) utanför ad hoc-analysen.
* 

>[!NOTE]
>
>I Ad hoc-analys kan du inte lägga till datumintervall till segment. Den här funktionen är tillgänglig på Analysis Workspace. Du kan inte heller använda Endast före/Endast efter-sekvenser i Ad Hoc-analys.

## Vad hände med mina befintliga segment? {#section_76CF47142D1A4FB6A0718AD9073049FE}

Dina befintliga segment kommer att fortsätta fungera som de gjorde innan segmenteringen i Analytics introducerades. Alla rapporter som använder dessa segment fortsätter att fungera korrekt.

De flesta tidigare fördefinierade och suite-segment migreras som [segmentmallar](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_templates.html) till segmentbyggaren. Segmentmallar används för att snabbt skapa anpassade segment med gemensamma målgrupper. Segmentmallar kan inte användas direkt i en rapport, men de kan enkelt sparas i ett anpassat segment.

## Vad hände med mina befintliga segmentmappar? {#section_FB04DCF775694E69B761DCA53F301C30}

I stället för (Ad hoc-analys) använder segmenthanteraren [taggar](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_tag.html). Dina mappnamn konverteras automatiskt till taggar och dessa taggar används i respektive segment.

## Kan jag hantera alla analyssegment i segmenthanteraren? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

I segmenthanteraren för ad hoc-analys kan du bara se de segment som tillhör dig (de segment som du har skapat) och de segment som delas med dig.

## Vad är en träbehållare? Skiljer det sig från en sidvisningsbehållare? {#section_65BBE60A836C4001938830DDA15DC256}

Sidvisningsbehållaren har bytt namn till Träff-behållaren för att ange att den här behållaren segmenterar alla typer av data och inte bara sidvyer. Till exempel tas alla anrop för länkspårning och [!DNL trackAction] anrop från mobila SDK:er med eller utesluts av träffbehållaren.

Observera att det inte fanns någon förändring av hur behållaren fungerar, utan att namnet bara ändrades.

## Vilka rättigheter och behörigheter behöver jag för att använda, skapa och hantera segment? {#section_648DFA3A882146C485A84ED014EEC707}

Alla användare kan skapa och redigera personliga segment. Dessa segment kan delas direkt med andra Analytics-användare.

Administratörer kan redigera alla segment och [dela segment](https://marketing.adobe.com/resources/help/en_US/analytics/segment/t_seg_share.html) med grupper och [ange behörigheter](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_rights.html) för att komma åt segment för organisationen.

## Vad ska jag göra med duplicerade segment som har samma namn men som kan ha olika definitioner? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Eftersom segment fungerar i flera rapportsviter kan det finnas flera segment med samma namn. Vi rekommenderar att du antingen

* Byt namn på segment som har samma namn men olika definitioner, eller
* Ta bort segment som inte längre behövs.

## Hur rekommenderar Adobe att jag rensar upp segment? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Tagga alla segment med äldre tagg.
* Granska de segment du har.
* Lägg till dem i segmentbiblioteket där det är tillämpligt.
* Godkänn kanoniska segment.
* Tagga segment enligt bästa praxis.

## Varför kan jag inte ta bort det här segmentet? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Om segmentet har [publicerats i Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html)kan du inte ta bort eller redigera det. Du kan dock kopiera den och redigera den kopierade versionen.

## Mer information om vad som händer med befintliga segment {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmentkategori </th> 
   <th colname="col2" class="entry"> Vad händer med de här segmenten? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Favoritsegment (ad hoc-analys) </td> 
   <td colname="col2">Dessa Ad hoc-analyssegment visas som vanliga segment i Adobe Analytics. <p>De ska inte blandas ihop med favoritfunktionen i segmenthanteraren som gör att du kan markera segment som favoriter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Förkonfigurerade segment: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Besök på en sida </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Besök från mobila enheter </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Besök från naturlig sökning </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Besök från betald sökning </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Besök med Visitor ID Cookie </li> 
    </ul> </td> 
   <td colname="col2"> <p>Dessa segment migreras som <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_templates.html"  > segmentmallar</a> till segmentbyggaren. </p> <p>Befintliga rapporter som använder dessa segment fortsätter att fungera korrekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Experience Cloud-segment (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Icke-köpare </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Inköpare </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Första gången du besöker </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Besök från sociala webbplatser </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Besök under mer än 10 minuter* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Besök med 5+ tidigare besök* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Besök från Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> De flesta av dessa segment (utom de som är markerade med en asterisk *) migreras över som <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_templates.html"  > segmentmallar</a> till segmentbyggaren. Dessutom har flera nya segmentmallar lagts till. </p> <p>Befintliga rapporter som använder dessa segment fortsätter att fungera korrekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Administratörssegment <p>(kallas även"globala" segment) </p> </td> 
   <td colname="col2"> <p> <b>Administrationssegment</b> migreras till det nya segmentgränssnittet och visas som segment som delas med alla. </p> <p>Ägaren till dessa segment anges till den administratör som har det äldsta kontot i inloggningsföretagets lista över adminanvändare, men alla administratörer kan ta bort, redigera och dela dessa segment. </p> <p>Segmenthanteringsgränssnittet i Admin Console där administratörer skapade och hanterade dessa globala segment är inte längre tillgängligt. Administratörer bör nu använda det nya segmentverktyget för att skapa segment och dela dem med lämpliga grupper eller individer eller med alla. </p> </td> 
  </tr> 
 </tbody> 
</table>

