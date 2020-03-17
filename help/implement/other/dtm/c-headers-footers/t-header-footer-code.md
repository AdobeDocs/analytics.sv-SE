---
description: Använd dynamisk tagghantering för att lägga till kod för sidhuvud och sidfot som avgör inläsningen av JavaScript och sidinnehåll på webbplatsen. Du måste installera både sidhuvuds- och sidfotskoden på alla sidor på webbplatsen, oavsett vilket värdalternativ som används.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;embed tab;embed
title: Lägg till sidhuvud och sidfot
topic: Developer and implementation
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Lägg till sidhuvud och sidfot

Använd dynamisk tagghantering för att lägga till kod för sidhuvud och sidfot som avgör inläsningen av JavaScript och sidinnehåll på webbplatsen. Du måste installera både sidhuvuds- och sidfotskoden på alla sidor på webbplatsen, oavsett vilket värdalternativ som används.

Eftersom Dynamic Tag Management innehåller ett kodavsnitt i både sidhuvud och sidfot kan du köra regler i början eller slutet av en sida. Detta gör att du kan implementera testverktyg och andra tekniker samtidigt som du behåller kontrollen över spårningen av sidorna.

Med Dynamic Tag Management skapas inbäddningskoder för testning och produktion som du kan använda för att testa ändringar i din staging-miljö innan du gör ändringar i din produktionsmiljö.

>[!IMPORTANT]
>
>För en lyckad implementering är det viktigt att du följer dessa instruktioner så som de visas i Adobe-hjälpen. Du måste placera rubriktexten i dokumentmallens `<head>` avsnitt. Du måste också placera sidfotskoden precis före den avslutande `</body>` taggen. Att placera någon av dessa inbäddningskoder någon annanstans i koden, eller använda asynkrona metoder för att lägga till inbäddningskoderna, eller kapsla inbäddningskoderna på något sätt, är *inte* en implementering av Dynamic Tag Management som stöds. Inbäddningskoderna måste implementeras exakt som angivet.
>
>En implementering som inte stöds kommer att ge oväntade resultat och förhindra kundtjänst och tekniker från att hjälpa dig med implementeringen.

1. I gränssnittet för dynamisk tagghantering öppnar du fliken och väljer värdalternativet (till exempel Akamai). Växla sedan till&quot;På&quot;. [!UICONTROL Embed]

   Stegresultat 1. Kopiera produktionshuvudkoden som finns på fliken Bädda in i Dynamic Tag Management och placera den i delen [!DNL HEAD] av platsens HTML-kod.

   ![](assets/dtm-embed.png)

   Placera koden så nära [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] tagga så mycket som möjligt. Det här kodfragmentet ska placeras på alla sidor i produktionsplatsen.

   >[!NOTE]
   >
   >Produktionsinbäddningskoden visar bara de publicerade objekten i den [egenskapen](/help/implement/other/dtm/t-create-web-property.md). Inbäddningskod för mellanlagring reflekterar dock alla objekt i den associerade egenskapen, oavsett publicerat eller opublicerat läge. Om du vill testa opublicerade objekt på din produktionsplats aktiverar du lokal mellanlagring i konsolen genom att följa instruktionerna i [Testa opublicerade regler för Akamai Hosting](/help/implement/other/dtm/c-rules/t-test-rules-akamai.md).

1. Kopiera koden för produktionssidfoten och placera den i avsnittet för [!DNL BODY] din webbplats-HTML.

   Placera koden så nära [!DNL </body>] tagga så mycket som möjligt.
1. Kopiera koden för sidhuvud och sidfot för mellanlagring och upprepa sedan stegen ovan på mellanlagringsplatsen.

   >[!NOTE]
   >
   >Skillnaden mellan produktions- och mellanlagringskodfragment är att det läggs [!DNL -staging] till i filnamnet i mellanlagringsversionen. Sidfotskoden är densamma i staging och produktion.

