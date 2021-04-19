---
description: Om du är van vid att arbeta med Segment Builder i Ad Hoc Analysis, förklarar denna Frågor och svar vad som händer med befintliga segment och mappar och vilka åtgärder du måste vidta.
keywords: segmentering;segment
title: Övergångshandbok för Ad Hoc Analysis
feature: Segmentering
uuid: d409d71a-f8d9-42a2-add2-37d426cd40d1
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 1%

---


# Övergångshandbok för Ad Hoc Analysis

Om du är van vid att arbeta med Segment Builder i Ad Hoc Analysis, förklarar denna Frågor och svar vad som händer med befintliga segment och mappar och vilka åtgärder du måste vidta.

## Funktioner {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Segmenten är universella för alla rapportsviter. Tidigare var segment specifika för rapporteringsprogram.
* Ad Hoc Analysis innehåller uppdateringar av segmentbyggaren och en fullständig uppdatering av segmenthanteraren.
* Nu kan du tagga segment för att ordna och söka senare i stället för att använda mappar. Tidigare använde du mappar i [!DNL Ad Hoc Analysis] för att ordna dina segment.

## Vad hände med mina befintliga segment? {#section_76CF47142D1A4FB6A0718AD9073049FE}

Befintliga segment fortsätter att fungera som tidigare. Alla rapporter som använder dessa segment fortsätter att fungera korrekt.

De flesta tidigare fördefinierade och suite-segment migreras som segmentmallar till segmentbyggaren. Segmentmallar används för att snabbt skapa anpassade segment med gemensamma målgrupper. Segmentmallar kan inte användas direkt i en rapport, men de kan enkelt sparas i ett anpassat segment.

Segmentmallar markeras med en speciell ikon i Segment Builder.

## Vad hände med mina befintliga segmentmappar? {#section_FB04DCF775694E69B761DCA53F301C30}

I stället för ad hoc-analysmappar använder segmenthanteraren taggar. Dina mappnamn konverteras automatiskt till taggar och dessa taggar används i respektive segment.

## Vad hände med schemalagda rapporter som har segment tillämpade? {#section_81D1B215533C46E99E17BAE7A3376FDF}

Schemalagda rapporter fortsätter att fungera korrekt med de segment som du har definierat.

När du tar bort ett segment fortsätter schemalagda rapporter och instrumentpaneler som använder det här segmentet att fungera som vanligt, dvs. segmentet eller instrumentpanelen fortsätter att använda det borttagna segmentet.

## Vad är en träbehållare? Skiljer det sig från en sidvisningsbehållare? {#section_65BBE60A836C4001938830DDA15DC256}

Sidvisningsbehållaren har bytt namn till Träff-behållaren för att ange att den här behållaren segmenterar alla typer av data och inte bara sidvyer. Till exempel tas alla anrop för länkspårning och trackAction-anrop från de mobila SDK:erna med eller utan av träffbehållaren.

Observera att det inte fanns någon förändring av hur behållaren fungerar, utan att namnet bara ändrades.

## Vilka rättigheter och behörigheter behöver jag för att använda, skapa och hantera segment? {#section_648DFA3A882146C485A84ED014EEC707}

Alla användare kan skapa och redigera personliga segment. Dessa segment kan delas direkt med andra Analytics-användare. Ad Hoc Analysis-användare kan se de segment som de har skapat och de som delas direkt med användaren.

På webbkonsolen för enhetlig segmentering kan administratörer redigera alla segment och dela segment med grupper och med alla i organisationen.

## Kan jag se alla segment i mitt företag? {#section_AC2D328C7410419E80C7C17971CD95B3}

Alla ad hoc-analyssegment som du äger och segment som delas med dig visas.

## Kan jag hantera alla analyssegment i segmenthanteraren? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

Ad hoc-analyser visar endast segment som skapats av dig eller segment som delats specifikt med dig. Endast för ad hoc-analyser kan du använda segmenthanteraren (Organizer Segments) för att hantera ad hoc-analyssegment. Använd segmenthanteraren i enhetlig segmentering för att hantera alla Analytics-segment.

## Vad ska jag göra med duplicerade segment som har samma namn men som kan ha olika definitioner? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Nu när segment fungerar i flera rapportsviter kan det finnas flera segment med samma namn. Vi rekommenderar att du antingen

* Byt namn på segment som har samma namn men olika definitioner, eller
* Ta bort segment som inte längre behövs.

## Hur rekommenderar Adobe att jag rensar upp segment? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Tagga alla segment med äldre tagg.
* Granska de segment du har.
* Lägg till dem i segmentbiblioteket där det är tillämpligt.
* Godkänn kanoniska segment.

## Varför kan jag inte ta bort det här segmentet? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Om segmentet publicerades i Experience Cloud kan du inte ta bort eller redigera det. Du kan dock kopiera den och redigera den kopierade versionen.

## Mer information om vad som händer med dina befintliga segment {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmentkategori </th> 
   <th colname="col2" class="entry"> Vad händer med de här segmenten? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Favoritsegment i Ad Hoc Analysis </td> 
   <td colname="col2">Dessa Ad Hoc Analysis-segment visas som vanliga segment i Adobe Analytics. <p>De ska inte blandas ihop med favoritfunktionen i segmenthanteraren som gör att du kan markera segment som favoriter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Förkonfigurerade segment i Ad Hoc Analysis: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Besök på en sida </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Besök från mobila enheter </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Besök från naturlig sökning </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Besök från betald sökning </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Besök med Visitor ID Cookie </li> 
    </ul> </td> 
   <td colname="col2"> <p>Dessa segment migreras som segmentmallar till segmentbyggaren. </p> <p>Befintliga rapporter som använder dessa segment fortsätter att fungera korrekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Experience Cloud (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Icke-köpare </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Inköpare </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Första gången du besöker </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Besök från sociala webbplatser </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Besök under mer än 10 minuter* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Besök med 5+ tidigare besök* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Besök från Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> De flesta av dessa segment (utom de som är markerade med en asterisk *) migreras över som segmentmallar till segmentbyggaren. Dessutom har flera nya segmentmallar lagts till. </p> <p>Befintliga rapporter som använder dessa segment fortsätter att fungera korrekt. </p> </td> 
  </tr> 
 </tbody> 
</table>

