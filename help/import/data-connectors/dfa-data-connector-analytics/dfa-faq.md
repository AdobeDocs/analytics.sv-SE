---
description: 'null'
keywords: DFA
title: Vanliga frågor
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Vanliga frågor{#frequently-asked-questions}

## Varför accepterar inte guiden för dataanslutningar mina inloggningsuppgifter? {#section-f019b3de18774df3954af7881aa564fa}

Om du har verifierat att inloggningsuppgifterna är giltiga kontrollerar du sedan att det användarnamn som har angetts för integreringen är aktiverat för API-åtkomst. Guiden Data Connectors använder DFA API för att validera inloggningsuppgifter samt stänger av och aktiverar Adobe-specifika inställningar i DFA API. API Access är en inställning som måste aktiveras inifrån DFA-gränssnittet av en administratör. Kontrollera sedan att du har behörighet att komma åt det annonsanvändar-ID eller det konfigurations-ID för Floodlight som valts i guiden.

## Varför ser jag inga data från de nightly uploaded metrics (DFA Impressions, DFA Clicks osv.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Om du använder version 1.5 av integreringen kan det bero på att integreringen ännu inte har tilldelats ett klientplats-ID. Ett CSID (Client Site ID) krävs för nattutbyte och för att begära data från DFA-annonsservern. CSID kan ta upp till tre dagar från integreringsdatumet att utbytas med Google. När CSID:t har tagits emot från Google meddelas du via integreringens e-postadress för det nya CSID:t, tillsammans med den senaste JavaScript-koden.

Om det har gått mer än tre dagar och du inte har fått installationsprogrammets e-post och mätvärden flödar, är det mest sannolika problemet att CSID redan har tilldelats en annan integrering. Google bevarar mappningen 1 till 1 mellan CSID och Report Suite, vilket innebär att om en integrering i en rapportserie använder samma Advertiser-ID som en annan integrering i en annan rapportsserie tilldelas endast det första ett CS-ID. Om du vill ändra vilket rapporteringsprogram eller Advertiser-ID som ett CSID mappas till måste en biljett öppnas med Google Support.

Anta till exempel att det finns en integrering i Report Suite A med Advertiser ID Z som tilldelas ett CSID. Om en annan integrering senare konfigureras i Report Suite B med Advertiser Z, kommer den här nyare integreringen INTE att tilldelas CSID på nytt. Det här skulle kräva en Google-biljett. Ta däremot ett exempel på en integrering i Report Suite A, med Advertiser ID Z, och senare en annan integrering i Report Suite A, så är Advertiser Z inställd. Endast den första integreringen kommer att ta emot data för integreringen. I det här fallet kan dock den första integreringen inaktiveras och data flödar till den andra integreringen.

> [!NOTE] CSID används inte i version 2.0 av integreringen och därför gäller inte CSID-förhandlingen.

## Jag använder version 2.0 av integrerings- och kostnadsstatistiken visas inte för mina DFA-annonser. Varför skulle det här vara? {#section-805748111bbe4bbf918d6dbbb2641fff}

Kostnadsvärden måste båda vara aktiverade från både Google DFA och anges i DFA-gränssnittet, samt aktiveras i guiden för dataanslutningar. Det första att verifiera är att du har mappat en Analytics-händelse för DFA Media Cost och angett en valutakod. Om du har mappat händelsen Mediekostnad och avslutar och sparar guiden aktiveras flaggan DFA omnitureCostData i DFA API. Detta signalerar till Google att mätvärdena ska skickas i nattfilen. Du kan dubbelkontrollera via DFA-gränssnittet att omnitureCostData är aktiverat genom att titta på egenskaper i det inbyggda Floodlight-objektet. När du har kontrollerat dessa två platser ser du till att annonserna som ingår i det integrerade Floodlight anger kostnadsdata och kostnadsstrukturer. Om inga kostnadsdata anges i DFA-gränssnittet visas de inte i Analytics.

## Varför visar vissa annonser inga DFA-exponeringar eller -visningar, men de visar faktiskt klickningar och klickningar? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Det finns några annonser som bara spelar in klickdata, som kallas klickningsspårare. Den här typen av annonser returnerar inte senaste visningsdata från när FlowLight-servern efterfrågas. Om du vill kontrollera om en viss annons är en klickningsspårare eller endast klickbar annons kontaktar du antingen din DFA-myndighet eller din Google Support-representant.

## Varför finns det inga klickningar för annonser som visar DFA-klick? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Det kan finnas ett av många svar på detta.

Kontrollera först att annonsen i fråga har en landningssid-URL som båda är (a) taggad med Adobe-kod för samma rapportsvit som du visar avvikelsen i och (b) innehåller frågesträngsparametern *`clickThroughParam`* .

För det andra kontrollerar du att du har en fungerande integrering genom att följa stegen i [Bekräfta en lyckad DFA-integrering](../dfa-data-connector-analytics/dfa-integration.md). Om en DFA-spårningskod visas med Adobe-träffen på landningssidan bör du se att Click-through-koden finns i DFA Campaigns-rapporten. Om du inte ser att det kommer fram kontrollerar du att rapportsviterna matchar landningssidans *`s.account`* variabel och att rapportsviten visas i Rapporter och analyser. Om de här matchar kontrollerar du om det finns spårningskoder i rapporten View Through eVar som ser ut som DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX.

Dessa indikerar fel i DFA VISTA-regeln när rådata från DFA ska samlas. Detta problem kan åtgärdas genom att en supportanmälan öppnas via din Adobe-kontorepresentant.

Om ingen av lösningarna ovan förklarar problemet, se [Avstämning av metriska avvikelser](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) för att utforska andra möjligheter.
