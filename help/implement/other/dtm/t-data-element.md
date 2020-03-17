---
description: Skapa ett dataelement i Dynamic Tag Management.
keywords: Dynamic Tag Management;data element;create new data element;name;type;default value;force lowercase value;remember this value for
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Skapa ett dataelement
uuid: eacd5c60-6197-4129-a9e1-a39e9a58b38a
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Skapa ett dataelement

Skapa ett dataelement i Dynamic Tag Management.

1. [Skapa webbegenskaper](/help/implement/other/dtm/t-create-web-property.md)om du inte redan har gjort det.
1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Data Elements]** i webbdelen.
1. Klicka på **[!UICONTROL Create New Data Element]**.
1. Fyll i följande fält och alternativ:

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> Alternativ</th> 
      <th class="chdeschd"> Beskrivning</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Namn</strong></td> 
      <td class="chdesc stentry"> <p>Dataelementets egna namn som en marknadsförare kan identifiera. Exempel, 
        <code>
          Product ID
        </code>. </p> <p> <p>Obs!  Namnet refereras av regelbyggaren, inte ett ID. Om du ändrar namnet på dataelementet måste du ändra dess referens i alla regler som använder det. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Typ</strong></td> 
      <td class="chdesc stentry"> <p> Anger varifrån data hämtas, till exempel JS-objekt, CSS-väljare, cookie, URL-parameter eller anpassat skript. </p> <p>Beroende på vilken typ du väljer visas olika alternativ. Mer information och exempel finns i Types of Data Elements <a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html"></a> i produktdokumentationen för Dynamic Tag Management. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Standardvärde</strong></td> 
      <td class="chdesc stentry"> <p>Ett standardelement. Detta värde ser till att dataelementet alltid har ett värde, även om en URL-parameter inte finns eller inte kan hittas av Dynamic Tag Management. </p> <p> <p>Obs!  Om det inte finns något värde och inget standardvärde returneras ingenting. Alla variabler som refererar till det dataelementet kommer inte att anges. Observera också att standardvärdefältet ignoreras om det är ett dataelement för anpassad kod. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Använd gemener</strong></td> 
      <td class="chdesc stentry"> <p>Dynamic Tag Management minskar automatiskt värdet. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Kom ihåg det här värdet för</strong></td> 
      <td class="chdesc stentry"> <p>Hur länge du vill att Dynamic Tag Management ska komma ihåg det här värdet. </p> <p> Giltiga värden är: </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>Session: Sessionsbaserad timing kan variera beroende på implementeringen. Sessionsdataelementen är inställda på sessionscookien. Den här inställningen kan dock baseras på en webbserver eller webbläsaren. Den är inte relaterad till sessionen som används i marknadsföringsrapporter och analyser. </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>Sidvy </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>Besökare </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   Mer information om hur du använder dataelement finns i [Dataelement](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html) i produktdokumentationen för Adobe Tag Management.
1. Klicka på **[!UICONTROL Save Data Element]**.
