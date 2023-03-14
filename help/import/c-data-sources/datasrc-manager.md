---
description: Skapa, hantera och visa användningen av datakällor i en rapportserie.
subtopic: Data sources
title: Data Sources Manager
topic-fix: Developer and implementation
feature: Data Sources
exl-id: a63137b8-deeb-4865-9be9-322416b00186
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---

# Data Sources Manager

Skapa, hantera och visa användningen av datakällor i en rapportserie.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data sources]**.

## Skapa flik {#section_74603FDA3D8842E49F1A51624A06DE20}

The [!UICONTROL Create] Med -fliken kan du konfigurera en ny datakälla för den valda rapportsviten. När du aktiverar en datakälla [!UICONTROL Data Sources Wizard] hjälper dig genom processen att skapa en mall för datakällor och skapar en FTP-plats för överföring av data.

Det du väljer på fliken Skapa avgör vilka inledande fält i mallen som skapas. Se [Generera en importfilsmall](/help/import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md).

## Fliken Hantera {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Starta om bearbetningen </p> </td> 
   <td colname="col2"> <p>Startar om bearbetning av datakälla som tidigare avbröts på grund av fel eller varningar. Bearbetningen fortsätter tills nästa fel påträffas. Datakällor avbryter bearbetningen av en datakällfil endast när du väljer <span class="uicontrol"> Avbryt bearbetning vid fel</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slutför bearbetning </p> </td> 
   <td colname="col2"> <p>Instruerar datakällor att stänga alla öppna besök i filen och slutföra bearbetningen av datakällfilen som om den är slutförd. Detta är användbart när du har besök som spänner över flera datakällfiler. Detta gäller endast <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Fullständig bearbetning</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inaktivera </p> </td> 
   <td colname="col2"> <p> Om du inaktiverar en datakälla tas den bort. Om några filer på servern har börjat bearbetas fortsätter bearbetningen tills den är klar. Filer som ännu inte börjat bearbetas kommer inte att bearbetas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stoppa bearbetning av fel/varningar </p> </td> 
   <td colname="col2"> <p> Instruerar bearbetningsmotorn för datakällor att avbryta bearbetningen när ett fel påträffas. Datakällan återupptar inte bearbetningen förrän du väljer Starta om bearbetning. Alternativet Stoppa bearbetning vid varningar gäller endast för <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Fullständig bearbetning</a>. </p> <p>När datakällor påträffar ett filfel får du ett meddelande om felet. Systemet flyttar datakällfilen med felet till en mapp med namnet <span class="filepath"> files_with_errors</span> på FTP-servern. När du har löst problemet skickar du datakällfilen igen för bearbetning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurera </p> </td> 
   <td colname="col2"> <p>Gör att du kan ändra datakällmallen eller andra inställningar som är specifika för den här datakällan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FTP-information </p> </td> 
   <td colname="col2"> <p>Visar FTP-information för den här datakällan. Använd den här informationen för att komma åt datakällmallen och skicka data från datakällan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filnamn </p> </td> 
   <td colname="col2"> <p>Namnet på den överförda filen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p> Filens aktuella status. Möjliga statusvärden är: </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">I kö (steg 1 av 3): Filen finns, men bearbetningen har inte påbörjats. Om filen inte visas inom 30 minuter kontrollerar du att den associerade <span class="filepath"> .fin</span> filen finns </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">Förberedelse (steg 2 av 3): Filen genomsöks efter fel eller varningar </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">Bearbetning (steg 3 av 3): Filen bearbetas </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">Misslyckades: Filen bearbetades inte på grund av fel </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">Slutfört: Filen har bearbetats fullständigt </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Fliken Fillogg {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

Filloggen innehåller en sökfunktion som gör att du kan söka efter information efter namn på datakälla, datakälltyp, filnamn, datum som tas emot eller status.
