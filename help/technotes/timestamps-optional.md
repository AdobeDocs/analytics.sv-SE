---
description: Läs mer om fördelarna och begränsningarna med att använda inställningen Tidsstämplar (valfritt).
keywords: Implementering av analyser
title: Tidsstämplar (valfritt)
topic-fix: Developer and implementation
feature: Implementation Basics
exl-id: c6a232d1-d7ce-4f21-9e8a-45703992bc6e
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# Tidsstämplar (valfritt)

Läs mer om fördelarna och begränsningarna med att använda inställningen Tidsstämplar (valfritt).

<!-- Hide video as it is not adding a lot according to feedback from customer in feedback report January 2025.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Timestamps Optional](https://video.tv.adobe.com/v/335740?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]
-->


Tidsstämplar Valfria är standardinställningen för alla nya rapportsviter.

* Blanda tidsstämplade och tidsstämplade data i samma globala rapportserie.
* Skicka tidsstämplade data från en mobilapp till en global rapportserie.
* Uppgradera appar för att använda tidsstämplar utan att behöva skapa en ny rapportserie.

>[!NOTE]
>
>Tidsstämplar Valfria är standardinställningen för alla nya rapportsviter som genereras från en mall. Nya rapportsviter som kopierats från en befintlig rapportserie ärver inställningar från originalet.

Se [Tidsstämplar (valfritt)](/help/technotes/timestamps-optional.md) om du vill ha mer installationsinformation.

## Tidsstämplar Valfritt: Integrera tidsstämplade och tidsstämplade data {#integrate}

Med funktionen Tidsstämplar (valfritt) kan du kombinera icke-tidsstämplade data med tidsstämplade data utan att data går förlorade. Offlinedata med tidsstämplar som genererats från en mobil enhet kan kombineras med live, tidstämplade data från en webbsida - eller integreras med data från vilken plattform som helst med ett tidsstämpelanrop på klientsidan.

* **Tidsstämpeldata**. Tidsstämpeldata på klientsidan hämtas och skickas direkt med enhetsdata med hjälp av klientsidans tidsstämpelvariabler: Javascript på en webbsida eller med ett Mobile SDK-anrop ( [!DNL offlineEnabled=true]) i en mobilapp.
* **Ej tidsstämpeldata**. Adobe sätter en tidsstämpel på data som inte är tidsstämplade i en rapportsvit när data träffar samlingsservrarna.

En rapportsvit kan ha någon av följande tidsstämpelinställningar:

* Tidsstämplar tillåts inte (stöd för inställning av visitorID)
* Tidsstämplar krävs (inställning av visitorID stöds inte)
* Tidsstämplar är valfria (ange besökarID stöds men inte för tidsstämplade träffar)

## Om Tidsstämplar Valfria funktioner {#features}

Tidsstämplar Valfritt gör att du kan integrera och rapportera i flera rapportsviter med eller utan tidsstämplar på klientsidan. Med Tidsstämplar Valfritt kan du uppdatera appen så att den använder tidsstämplar medan du fortfarande använder data som inte är tidsstämplade från den tidigare appen.

| I tidigare versioner... | Dessutom... |
|--- |--- |
| Det gick inte att skicka tidsstämplade data till en global rapportserie som inte är tidsstämplad. Följaktligen släpptes träffdata som skickades från offlineenheter när de lades till i en rapportserie som inte är tidsstämplad. <br/><br/>Följaktligen togs träffdata som skickades från offlinedata bort när de lades till i en rapportserie som inte är tidsstämplad. | När du uppdaterar en app för att samla in och använda tidsstämplar måste du använda en ny rapportserie. <br/>Det gick inte att spara till den befintliga rapportsviten eller integrera befintliga data när appen uppdaterades för att använda tidsstämplar. |

**Med tidsstämplar (valfritt)** kan du integrera data som inte är tidsstämplade från en aktiv webbplats med offlinedata från mobila enheter, eller uppdatera en app som inte är tidsstämplad till en tidsstämplad app.

## Kombinera data i en Global Report Suite {#combine}

Att kombinera data i en global rapportserie kan göras på flera sätt, inklusive märkning med flera programsviter, Vista-regler och importerade batchfiler från offlinekällor.

>[!IMPORTANT]
>
>Planera noggrant designen för varje komponentdatauppsättning så att kombinationen passar i en global rapportserie.

## Bästa tillvägagångssätt vid användning av tidsstämplar {#best-pratices}

Nedan följer god praxis och några krav och begränsningar som du bör känna till när du integrerar tidsstämplade data med data som inte är tidsstämplade.

* I allmänhet måste tidsstämplar för en viss besökare eller besök anlända till Adobe i rätt kronologisk ordning.

  Data som inte är i ordning kan omfatta sena data från offlinedatainsamling och sena träffar, eller osynkroniserade klockor på offline-mobilenheter. Obeställda data kan påverka tidsberäkningar negativt (t.ex. tidsåtgång), attribuering (eVar persistence), antal besök/besök samt rapporter om kundvägar.

* Du bör inte använda tidsstämplar när du anger ett [s.visitorID](/help/implement/vars/config-vars/visitorid.md). Det kan leda till oordnade data.

* Hybridappar som består av en app (tidsstämplade, offlinedata) som öppnar en webbläsare (utan tidsstämpel, livedata) bör inte använda tidsstämplar. Det resulterar i felaktig rapportering av sessionen.

  Dessutom bör hybridappar inte ange ett besökar-ID.
