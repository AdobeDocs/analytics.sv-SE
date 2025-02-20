---
title: Fältbaserad stygn
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med fältbaserad sammanfogning.
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
feature: CDA
role: Admin
source-git-commit: 5faf1631a52594591a74a93868198da8bc0f9cff
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# Fältbaserad stygn

{{available-existing-customers}}

Enhetsövergripande analys erbjuder två olika metoder för att sammanfoga data. Den här metoden är beroende av en Analytics-variabel, som [prop](/help/implement/vars/page-vars/prop.md) eller [eVar](/help/implement/vars/page-vars/evar.md) , som innehåller en person-ID. Den använder den variabeln som bas för att länka samman enheter. Adobe rekommenderar detta sammanfogningsalternativ för större genomskinlighet och större förutsägbarhet när det gäller besökarspårning.

## Krav som är specifika för fältbaserad sammanfogning

Om du tänker implementera enhetsövergripande analys med fältbaserad sammanfogning krävs följande. Samarbeta med team i er organisation och i er kontogrupp på Adobe för att säkerställa att ni uppfyller alla följande krav.

>[!WARNING]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när du sammanfogar data.

* Alla krav som anges på [översiktssidan](overview.md).
* Implementeringen måste ange en prop eller eVar som unikt identifierar en individ när det är möjligt, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används.<br/>Undvik att tilldela ett standardvärde till det här proffset eller eVar. När 2 000 eller fler olika enheter tilldelas samma standardvärde läggs personen till i en&quot;dålig person&quot;-lista och dessa händelser tas bort från den virtuella rapportsviten som aktiverats för CDA, vilket resulterar i felaktig analys.
* Informera ditt Adobe-kontoteam om den önskade identifieringsvariabeln när den tillhandahålls för fältbaserad sammanfogning.

## Begränsningar som är specifika för fältbaserad sammanfogning

* Fältbaserad sammanfogning fungerar bäst på rapportsviter med hög användaridentifierings-/autentiseringsfrekvens.
* Även om props och eVars har regler för hur versaler och gemener hanteras för rapportering, innebär fältbaserad stygn inte att propen eller eVar som används för stygning omformas på något sätt. Fältbaserad sammanfogning använder värdet i det angivna fältet så som det finns efter VISTA-regler och regler för efterbearbetning. Smältningsprocessen är skiftlägeskänslig. Om ibland ordet &#39;Bob&#39; visas i utkastet/eVar, och ibland ordet &#39;BOB&#39;, kommer dessa att behandlas som två separata personer genom sammanfogningsprocessen.
* Med tanke på att fältbaserad sammanfogning är skiftlägeskänslig rekommenderar Adobe att man granskar VISTA-regler eller bearbetningsregler som gäller för det utkast eller den eVar som används för fältbaserad sammanfogning. De måste granskas för att säkerställa att ingen av dessa regler inför nya formulär med samma ID. Du bör t.ex. se till att inga VISTA-regler eller bearbetningsregler för endast en del av träffarna kommer att medföra lägre radering av proppen eller eVar.
* Fältbaserad stygn stöder inte användning av mer än en prop eller eVar för stygn. Om till exempel eVar12 innehåller inloggnings-ID och eVar20 innehåller e-post-ID måste du välja ett av dem.
* Fältbaserad sammanfogning varken kombinerar eller sammanfogar fält (t.ex. eVar10 + prop5).
* Kortet eller eVar ska innehålla en enda typ av ID. Kortet eller eVar får till exempel inte innehålla en kombination av inloggnings-ID och e-post-ID.
* Om flera träffar inträffar med samma tidsstämpel för samma besökare, men med olika värden i sömningsproppen eller eVar, väljer CDA i alfabetisk ordning. Om besökare A har två träffar med samma tidsstämpel och en av träffarna anger Bob och den andra anger Ann, väljer CDA Ann.


## Nästa steg

När din organisation uppfyller alla krav och förstår begränsningarna kan du starta [Konfigurera Cross-Device Analytics](setup.md).

