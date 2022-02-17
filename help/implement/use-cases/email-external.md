---
title: Extern e-postspårning
description: Använd Adobe Analytics för att spåra e-postinnehåll.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---

# Extern e-postspårning

Företagen använder Analytics för att avgöra hur framgångsrik en e-postkampanj är.

[!DNL Analytics] kan rapportera analysdata för e-postkampanjer i flera viktiga mätvärden, bland annat följande:

| Mått | Beskrivning |
|---|---|
| Genomklickningar | Visar antalet genomklickningar som spåras från e-postmeddelandet till landningssidan. |
| Inköp och/eller lyckade inköp | Visar antalet inköp som är resultatet av e-postmeddelandet. |
| Beställningar | Visar antalet beställningar som gjorts som ett resultat av e-postmeddelandet. |
| Avkastning | Visar dollarbeloppet per besök som genererats från e-postmeddelandet. |
| Konvertering | Visar antalet leads, registreringar eller andra lyckade händelser som genereras från e-postmeddelandet. |

Du måste ändra e-postbrödtexten och JavaScript-biblioteket i HTML för att kunna hämta nyckelmåtten som visas ovan.

## Implementering {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Det finns flera steg att följa för att visa data för e-postkampanjanalys. Stegen beskrivs enligt följande:

1. Skapa unika spårningskoder.

   Användare frågar ofta efter rekommendationer för varje unik kampanj. Det är helt och hållet upp till dem, baserat på vad som fungerar bäst. Alla användare är olika. Adobe rekommenderar att varje användare genererar egna spårningskoder, vilket visas i exemplet nedan:

   * sc_cid=A1123A321 > &quot;A&quot; flaggar filialkampanj
   * sc_cid=EM033007 > &quot;EM&quot; flaggar e-postkampanj
   * sc_cid=GG987123 > &quot;GG&quot; innebär Google och är en betalsökkampanj

   Kontakta Adobe [!DNL Customer Care] om du vill ha information om hur du ställer in och använder spårningskoder.

1. Lägg till frågesträngsparametrar i HTML e-postlänkar.

   För att spåra en användarklicknings- och efterföljande lyckningshändelser måste en frågesträngsparameter läggas till i varje länk i HTML-e-postmeddelandet. Du kan välja att spåra varje länk separat eller att hålla ihop alla länkar. Varje länk kan ha en unik spårningskod eller så kan alla länkar ha samma spårningskod. Tänk på följande hypotetiska länk i e-postmeddelandet till en webbplats:

   ```js
   <a href="https://www.example.com/index.asp">Visit our home page</a>
   ```

   Följande frågesträngsparametrar ?sc_cid=112233B ska läggas till i länken ovan:

   ```js
   <a href= "https://www.example.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Uppdatera JavaScript-biblioteket.

   Ändra kod i JavaScript-filen, [!DNL s_code.js]Med kan du fånga upp hur många användare (och vilka användare) som har klickat igenom från e-postmeddelandet och deltagit i efterföljande lyckade händelser. Det finns två steg för att uppdatera JavaScript-biblioteket.

   1. Anpassa [!DNL s_code.js] genom att ringa [!UICONTROL getQueryParam].

      The [!DNL s_code.js] filen ska placeras på en plats på webbservern där varje webbsida kan komma åt den. The *`doPlugins`* -funktionen i den här filen bör ändras så att den hämtar frågesträngsparametrarna på e-postlänkarna. Exempel:

      ```js
      /* Plugin Config */ 
      s.usePlugins=true 
      function s_doPlugins(s) { 
       /* Add calls to plugins here */ 
       // External Campaigns 
      s.campaign=s.getQueryParam('source') 
      } 
      s.doPlugins=s_doPlugins 
      ```

      Varje frågesträngsparameter som måste kopieras till en variabel måste ha en [!UICONTROL getQueryParam] ring. I exemplet ovan är frågesträngsparametern [!UICONTROL sc_cid] kopieras till *`campaign`*.

      Endast första anropet till [!UICONTROL getQueryParam] krävs för att fånga klickningar. Kontakta Adobe [!DNL Customer Care] för att implementera den här funktionen och se till att din version av JavaScript-filen innehåller [!UICONTROL getQueryParam] plugin-program.

   1. Kontrollera att koden för att klistra in JavaScript-taggar finns på alla landningssidor. Koden som ska klistras in måste referera till versionen av [!DNL s_code.js] ändras i del A.

      Följande punkter är viktiga att komma ihåg när du uppdaterar JavaScript-biblioteket. Dessa punkter listas nedan.

      * Frågesträngsparametern [!UICONTROL sc_cid] måste vara synligt i URL:en på den slutliga landningssidan, annars registreras ingen genomklickningskonvertering.
      * The [!UICONTROL sc_cid] parameter är ett exempel på en frågesträngsparameter. Alla frågesträngsparametrar kan användas och hämtas av [!UICONTROL getQueryParam] plugin-program. Kontrollera att frågesträngsparametrarna bara används för kampanjspårning. När parametrarna visas i en frågesträng kopieras deras värden till *`campaign`*.

1. Använd [!UICONTROL SAINT] för att klassificera kampanjspårningskoder.

   The [!UICONTROL SAINT Campaign Management Tool] kan användas för att konvertera spårningskoder till användarvänliga namn. Det kan också användas för att sammanfatta resultatet av varje e-postkampanj. Steg 5 nedan beskriver processen som krävs för att skapa en e-postkampanj.

1. Se Betalning via e-postkampanj (valfritt).

   Målningsanalys med e-postkampanjer kan utföras på liknande sätt som målning med en annan kampanj. Du kan använda en variabel för att visa mellanrum efter kampanj, vilket förklaras i följande steg:

   1. Kontakta Adobe [!DNL Customer Care] om att sätta på en bana för [!UICONTROL Custom Insight] variabel (prop)

   1. På alla sidor kopierar du sidnamnet till det avsedda [!DNL s.prop].
   1. Lägg till namnet på e-postkampanjen till säljaren på e-postlandningssidan. Resultatet visas enligt nedan:

      ```js
      s.prop1="Home Page : 123456"
      ```

      När målning är aktiverad för [!UICONTROL Custom Insight] variabel kan du använda [!UICONTROL Path] rapporter (som [!UICONTROL Next Page Flow] eller [!UICONTROL Fallout]) för att se besöksnavigering från landningssidan.
