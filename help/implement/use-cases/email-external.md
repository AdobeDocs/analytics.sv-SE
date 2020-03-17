---
title: Extern e-postspårning
description: Använd Adobe Analytics för att spåra e-postinnehåll.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Extern e-postspårning

Företagen använder Analytics för att avgöra hur framgångsrik en e-postkampanj är.

[!DNL Analytics] kan rapportera analysdata för e-postkampanjer i flera viktiga mätvärden, bland annat följande:

| Mått | Beskrivning |
|---|---|
| Klickningar | Visar antalet genomklickningar som spåras från e-postmeddelandet till landningssidan. |
| Inköp och/eller lyckade inköp | Visar antalet inköp som är resultatet av e-postmeddelandet. |
| Beställningar | Visar antalet beställningar som gjorts som ett resultat av e-postmeddelandet. |
| Avkastning | Visar dollarbeloppet per besök som genererats från e-postmeddelandet. |
| Konvertering | Visar antalet leads, registreringar eller andra lyckade händelser som genereras från e-postmeddelandet. |

Du måste ändra HTML-e-postbrödtexten och JavaScript-biblioteket för att kunna hämta nyckelmåtten som visas ovan.

## Implementering {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Det finns flera steg att följa för att visa data för e-postkampanjanalys. Stegen beskrivs enligt följande:

1. Skapa unika spårningskoder.

   Användare frågar ofta efter rekommendationer för varje unik kampanj. Det är helt och hållet upp till dem, baserat på vad som fungerar bäst. Alla användare är olika. Adobe rekommenderar alla användare att generera egna spårningskoder, vilket visas i exemplet nedan:

   * sc_cid=A1123A321 > &quot;A&quot; flaggar filialkampanj
   * sc_cid=EM033007 > &quot;EM&quot; flaggar e-postkampanj
   * sc_cid=GG987123 > &quot;GG&quot; betyder Google och är en betalsökningskampanj
   Kontakta Adobe [!DNL Customer Care] för mer information om hur du ställer in och använder spårningskoder.

1. Lägg till frågesträngsparametrar i HTML-e-postlänkar.

   För att spåra en användarklicknings- och efterföljande lyckningshändelser måste en frågesträngsparameter läggas till i varje länk i HTML-e-postmeddelandet. Du kan välja att spåra varje länk separat eller att hålla ihop alla länkar. Varje länk kan ha en unik spårningskod eller så kan alla länkar ha samma spårningskod. Tänk på följande hypotetiska länk i e-postmeddelandet till en webbplats:

   ```js
   <a href="https://www.example.com/index.asp">Visit our home page</a>
   ```

   Följande frågesträngsparametrar ?sc_cid=112233B ska läggas till i länken ovan:

   ```js
   <a href= "https://www.example.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Uppdatera JavaScript-biblioteket.

   Genom att ändra kod i JavaScript-filen [!DNL s_code.js]kan du ta reda på hur många användare (och vilka användare) som har klickat igenom från e-postmeddelandet och deltagit i efterföljande lyckade händelser. Det finns två steg för att uppdatera JavaScript-biblioteket.

   1. Anpassa [!DNL s_code.js] genom att ringa [!UICONTROL getQueryParam].

      Filen ska placeras på en plats på webbservern där varje webbsida kan komma åt den. [!DNL s_code.js] Funktionen i den här filen bör ändras så att den hämtar frågesträngsparametrarna på e-postlänkarna. *`doPlugins`* Exempel:

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

      Varje frågesträngsparameter som måste kopieras till en variabel måste ha ett [!UICONTROL getQueryParam] anrop. I exemplet ovan [!UICONTROL sc_cid] kopieras frågesträngsparametern till *`campaign`*.

      Endast det första anropet [!UICONTROL getQueryParam] krävs för att fånga klickningar. Kontakta Adobe för [!DNL Customer Care] att implementera den här funktionen och kontrollera att din version av JavaScript-filen innehåller [!UICONTROL getQueryParam] plugin-programmet.

   1. Kontrollera att koden för att klistra in JavaScript-taggar finns på alla landningssidor. Denna kod som ska klistras in måste hänvisa till den version av [!DNL s_code.js] som ändrats i del A.

      Följande punkter är viktiga att komma ihåg när du uppdaterar JavaScript-biblioteket. Dessa punkter listas nedan.

      * Frågesträngsparametern [!UICONTROL sc_cid] måste vara synlig i URL:en på den sista landningssidan, annars registreras ingen klickkonvertering.
      * Parametern [!UICONTROL sc_cid] är ett exempel på en frågesträngsparameter. Alla frågesträngsparametrar kan användas och hämtas av [!UICONTROL getQueryParam] plugin-programmet. Kontrollera att frågesträngsparametrarna bara används för kampanjspårning. Varje gång parametrarna visas i en frågesträng kopieras deras värden till *`campaign`*.

1. Används [!UICONTROL SAINT] för att klassificera kampanjspårningskoder.

   Den här metoden [!UICONTROL SAINT Campaign Management Tool] kan användas för att konvertera spårningskoder till användarvänliga namn. Det kan också användas för att sammanfatta resultatet av varje e-postkampanj. Steg 5 nedan beskriver processen som krävs för att skapa en e-postkampanj.

1. Se Betalning via e-postkampanj (valfritt).

   Målningsanalys med e-postkampanjer kan utföras på liknande sätt som målning med en annan kampanj. Du kan använda en variabel för att visa mellanrum efter kampanj, vilket förklaras i följande steg:

   1. Kontakta Adobe [!DNL Customer Care] om hur du aktiverar en [!UICONTROL Custom Insight] variabel (prop)

   1. På alla sidor kopierar du sidnamnet till det angivna [!DNL s.prop].
   1. Lägg till namnet på e-postkampanjen till säljaren på e-postlandningssidan. Resultatet visas enligt nedan:

      ```js
      s.prop1="Home Page : 123456"
      ```

      När målning är aktiverat för [!UICONTROL Custom Insight] variabeln kan du använda [!UICONTROL Path] rapporter (till exempel [!UICONTROL Next Page Flow] eller [!UICONTROL Fallout]) för att se besöksnavigering från landningssidan.

