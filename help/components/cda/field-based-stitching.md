---
title: Fältbaserad stygn
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med fältbaserad sammanfogning.
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# Fältbaserad stygn

Enhetsövergripande analys erbjuder två olika metoder för att sammanfoga data. Den här metoden är beroende av en Analytics-variabel, som [prop](/help/implement/vars/page-vars/prop.md) eller [eVar](/help/implement/vars/page-vars/evar.md), som innehåller en personidentifierare. Den använder den variabeln som bas för att länka samman enheter. Adobe rekommenderar detta sammanfogningsalternativ för större genomskinlighet och mer förutsägbarhet i besöksspårning.

## Krav som är specifika för fältbaserad sammanfogning

Om du tänker implementera enhetsövergripande analys med fältbaserad sammanfogning krävs följande. Arbeta med team inom organisationen och kontoteamet på Adobe för att säkerställa att ni uppfyller alla följande.

>[!WARNING]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när du sammanfogar data.

* Alla krav som anges på [översiktssida](overview.md).
* Implementeringen måste ange ett utkast eller en eVar som unikt identifierar en individ när det är möjligt, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Undvik att tilldela ett standardvärde till säljaren eller eVarna.
* Kommunicera den önskade identifieringsvariabeln till ditt Adobe-kontoteam när den tillhandahålls för fältbaserad sammanslagning.

## Begränsningar som är specifika för fältbaserad sammanfogning

* Fältbaserad sammanfogning fungerar bäst på rapportsviter med hög användaridentifierings-/autentiseringsfrekvens.
* Även om props och eVars har regler för hur versaler och gemener hanteras i rapporteringssyfte, omformas inte propen eller eVar som används för att fästa ihop på något sätt. Fältbaserad sammanfogning använder värdet i det angivna fältet så som det finns efter VISTA-regler och regler för efterbearbetning. Smältningsprocessen är skiftlägeskänslig. Om ibland ordet &#39;Bob&#39; visas i utkastet/eVarna och ibland ordet &#39;BOB&#39; visas, behandlas dessa som två separata personer genom sammanfogningsprocessen.
* Med tanke på att fältbaserad sammanfogning är skiftlägeskänslig rekommenderar Adobe att man granskar VISTA-regler eller bearbetningsregler som gäller för det utkast eller den eVar som används för fältbaserad sammanfogning. De måste granskas för att säkerställa att ingen av dessa regler inför nya formulär med samma ID. Du bör t.ex. se till att inga VISTA-regler eller bearbetningsregler för endast en del av träffarna medför lägre radering av proppen eller eVarna.
* Fältbaserad sammanfogning stöder inte användning av mer än en prop eller eVar för sammanfogning. Om eVar12 till exempel innehåller inloggnings-ID och eVar20 innehåller e-post-ID måste du välja ett av dem.
* Fältbaserad sammanfogning varken kombinerar eller sammanfogar fält (t.ex. eVar10 + prop5).
* Kortet eller eVarna ska innehålla en enda typ av ID. Kortet eller eVarna får till exempel inte innehålla en kombination av inloggnings-ID och e-post-ID.
* Om flera träffar inträffar med samma tidsstämpel för samma besökare, men med olika värden i sömningsproppen eller eVarna, väljer CDA i alfabetisk ordning. Om besökare A har två träffar med samma tidsstämpel och en av träffarna anger Bob och den andra anger Ann, väljer CDA Ann.


## Nästa steg

När organisationen uppfyller alla krav och förstår begränsningarna kan du börja [Konfigurera enhetsövergripande analys](setup.md).
