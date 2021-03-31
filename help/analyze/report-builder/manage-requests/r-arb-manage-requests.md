---
description: Fältbeskrivningar för Hantera begäranden i Report Builder.
title: Hantera förfrågningar – definitioner
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---


# Hantera förfrågningar – definitioner

Fältbeskrivningar för Hantera begäranden i Report Builder.

## Översikt {#section_75C288C945FA4781A4EDF806711A5660}

[!UICONTROL Request Manager] ger en detaljerad vy över statusen för alla begäranden som du har skapat för alla blad eller bara ett blad i den aktiva arbetsboken. Du kan också lägga till, redigera, uppdatera och ta bort en begäran (funktioner som vanligtvis är kopplade till [!UICONTROL Request Wizard] och [!UICONTROL Request Manager]) genom att högerklicka på en tillgänglig cell i Excel-kalkylbladet som innehåller tidigare begäranden.

[!UICONTROL Request Manager] visas när du klickar på **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) i verktygsfältet Report Builder.

>[!NOTE]
>
>Adobe Report Builder verkställer endast beroenden av begäranden inom samma kalkylblad, inte mellan kalkylblad. Genom att begränsa till beroenden i ett enda kalkylblad säkerställs att körningen går så snabbt som möjligt.

## Definitioner {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Alla blad </p> </td> 
   <td colname="col2"> <p>Visar begäranden från alla blad i den aktiva arbetsboken. Om du vill visa begäranden från specifika blad avmarkerar du det här alternativet. Om du avmarkerar det här alternativet måste du klicka på en bladflik längst ned i Excel-rapporten för att visa begäranden som är kopplade till det bladet i <span class="wintitle"> Request Manager</span>. Etiketten bredvid kryssrutan anger vilket blad i arbetsboken som är i fokus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Blad </p> </td> 
   <td colname="col2"> <p>Visar namnet på bladen i arbetsboken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Suite </p> </td> 
   <td colname="col2"> <p>Visar namnet på rapportsviten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datumintervall </p> </td> 
   <td colname="col2"> <p>Visar rapportens angivna datumintervall. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kornighet </p> </td> 
   <td colname="col2"> <p>Anger förfrågningens granularitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Senaste körning </p> </td> 
   <td colname="col2"> <p>Anger det datum då begäran senast bearbetades av Report Builder. Ett diagnostiskt meddelande visas även i den här tabellen i kolumnen <span class="wintitle"> Senaste körning</span>, om tillämpligt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lägg till </p> </td> 
   <td colname="col2"> <p>Visar dialogrutan Begäranguiden. Se <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > Skapa en databegäran</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Redigera </p> </td> 
   <td colname="col2"> <p> (eller Redigera flera) Redigerar en markerad begäran. Systemet visar dialogrutan <span class="wintitle"> Request Wizard</span>. Se <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Redigera flera begäranden</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta bort </p> </td> 
   <td colname="col2"> <p>Tar bort begäranden. Du kan ta bort flera markerade begäranden. Du kan även ta bort en begäran i listan genom att markera begäran och trycka på Delete på tangentbordet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Markera alla </p> </td> 
   <td colname="col2"> <p>Markera alla begäranden. I <span class="wintitle"> Request Manager</span> visas antalet begäranden som du har valt längst ned i listan över begäranden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Från cell </p> </td> 
   <td colname="col2"> <p>Hämtar data för en begäran från kalkylbladet. Om en begäran är associerad med den markerade cellen i det aktiva kalkylbladet, markeras den associerade begäran i listan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Uppdatera </p> </td> 
   <td colname="col2"> <p>Uppdaterar en enskild begäran eller ett urval av begäranden. (Se <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Uppdatera en begäran</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uppdatera lista </p> </td> 
   <td colname="col2"> <p>Uppdaterar alla begäranden som visas. När du uppdaterar alla begäranden är tiden det tar att uppdatera informationen från servern till rapporten direkt proportionerlig till komplexiteten hos förfrågningarna i rapporten. För mycket stora rapporter kan det ta flera minuter att uppdatera alla förfrågningar. Därför kanske du vill uppdatera de mest brådskande begäranden separat och välja <span class="wintitle"> Uppdatera alla</span> vid ett annat, mindre tidskritiskt tillfälle. </p> <p> <p>Obs! Vi rekommenderar att du ofta kontrollerar resultaten i <span class="wintitle"> Request Manager</span> om du uppdaterar ett kalkylblad som innehåller flera begäranden. Om ett fel uppstår i en begäran hjälper felmeddelandet i diagnostikkolumnen dig att hitta felets källa. I de flesta fall visas ett felmeddelande när en begäran misslyckas, men då och då genereras inget felmeddelande. Du kan märka att en uppdatering inte uppdaterar data i en cell som innehåller en referens, eller att en uppdatering tar bort data från cellen. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

