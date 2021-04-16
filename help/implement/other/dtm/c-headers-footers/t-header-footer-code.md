---
description: Använd dynamisk tagghantering för att lägga till kod för sidhuvud och sidfot som avgör inläsningen av JavaScript och sidinnehåll på webbplatsen. Du måste installera både sidhuvuds- och sidfotskoden på alla sidor på webbplatsen, oavsett vilket värdalternativ som används.
keywords: Analysimplementering;implementeringsmetod;dynamisk tagghantering;dtm;kod;sidkod;sidhuvudskod;sidfotskod;inbäddningskod;inbäddningsflik;inbäddning
title: Lägg till sidhuvuds- och sidfotskod
topic-fix: Developer and implementation
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
exl-id: 170c28fb-8884-4c44-b586-f88a7583083e
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 2%

---

# Lägg till sidhuvuds- och sidfotskod

Använd dynamisk tagghantering för att lägga till kod för sidhuvud och sidfot som avgör inläsningen av JavaScript och sidinnehåll på webbplatsen. Du måste installera både sidhuvuds- och sidfotskoden på alla sidor på webbplatsen, oavsett vilket värdalternativ som används.

Eftersom Dynamic Tag Management innehåller ett kodavsnitt i både sidhuvud och sidfot kan du köra regler i början eller slutet av en sida. Detta gör att du kan implementera testverktyg och andra tekniker samtidigt som du behåller kontrollen över spårningen av sidorna.

Med Dynamic Tag Management skapas inbäddningskoder för testning och produktion som du kan använda för att testa ändringar i din staging-miljö innan du gör ändringar i din produktionsmiljö.

>[!IMPORTANT]
>
>För att implementeringen ska lyckas är det viktigt att du följer dessa instruktioner så som de visas i hjälpen för Adobe. Du måste placera rubrikkoden i avsnittet `<head>` i dokumentmallarna. Du måste också placera sidfotskoden precis före den avslutande `</body>`-taggen. Om du placerar någon av dessa inbäddningskoder någon annanstans i koden, eller använder asynkrona metoder för att lägga till inbäddningskoderna, eller kapslar in inbäddningskoderna på något sätt, är *inte* en implementering av Dynamic Tag Management som stöds. Inbäddningskoderna måste implementeras exakt som angivet.
>
>En implementering som inte stöds kommer att ge oväntade resultat och förhindra kundtjänst och tekniker från att hjälpa dig med implementeringen.

1. I gränssnittet för dynamisk tagghantering öppnar du fliken [!UICONTROL Embed] och väljer värdalternativ (till exempel Akamai). Växla sedan till På.

   Stegresultat 1. Kopiera produktionshuvudkoden som finns på fliken Bädda in i Dynamic Tag Management och placera den i [!DNL HEAD]-avsnittet i HTML-koden för platsen.

   ![](assets/dtm-embed.png)

   Placera koden så nära taggen `<head>` som möjligt. Det här kodfragmentet ska placeras på alla sidor i produktionsplatsen.

   >[!NOTE]
   >
   >Produktionsinbäddningskoden speglar bara de publicerade objekten i den [egenskapen](/help/implement/other/dtm/t-create-web-property.md). Inbäddningskod för mellanlagring reflekterar dock alla objekt i den associerade egenskapen, oavsett publicerat eller opublicerat läge. Om du vill testa opublicerade objekt på din produktionsplats aktiverar du lokal mellanlagring i konsolen genom att följa instruktionerna i [Testa opublicerade regler för Akamai Hosting](/help/implement/other/dtm/c-rules/t-test-rules-akamai.md).

1. Kopiera koden för produktionssidfoten och placera den i [!DNL BODY]-avsnittet i HTML-koden för platsen.

   Placera koden så nära taggen `</body>` som möjligt.
1. Kopiera koden för sidhuvud och sidfot för mellanlagring och upprepa sedan stegen ovan på mellanlagringsplatsen.

   >[!NOTE]
   >
   >Skillnaden mellan kodfragment för produktion och mellanlagring är att [!DNL -staging] har lagts till i filnamnet i mellanlagringsversionen. Sidfotskoden är densamma i staging och produktion.
