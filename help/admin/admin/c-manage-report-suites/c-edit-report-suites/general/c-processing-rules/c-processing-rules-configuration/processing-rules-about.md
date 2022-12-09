---
description: Med bearbetningsregler kan du ändra data baserat på definierade villkor. När attribut eller värden matchar definierade villkor kan värden anges och tas bort, och händelser kan anges.
subtopic: Processing rules
title: Så fungerar behandlingsregler
feature: Processing Rules
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 2%

---

# Så fungerar behandlingsregler

Med bearbetningsregler kan du ändra data baserat på definierade villkor. När attribut eller värden matchar definierade villkor kan värden anges och tas bort, och händelser kan anges.

Bearbetningsregler tillämpas på data när de samlas in, och regler tillämpas på alla data som kommer via AppMeasurement-biblioteken och via API:t för datainmatning. Bearbetningsreglerna gäller även för den fullständiga datakällan och loggdatakällan. Dessa källor innehåller data som representerar *`hit`* eller en åtgärd som en användare utför. Bearbetningsreglerna gäller inte för andra datakällor.

## Viktiga begrepp {#section_EB138775E7C64C74B0D1D3213F7A823C}

Följande tabell innehåller viktiga begrepp som du måste förstå när du använder bearbetningsregler:

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Koncept </p> </th> 
   <th colname="col2" class="entry"> <p>Detaljer </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Reglerna gäller för en enda rapportserie. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> Kopiera behandlingsregler till en annan rapportsvit </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bearbetningsreglerna tillämpas i den ordning som anges. </p> </td> 
   <td colname="col2"> <p>Om en åtgärd ändrar ett värde används det nya värdet för efterföljande villkor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bearbetningsreglerna tillämpas omedelbart på rapportsviten när de har sparats. </p> </td> 
   <td colname="col2"> <p>Ändringar i bearbetningsreglerna ska visas i rapportsviten inom några minuter efter att de har sparats. När vi testar bearbetningsregler rekommenderar vi att du konfigurerar <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md"> realtidsrapporter</a> i testrapportsviten så att du snabbt kan se resultatet av en bearbetningsregel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bearbetningsregler är det enda sättet att få åtkomst till kontextdatavariabler. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Kopiera en kontextdatavariabel till en eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bearbetningsregler tillämpas före VISTA-regler och regler för marknadsföringskanal. </p> </td> 
   <td colname="col2"> <p> <a href="/help/technotes/processing-order.md"> Bearbetningsordning </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Det går inte att utesluta träffar. </p> </td> 
   <td colname="col2"> <p>Du kan använda VISTA-regler för att exkludera träffar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produktsträngen, refereraren och användaragenten kan inte ändras. </p> </td> 
   <td colname="col2"> <p>Referent och användaragent är skrivskyddade. Produktsträngen är inte tillgänglig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribut och klassificeringar för mobila enheter är inte tillgängliga. </p> </td> 
   <td colname="col2"> <p>Sökning efter mobila enheter sker innan regler bearbetas, men attribut är inte tillgängliga i bearbetningsregler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Frågesträngsparametrar kan inte läsas utöver de första 255 tecknen i en URL om du kör JavaScript AppMeasurement H.25.2 eller tidigare. JavaScript AppMeasurement H.25.3 och senare innehåller den fullständiga URL:en inklusive alla frågesträngsparametrar för bearbetningsregler. </p> </td> 
   <td colname="col2"> <p>Uppgradera till H.25.3 eller senare, eller läs frågesträngsparametrar från långa URL:er på klientsidan och lagra värden i kontextdatavariabler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Frågesträngsvärden måste kodas i Unicode eller UTF-8 för att kunna läsas av bearbetningsregler. </p> </td> 
   <td colname="col2"> <p>Detta kan påverka flerbytetecken som skickas med frågesträngar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Du är begränsad till 150 regler med 30 villkor för varje rapportserie. </p> </td> 
   <td colname="col2"> <p>Bearbetningsregelgränserna är per rapportserie, inte per företag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bearbetningsregler måste ställas in för att hämta kontextdatavariabler innan data skickas. </p> </td> 
   <td colname="col2"> <p>Bearbetningsreglerna tillämpas när serveranrop skickas. Värden som lagras i kontextdatavariabler ignoreras om de inte kopieras med bearbetningsregler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Värdejämförelser i användargränssnittet är skiftlägeskänsliga. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> Rensa värden i en rapport </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sammanhangsdatavariabelnamn får bara innehålla alfanumeriska tecken, understreck och punkter. Eventuella ytterligare tecken tas bort. </p> </td> 
   <td colname="col2"> <p>Datavariabeln context <code> login_page-home</code> blir automatiskt <code> login_pagehome</code>. Alla data som skickas till <code> login_page-home</code> variabeln fördelas under <code> login_pagehome</code>. </p> <p>Kontextdatavariabler som innehåller tecken som inte stöds kan inte läggas till i gränssnittet Bearbetningsregler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cirkumflex (^) är ett specialtecken i bearbetningsregelsystemet. </p> </td> 
   <td colname="col2"> <p>Om du vill matcha ett enskilt cirkumflex använder du två cirkumflex (^^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Villkor för bearbetningsregel {#section_387390EEE9BA4DA98698522A84326DB4}

Villkor kontrollerar sidvariabler för ett matchande värde eller om ett värde finns. Du kan lägga till flera villkor och välja om alla villkor måste matchas.

Du kan skapa en regel utan villkor som alltid utför definierade åtgärder.

Variabler kontrolleras inte automatiskt för värden innan åtgärder utförs. Prop1 innehåller till exempel värdet &quot;någonting&quot; och eVar1 är tom. Om du anger Prop1 som lika med eVar1 kommer båda värdena att vara tomma. Om du behöver undvika det här lägger du till ett villkor för att kontrollera om ett värde finns.

## Bearbetar regelåtgärder {#section_E2285C9D008442C7BF136E52A9A4CC06}

Funktionsmakron anger sidvariabler, tar bort sidvariabler eller utlöser händelser. Åtgärder kan också sammanfoga värden som ska visas i en rapport.

Du kanske vill visa `category:product` genom att sammanfoga två variabler.
