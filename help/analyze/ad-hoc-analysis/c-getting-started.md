---
description: Kom igång med Ad hoc-analys.
title: Komma igång
uuid: 6a698e18-4e62-405e-b020-b973c9c4008b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Kom igång med ad hoc-analys{#concept_48936BA28FAE42DB81F1B2CD4726EB17}

>[!Iviktig]
>Den 6 augusti 2018 meddelade Adobe att man hade för avsikt att göra en Ad hoc-analys i slutet av livscykeln. Ett slutdatum delas så snart det är tillgängligt. Mer information, inklusive vilka versioner av Java som kommer att vara kompatibla under perioden, finns på [https://adobe.ly/discoverworkspace](https://adobe.ly/discoverworkspace).

Du kan utföra ögonblicklig, avancerad analys av webbplatsaktiviteter. Du kan visa flera rapporter samtidigt och tillämpa segment över flera dimensioner. Ni kan analysera data från både mikro- och makroperspektiv för att se hur de påverkar era viktiga affärsvärden.

Med de här funktionerna kan du besvara frågor om webbplatstrafik, demografi för besökare, intäkter och produktrörelser. Du kan sedan filtrera, sortera och segmentera data för att hitta svar på exakta frågor. Resultaten returneras nästan direkt, vilket gör att du snabbt kan analysera effekterna av en kombination av faktorer.

<table id="table_C9C0444687FC418580F996E1D2ADB61A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komma igång-aktiviteter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1. Logga in på Adobe <span class="keyword"> Analytics</span>. </p> </td> 
   <td colname="col2"> <p>Gå till <a href="https://marketing.adobe.com"  > marketing.adobe.com </a>och logga in med inloggningsuppgifterna för Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2. Starta ad hoc-analys. </p> </td> 
   <td colname="col2">Klicka på <span class="uicontrol"> Adobe Analytics</span> &gt; <span class="uicontrol"> Tools</span> &gt; <span class="uicontrol"> Ad Hoc Analysis</span>och klicka sedan på <span class="uicontrol"> Launch Ad Hoc Analysis</span> . <p> <p>Obs! Om du inte ser knappen <b>Starta ad hoc-analys</b> på den här sidan ska du vara säker på att administratören har lagt till dig i gruppen <i>Ad Hoc Analysis License User</i> i Admin Tools. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3. Skapa ett projekt. </p> </td> 
   <td colname="col2"> <p>Välj en rapportsvit på startsidan och klicka sedan på <span class="uicontrol"> Skapa projekt</span>. </p> <p>Se <a href="/help/analyze/ad-hoc-analysis/c-getting-started.md"   > Projekt och arbetsytor</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4. Öppna en rapport. </p> </td> 
   <td colname="col2"> <p>Sök efter en rapport med standardrapportmenyn i Cloud. Du kan också välja en mall. </p> <p>Se <a href="/help/analyze/ad-hoc-analysis/c-getting-started.md"   > Rapportmallar</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5. Konfigurera rapporten. </p> </td> 
   <td colname="col2"> <p>Konfigurera rapporter genom att utföra uppgifter som: </p> 
    <ul id="ul_0D2E8C614F2A4899A376BCEECEA374C6"> 
     <li id="li_FA925D52A8FD4DFAB0C88B797B24E72B"> Skapa segment som fördjupar sig i data </li> 
     <li id="li_5E91632551D2473BA8BD0637CDC1A9F6"> Lägga till mått, dimensioner och segment i <a href="/help/analyze/ad-hoc-analysis/c-tablebuilder.md"   > tabellverktyget</a> </li> 
     <li id="li_019316C9A94B4A8C8A77D07C04E50278">Konfigurera <a href="/help/analyze/ad-hoc-analysis/c-dates.md"   > datumintervall</a> </li> 
     <li id="li_2B33B325D5EE420AB412B73AD1D231C5"> <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > Leverans av</a> planeringsrapport </li> 
    </ul> <p>Sök i det här hjälpsystemet efter den hjälp du behöver. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Systemrekommendationer {#concept_6691331B45174290BD9B839806A9B52D}

Även om rapporter fungerar som de ska i de flesta webbläsare så fungerar de bäst i system som uppfyller vissa rekommendationer.

<!-- 

c_sys_reqs.xml

 -->

> [!NOTE] Från och med juli 2018 kommer Ad Hoc Analysis endast att ha stöd för Java 8 eller senare. Om du väljer att köra Ad Hoc Analysis på Java 7 efter Maintenance Release från juli 2018 kommer Adobe inte längre att stödja implementeringen av Ad Hoc Analysis.

* Grafikkort med stöd för OpenGL 2.0
* Cookies: Obligatoriskt
* Operativsystem: Windows och Mac OS.
* Macromedia Flash Player: version 6 eller senare
* Bildskärmsupplösning: 800x600 (1 024 x 768 rekommenderas)
* Färgdjup: 16 bitar eller mer
* JavaScript: Aktiverad
* Java-version: Java 1.7 eller senare (se anm. ovan)

   Om du inte har rätt version av Java installerad installeras den åt dig. Om du har en icke-kompatibel version av Java installerad hämtas och du uppmanas att installera uppdateringarna.

## Instruktioner för Java-uppgradering {#section_E4C0C6492FF24636A0FF71A59331111D}

Från och med juli 2018 kommer Ad Hoc Analysis endast att ha stöd för Java 8 eller senare. Om du väljer att köra Ad Hoc Analysis på Java 7 efter Maintenance Release från juli 2018 kommer Adobe inte längre att stödja implementeringen av Ad Hoc Analysis.

Våra .jar-filer är signerade med en säker 256-bitarskryptering som inte stöds av Java-versioner som är mindre än 1.7.0_76. Detta 256-bitars certifikat ger dig bättre säkerhet.

Om du fortfarande har Java 7 installerat måste du uppgradera före underhållsversionen från juli 2018. Så här:

* Om du får installera program på datorn:

   1. Gå till https://www.java.com.
   1. Klicka på **[!UICONTROL Free Java Download]**.
   1. Klicka på **[!UICONTROL Agree and Start Free Download]**.
   1. Installera den senaste Java-versionen som är specifik för ditt operativsystem.

* Om du **inte** får installera program på datorn:

   1. Kontakta IT-avdelningen för att få den senaste versionen av Java installerad.

## Starta ad hoc-analys {#concept_B1CE3C1E6D1A4311B9835BEB69812E55}

<!-- 

c_login.xml

 -->

Du kan logga in från [!DNL Experience Cloud] eller från en URL-adress. Om du loggar in från Rapporter och Analytics loggas du in automatiskt. Du behöver bara logga in med en URL om du kommer åt ad hoc-analysens URL från en annan plats, till exempel en länk eller från en favoritmeny.

## Logga in från Experience Cloud {#task_128ED319F3AE49ED886EA3DFA8D0987F}

Steg som beskriver hur du loggar in från [!DNL Experience Cloud].

<!-- 

t_login_suite.xml

 -->

1. Navigera till i en webbläsare [!DNL marketing.adobe.com].
1. Skriv ditt företagsnamn, ditt användarnamn och ditt lösenord. Klicka sedan på **[!UICONTROL Sign In]**.
1. Klicka på **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Ad Hoc Analysis]**.

   Om du inte ser knappen **Starta ad hoc-analys** på den här sidan ska du vara säker på att administratören har lagt till dig i gruppen *Ad Hoc Analysis License User* i Admin Tools.
1. Klicka på **[!UICONTROL Launch Ad Hoc Analysis]**.
1. Spara [!DNL discover.jnlp] filen lokalt.

   Du kan köra den här sparade filen när du vill starta ad hoc-analys.

## Projekt och arbetsytor {#concept_FAE346335B0347A192C6C806C775D72B}

Ett projekt definierar den uppsättning data som importeras, inklusive en rapportserie och ett datumintervall. Ett projekt består av ett obegränsat antal rapporter med alla mätvärden, inställningar, dimensioner och segment. Du kan påbörja ett nytt projekt, läsa in ett sparat projekt eller läsa in det projekt som sparas automatiskt.

<!-- 

c_projects.xml

 -->

Du grupperar rapporter i en *arbetsyta*. Ett projekt kan innehålla flera arbetsytor och en arbetsyta kan innehålla flera rapporter. Förhållandet mellan dessa objekt tolkas bäst som ett kapslat:

![](assets/project_workspace.png)

Du kan bara öppna ett projekt i taget. Du kan dock öppna flera arbetsytor i ett projekt. I varje arbetsyta kan du ha flera rapporter öppna.

Standarddatumintervallet för ett nytt projekt är [!UICONTROL Last 90 Days].

## Starta ett projekt {#task_918A4539134E4E62B00486DCB8D3D403}

Steg som beskriver hur du startar ett projekt.

<!-- 

t_project_start.xml

 -->

1. Logga in.
1. Öppna ett sparat projekt eller klicka på **[!UICONTROL Create Project]**.
1. Sök efter en rapport eller välj en mall.

## Öppna en nyligen sparad arbetsyta {#task_DE4A54180BC24E9DAEC98E2171DC6B40}

Steg som beskriver hur du öppnar nyligen sparade arbetsytor.

<!-- 

t_recent_workspace.xml

 -->

1. Klicka på **[!UICONTROL File]** > **[!UICONTROL Recent Workspace]**.

   Du kan öppna upp till fem senaste arbetsytor. Senaste arbetsytor är inte tillgängliga när du har avslutat sessionen.

## Dela projekt {#task_5911780D90164F3A8A677C8BC719750D}

Delade projekt är tillgängliga för alla Ad hoc-analysanvändare i företaget.

<!-- 

t_share_projects.xml

 -->

1. Gå till **[!UICONTROL File]** > **[!UICONTROL Save As]**.
1. Välj **[!UICONTROL Shared Projects]** i **[!UICONTROL Save in:]** listrutan.

   ![](assets/shared_projects.png)

1. Klicka **[!UICONTROL Save]** för att spara projektet.

   Delade projekt kan öppnas via **[!UICONTROL File]** > **[!UICONTROL Open]** > **[!UICONTROL Shared Projects]**.

   >[!NOTE]
   >
   >Du kan ta bort dina egna delade projekt i samma dialogruta för att dela projekt genom att välja ett eller flera projekt.

## Byta namn på en arbetsyta {#task_0DB177DD6DB54B7F9FE60A0B3FC7CFC3}

Steg som beskriver hur du byter namn på en arbetsyta.

<!-- 

t_rename_workspace.xml

 -->

1. Högerklicka på arbetsytans namn.
1. Välj **[!UICONTROL Rename Workspace]**.
1. Skriv ett namn och klicka sedan på **[!UICONTROL OK]**.

## Öppna lokalt projekt {#task_1B3EF63A80C74776B24B99D80EAC74AC}

Steg som beskriver hur du öppnar en lokal kopia av ett projekt.

<!-- 

t_open_local_project.xml

 -->

1. Klicka på **[!UICONTROL File]** > **[!UICONTROL Open Local Copy]**.
1. Navigera till den lokala [!DNL .dproj] filen och klicka sedan på **[!UICONTROL Open]**.

## Rapportmallar {#concept_370F674C5B4C45368731AA801C5A45F8}

Mallar är utgångspunkter för den typ av analys som du vill utföra. En mall kan vara en tom arbetsyta, till exempel en Rankad eller Utfall-rapport. Eller så är mallen en rapport som börjar med standardvärden och -mått.

<!-- 

c_templates.xml

 -->

Du kan komma åt mallar när du skapar ett projekt ( **[!UICONTROL File]** > **[!UICONTROL New Project]**) eller genom att lägga till en arbetsyta eller rapport.

| Mall | Beskrivning |
|--- |--- |
| Rankad | Innehåller en tom arbetsyta där du kan skapa en tabell. En sidrapport rangordnar till exempel sidorna på din webbplats baserat på trafik. Detaljtabellen visar procenttal och siffror för mätvärden som Sidvyer och Intäkter. |
| Trender | Gör att du kan undersöka hur konverteringar och händelser trendar under en viss tidsperiod (timme, dag, vecka, månad, kvartal eller år) under en rapporteringsperiod. |
| Summor | En rapport på chefsnivå som visar siffror i resultatet. Den innehåller data för Total Intäkter, Sidvisningar och Beställningar. |
| Utfall | Gör att du kan skapa en kanal som visar konverterings- och utfallsfrekvenser mellan kontrollpunkter. Du kan till exempel spåra en besökares utfallspunkter under en köpprocess. |
| Flöde | Visar de vanligaste sökvägarna som användare tar över sidor, webbplatsavsnitt och servrar. |
| Konverteringsström | Visar konverteringsprocentsatser mellan specifika måtthändelser. Du kan använda den här rapporten för att förstå antalet klickningar som genererar försäljning och antalet sålda enheter. |
| Platsanalys | Ett tredimensionellt verktyg för webbplatspaltning som visar hur besökarna rör sig mellan angivna sidor och händelser. |
| Grupp för virtuellt fokus | Besök dig slumpmässigt från dina besök och visar en stor mängd data om besöket. Du kan använda rapporten för att skapa fokusgrupper utifrån besökarpopulationen. |

## Öppna en rapport {#task_0AC455CDA198497AA546622FB05F300D}

Du kan öppna en rapport eller en mall när du skapar ett projekt, eller från ett befintligt projekt. Använd en mall för att konfigurera en rapport från början.

<!-- 

t_reports_opening.xml

 -->

Det finns flera sätt att öppna en rapport:

* Sök efter en rapport eller välj en mall på [!UICONTROL New Report] sidan.
* Klicka **[!UICONTROL Reports]** på menyn och välj sedan en rapport- eller rapportmall.
* Starta en rapport från en dimension: högerklicka på ett dimensionsnamn och välj sedan **[!UICONTROL Run Report]** > **`report name`**.
