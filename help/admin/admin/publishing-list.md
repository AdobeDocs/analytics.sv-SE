---
description: Att publicera listor är ett enkelt sätt att skicka olika rapporter som är specifika för olika grupper i organisationen utan att behöva skapa flera separata schemalagda rapporter. Publiceringslistor är användbara om du har platsspecifika rapportsviter och vill ge varje avdelning en kopia av en specifik kontrollpanel. Du kan också använda publiceringslistor för att skicka data till många personer utan att behöva skriva in deras e-postadresser separat, om du arbetar med en enda rapportserie.
title: Publiceringslistor
feature: Admin Tools
uuid: 07dad661-c302-4981-80d1-3169ad1fe90e
exl-id: 5c9a0ae7-742b-4247-bcbc-2e979af6160c
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---

# Publiceringslistor

Att publicera listor är ett enkelt sätt att skicka olika rapporter som är specifika för olika grupper i organisationen utan att behöva skapa flera separata schemalagda rapporter. Publiceringslistor är användbara om du har platsspecifika rapportsviter och vill ge varje avdelning en kopia av en specifik kontrollpanel. Du kan också använda publiceringslistor för att skicka data till många personer utan att behöva skriva in deras e-postadresser separat, om du arbetar med en enda rapportserie.

Flera publiceringslistor kan anges när en rapport schemaläggs.

## Publiceringslistornas upphörande

Som du antagligen vet kommer Adobe att ersätta både Reports and Analytics (R&amp;A) och Site Catalyst-punktprodukten den 31 december 2023. [Du kan lära dig mer om hur utgånget är och hur du kan förbereda dig för det här](https://express.adobe.com/page/6WnF8JK6IRDhf/).

En av de funktioner i FoA som är avsedda att nå slutet av livscykeln det här datumet är Publiceringslistor. Vissa funktioner som Kalenderhändelser och Sidsammanfattningsrapport har/kommer att ha en paritetsversion i Analysis Workspace. Publiceringslistor är dock inte en av dem och kommer att bli inaktuella när FoA når sitt slut. **Du kommer inte att kunna skapa nya eller använda befintliga publiceringslistor för att skicka eller schemalägga Analysis Workspace-projekt.**

För att minska eventuella störningar i de arbetsflöden för rapportdistribution som är beroende av publiceringslistor ber vi dig att överväga följande alternativ:

* Om du använder Publiceringslistor för att distribuera samma version av rapporten till flera användare (utan att tillämpa åsidosättningar av rapportsviter):

   När du återskapar dina rapporter i Analysis Workspace som projekt kan du använda en kombination av en kontaktgrupp eller distributionslista som skapats för din e-postklient och funktionen Schemalagda projekt på arbetsytan för att skicka eller schemalägga den återkommande leveransen av projektet. Precis som publiceringslistor skickas sedan en PDF/CSV-version av projektet till alla e-post-ID som ingår i gruppen/listan. Du kan lära dig mer om [Schemalagda projekt här](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html#:~:text=Scheduled%20Analysis%20Workspace%20projects%20can,options%20in%20the%20left%20rail.).

* Om du använder publiceringslistor för att distribuera flera versioner av rapporten eller kontrollpanelen till flera användare (via rapportsvitens åsidosättningsfunktion):

   Analysis Workspace stöder inte åsidosättande av rapportsviten. Det stöder inte heller möjligheten att låsa rapportsviter vid delning och planering av projekt. Om du vill replikera arbetsflödet kan du behöva skapa flera versioner av samma projekt med olika rapportsviter för varje version och sedan använda den schemalagda projektfunktionen som beskrivs ovan.

Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst.

## Beskrivningar av publiceringslisthanteraren {#section_099DF8AC5691495F9B22C71266DD6004}

| Element | Beskrivning |
|--- |--- |
| [!UICONTROL Search for] | Gör att du kan filtrera tabellen och söka efter en publiceringslista. |
| [!UICONTROL Report Suites to Include] | Åsidosätter rapportsviten för en schemalagd rapport eller alla rapporter på en kontrollpanel. Även om det inte finns någon teknisk gräns för hur många separata poster i rapporteringsprogramsviten som ska anges, rekommenderas en begränsning till ungefär 50. Det finns ingen fastställd gräns för hur många e-postmeddelanden som kan inkluderas. |
| [!UICONTROL E-mail Addresses] | En kommaavgränsad lista över alla e-postmeddelanden som kommer att ta emot rapporten med den nya rapportsviten.  Klicka **[!UICONTROL Click to Edit]** för att ange de e-postadresser som ska tas emot. Ange varje e-postadress och avgränsa flera e-postadresser med semikolon (;). Tryck `<Enter>` när e-postadresserna är klara. <br>I fältet Antal e-postmeddelanden visas antalet e-postadresser som för närvarande är associerade med posten för rapportsviten. |
| [!UICONTROL Duplicate] | Skapar en kopia av publiceringslistan. |
