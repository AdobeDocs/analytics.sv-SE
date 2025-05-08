---
description: Definitioner av gränssnittselement på sidorna i Klassificeringsregelbyggaren.
title: Klassificeringsregler - definitioner
feature: Classifications
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 0%

---

# Klassificeringsregeldefinitioner (äldre)

Definitioner av gränssnittselement på sidorna i Klassificeringsregelbyggaren.

## Regelsida

På den här sidan visas reglerna i en regeluppsättning.

![](assets/classification_rules_page.png)

**Definitioner**

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Välj Rapportsviter och variabler </p> </td> 
   <td colname="col2"> <p><b>Report Suite</b> </p> <p>Rapportsviterna som regeluppsättningen gäller för. </p> <p><b>Variabel</b> </p> <p>Du kan bara använda en variabel när du skapar en klassificeringsregeluppsättning. Om du vill skapa flera regeluppsättningar för en variabel måste du tillämpa varje regeluppsättning på flera rapportsviter. </p> <p>Obs! Du kan bara använda de variabler du har tillgång till i dina rapportsviter. Variabler visas bara på panelen <span class="wintitle"> Ny regeluppsättning </span> när minst en klassificering har definierats för den variabeln. </p> <p> Du kan skapa klassificeringar för en variabel i <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Rapportsviter </span> &gt; <span class="uicontrol"> Trafik </span> &gt; <span class="uicontrol"> Trafikklassificeringar </span> (eller <span class="uicontrol"> Konvertering </span> &gt; <span class="uicontrol"> Konverteringsklassificeringar </span>). Markera sedan variabeln och klicka på <span class="uicontrol"> Lägg till klassificering </span>. </p> <p>Se <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/traffic-variables/traffic-classifications.html?lang=sv-SE"  > Trafikklassificeringar </a> och <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html?lang=sv-SE"  > Konverteringsklassificeringar </a> i administrationshjälpen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aktivera</span> </p> </td> 
   <td colname="col2"> <p>Validerar och aktiverar en regel. Aktiva regler bearbetas dagligen och klassificeringsuppgifterna undersöks, vanligtvis en månad tillbaka. Reglerna söker automatiskt efter nya värden och överför klassificeringarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Inaktivera</span> </p> </td> 
   <td colname="col2"> <p>Inaktiverar reglerna så att du kan redigera och testa dem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurera rapportsviter och variabler </p> </td> 
   <td colname="col2"> <p>Visar sidan <span class="wintitle"> tillgängliga rapportsviter</span>, där du kan välja en eller flera tillgängliga rapportsviter att använda för alla regeluppsättningar. (Den här sidan visas också när du kör <span class="wintitle"> Klassificeringsregelverktyget</span> första gången.) </p> <p>Den här funktionen är avsedd att minska belastningstiden för rapportsviten om du har hundratals tillgängliga rapportsviter. </p> <p>Rapportsviterna som du väljer här är tillgängliga på regelnivå när du klickar på <span class="uicontrol"> Lägg till sviter </span> när du skapar en regel. </p> <p>Obs! En rapportserie blir bara tillgänglig <span class="term"></span> när minst en klassificering har definierats för variabeln i <span class="wintitle"> Administratörsverktyg </span> för rapportsviten. <p>(Se <span class="term"> Variabel </span> i <a href="/help/components/classifications/crb/classification-rule-set.md"  > Klassificeringsregeluppsättningar </a> för en förklaring av den här förutsättningen.) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regler skriver över befintliga värden </p> </td> 
   <td colname="col2"> <p> (Standardinställning) Skriv alltid över befintliga klassificeringsnycklar, inklusive klassificeringar som överförts via importören (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regler skriver bara över ej avaktiverade värden </p> </td> 
   <td colname="col2"> <p>Fyll bara i tomma celler (ta bort). Befintliga klassificeringar ändras inte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fönstret Lookback </p> </td> 
   <td colname="col2"> <p>När du aktiverar och validerar regler kan du ange om reglerna ska skriva över befintliga klassificeringar för berörda nycklar. (Endast klassificerade nycklar som tidigare har skickats till <span class="keyword"> Adobe Analytics</span> inom den tidsperiod du anger påverkas.) </p> <p>Om du inte anger ett <span class="term">-uppslagsfönster </span> kommer reglerna att synas bakåt ungefär en månad (beroende på den aktuella dagen i månaden). Befintliga klassificeringar skrivs aldrig över om du inte aktiverar det här alternativet. </p> <p><b>Dev Center</b>: Partners kan skapa klassificeringsregler i <span class="wintitle"> Dev Center</span>. Dessa regler distribueras när kunden aktiverar en integrering. I <span class="wintitle"> Dev Center</span> kan partnern med alternativet <span class="uicontrol"> Skriv över sedan </span> ange om kunden kan fastställa överskrivningsvärdet när en integrering aktiveras eller redigeras. </p> <p>Mer information om regelbearbetning finns i <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Hur regler bearbetas</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Lägg till regel </a> </td> 
   <td colname="col2"> <p>Gör att du kan lägga till regler i regeluppsättningen. </p> <p>Obs! Om ett värde matchas två gånger eller mer i en uppsättning regler, används den sista regeln för att klassificera värdet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Utkast</span> </td> 
   <td colname="col2"> Här kan du ange att en regel är i utkastläge. Med utkaststatus kan du testa regeln innan du kör den. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplicera </span> </td> 
   <td colname="col2"> Duplicerar (kopierar) en regeluppsättning så att du kan tillämpa regeluppsättningen på en annan variabel eller på samma variabel i en annan rapportserie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Testregeluppsättning </a> </p> </td> 
   <td colname="col2"> <p>Gör att du kan testa giltigheten för en regeluppsättning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Matchningsvillkor </span> </td> 
   <td colname="col2"> Anger villkoren som du vill använda för regeln. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Klassificeringsåtgärd </span> </td> 
   <td colname="col2"> <p>Anger vilken åtgärd som ska utföras när Matchningsvillkor inträffar. </p> <p>Du kan till exempel ställa in ett kampanjnamn på $2, som identifierar position 2 i en spårningskod som kampanjnamn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>Regelnumret. </p> <p>Mer information finns i <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Hur regler bearbetas</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Välj regeltyp </span> </td> 
   <td colname="col2"> <p>Varje regeluppsättning gäller för en viss variabel. Giltiga val är: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Börjar med </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Slutar med </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Innehåller </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Reguljärt uttryck </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ange matchningsvillkor </span> </td> 
   <td colname="col2"> Textmönstret som du letar efter i en nyckel. Dessa villkor kan vara söktermer, tecken eller reguljära uttryck. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ange klassificering </span> </td> 
   <td colname="col2"> Klassificeringskolumnen som du vill ange om matchningsvillkoren uppfylls. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> till</span> </td> 
   <td colname="col2"> Värdet som du vill ange för den valda klassificeringskolumnen om matchningsvillkoren uppfylls. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter </td> 
   <td colname="col2"> Gör att du kan söka efter regler. </td> 
  </tr> 
 </tbody> 
</table>

## Sidan med reguljära uttryck {#section_C932A5469E774841B2229965A154163C}

Du kan redigera reguljära uttryck på sidan [!UICONTROL Regular Expression].

![](assets/regex_tracking_code.png)

**Definitioner**

| Element | Beskrivning |
|---|---|
| Exempelnyckel | Teststrängen som ska användas. Du kan till exempel skapa en klassificering av specifika tecken i en spårningskod. Du kan matcha vissa tecken, ord eller teckenmönster. |
| Matcha grupper | Visar hur det reguljära uttrycket motsvarar kampanj-ID-tecknen, så att du kan klassificera en position i kampanj-ID:t. |
| Matcha resultat | Visar de delar av en sträng som matchar det reguljära uttrycket. |

Se [Reguljära uttryck i klassificeringsregler](/help/components/classifications/crb/classification-quickstart-rules.md).

## Testsida {#section_EC926F97901C4E65901413F9683AA70A}

På den här sidan kan du testa regler i en uppsättning.

**Definitioner**

| Element | Beskrivning |
|---|---|
| Kör test | När du testar regeluppsättningen kan du använda nycklar från rapporten för att se hur de kommer att påverkas av regeluppsättningen. |
| Filter | Filtrerar värdena på panelen [!UICONTROL Results]. |
