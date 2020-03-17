---
description: Läs mer om fördelarna och begränsningarna med att använda inställningen Tidsstämplar (valfritt).
keywords: Analytics Implementation
title: Användning av tidsstämplar som tillval
topic: Developer and implementation
uuid: 956aaa16-6ffa-4b63-b022-a659f5143e00
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Användning av tidsstämplar som tillval

Läs mer om fördelarna och begränsningarna med att använda inställningen Tidsstämplar (valfritt).

Tidsstämplar Valfria är standardinställningen för alla nya rapportsviter.

* Blanda tidsstämplade och tidsstämplade data i samma globala rapportserie.
* Skicka tidsstämplade data från en mobilapp till en global rapportserie.
* Uppgradera appar för att använda tidsstämplar utan att behöva skapa en ny rapportserie.

> [!NOTE] Tidsstämplar Valfria är standardinställningen för alla nya rapportsviter som genereras från en mall. Nya rapportsviter som kopierats från en befintlig rapportserie ärver inställningar från originalet.

Se [Tidsstämplar Valfritt](https://marketing.adobe.com/resources/help/en_US/reference/timestamp-optional.html) om du vill ha mer installationsinformation.

## Valfria tidsstämplar: Integrera tidsstämplade och icke tidsstämplade data {#section_BF17CB593044462B993FD0D28EA56518}

Med funktionen Tidsstämplar (valfritt) kan du kombinera icke-tidsstämplade data med tidsstämplade data utan att data går förlorade. Offlinedata med tidsstämplar som genererats från en mobil enhet kan kombineras med live, tidstämplade data från en webbsida - eller integreras med data från vilken plattform som helst med ett tidsstämpelanrop på klientsidan.

* **Tidsstämpeldata**. Tidsstämpeldata på klientsidan hämtas och skickas direkt med enhetsdata med hjälp av tidsstämpelvariabler på klientsidan: Javascript på en webbsida eller via ett Mobile SDK-anrop ( [!DNL offlineEnabled=true]) i en mobilapp.
* **Ej tidsstämpeldata**. Adobe sätter en tidsstämpel på data som inte är tidsstämplade i en rapportsvit när data träffar samlingsservrarna.


En rapportsvit kan ha någon av följande tidsstämpelinställningar:

* Tidsstämplar tillåts inte (stöd för inställning av visitorID)
* Tidsstämplar krävs (inställning av visitorID stöds inte)
* Tidsstämplar är valfria (ange besökarID stöds men inte för tidsstämplade träffar)

## Om tidsstämplar, valfria funktioner {#section_63B2FA9A2AB24B3993E84D2C2B4BF2CE}

Tidsstämplar Valfritt gör att du kan integrera och rapportera i flera rapportsviter med eller utan tidsstämplar på klientsidan. Med Tidsstämplar Valfritt kan du uppdatera appen så att den använder tidsstämplar medan du fortfarande använder data som inte är tidsstämplade från den tidigare appen.

| I tidigare versioner... | Dessutom... |
|--- |--- |
| Det gick inte att skicka tidsstämplade data till en global rapportserie som inte är tidsstämplad. Följaktligen släpptes träffdata som skickades från offlineenheter när de lades till i en rapportserie som inte är tidsstämplad. <br/><br/>Följaktligen togs träffdata som skickades från offlinedata bort när de lades till i en rapportserie som inte är tidsstämplad. | När du uppdaterar en app för att samla in och använda tidsstämplar måste du använda en ny rapportserie. <br/>Du kunde inte spara till den befintliga rapportsviten eller integrera befintliga data när du uppdaterar appen för att använda tidsstämplar. |

**Med tidsstämplar som valfria** kan du integrera icke-tidsstämplade data från en livewebbplats med offlinedata från mobila enheter, eller uppdatera en tidsstämplad app till en tidsstämplad app.

## Kombinera data i en global rapportsserie {#section_5BE3BDF56007402BB1F5C3144D5FE1E0}

Att kombinera data i en global rapportserie kan göras på flera sätt, inklusive märkning med flera programsviter, Vista-regler och importerade batchfiler från offlinekällor.

> [!IMPORTANT] Planera noggrant designen för varje komponentdatauppsättning så att kombinationen passar i en global rapportserie.

## Bästa tillvägagångssätt vid användning av tidsstämplar {#section_9436394E5D7E4F8A8B369B6D11BB2B2B}

Nedan följer god praxis och några krav och begränsningar som du bör känna till när du integrerar tidsstämplade data med data som inte är tidsstämplade.

* Vanligtvis måste tidsstämplar för en viss besökare eller besök anlända till Adobe i rätt kronologisk ordning.

   Data som inte är i ordning kan omfatta sena data från datainsamling offline och sena träffar, eller osynkroniserade klockor på offline-mobilenheter. Oordnade data kan påverka tidsberäkningar negativt (t.ex. tidsåtgång), attribuering (eVar persistence), antal besök/besök samt kundvägsrapporter.

* Du bör inte använda tidsstämplar när du anger ett [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) . Det kan leda till oordnade data.

* Hybridappar som består av en app (tidsstämplade, offlinedata) som öppnar en webbläsare (utan tidsstämpel, livedata) bör inte använda tidsstämplar. Det resulterar i felaktig rapportering av sessionen.

   Dessutom bör hybridappar inte ange ett besökar-ID.
