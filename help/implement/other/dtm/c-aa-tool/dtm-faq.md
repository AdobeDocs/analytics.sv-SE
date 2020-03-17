---
description: A FAQ about the automatic configuration of the Adobe Analytics deployment. Den automatiska konfigurationsmetoden hanterar AppMeasurement-koden åt dig.
keywords: Dynamic Tag Management;plug-ins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Frågor och svar om Adobe Analytics Tool
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Frågor och svar om Adobe Analytics Tool

A FAQ about the automatic configuration of the Adobe Analytics deployment. Den automatiska konfigurationsmetoden hanterar koden åt dig [!DNL AppMeasurement] .

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Var lägger jag mina plugin-program när jag implementerar Adobe Analytics via DTM? </p> </td> 
   <td colname="col2"> <p> Om du använder DTM för att hantera <code> s_code</code><code> s_code</code>plugin-program manuellt kan de läggas till i samma redigerare som värddatorn, på samma sätt som i en vanlig Adobe Analytics-implementering. </p> <p>Det är emellertid också ett alternativ att placera plugin-programmen i redigeraren under <span class="term"> Anpassa sidkod</span> i verktygsinställningarna. Båda genomförandemetoderna bör vara lika effektiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Om jag gör konfigurationsändringar i den nya versionen av verktyget, kan jag testa mellanlagring innan jag publicerar till produktion? </p> </td> 
   <td colname="col2"> <p>Ja. </p> <p>Alla ändringar kan testas i mellanlagringen på samma sätt som du normalt gör innan du distribuerar till en produktionsmiljö. Om du väljer att inte publicera kommer produktionskoden att fortsätta fungera som den gjorde innan den nya integreringen släpptes eftersom du märker problem med mellanlagring. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Om jag växlar från manuell konfiguration (standardinställningen för befintliga verktyg) till automatisk konfiguration, kommer mina aktuella inställningar att påverkas? </p> </td> 
   <td colname="col2"> <p>Nej. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Om jag byter från manuell bibliotekshantering till Hanteras av Adobe, kommer mina aktuella inställningar eller kod att påverkas? </p> </td> 
   <td colname="col2"> <p>All användarkod som du har angett skrivs över med det grundläggande <span class="keyword"> AppMeasurement</span> -biblioteket. Du måste flytta den här koden till det nya avsnittet <span class="wintitle"> Egen sidkod</span> i slutet av verktygskonfigurationen så att koden fortsätter att köras. Med den här metoden kan <span class="keyword"> AppMeasurement</span> -biblioteket hanteras (och uppgraderas) separat från användarens anpassade kod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kommer revisionshistoriken för <span class="keyword"> Adobe Analytics</span> -verktyget att bevaras när den nya integreringen släpps? </p> </td> 
   <td colname="col2"> <p>Ja. </p> </td> 
  </tr> 
 </tbody> 
</table>

Se [Lägg till Adobe Analytics Tool](/help/implement/other/dtm/c-aa-tool/analytics-dtm.md) för konfigurationsinformation.

## Potentiella förmåner {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Det finns en liten risk för att integreringen kan orsaka datainsamlingsproblem om du använder [!DNL Adobe Analytics]. Dessa problem kan uppstå endast om du publicerar biblioteket i produktion efter releasen. (Produktionskoden förblir intakt tills publicering sker.)

Undvik dessa problem genom att se till att:

* Rapportsvitens ID anges korrekt i verktyget.
* Rapportsvitens ID:n i verktyget matchar ID:n i [!DNL AppMeasurement] koden.
* Konfigurationsfälten för valutakod, teckenuppsättning, spårningsserver och SSL-spårningsserver är korrekt inställda med värden som stöds.
* Anpassad kod definieras i [!DNL Library Management].

