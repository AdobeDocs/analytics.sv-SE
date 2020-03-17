---
description: Här är några vanliga fallgropar när du använder Report Builder med Power BI.
title: Felsökning av Power BI-integrering
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Felsökning av Power BI-integrering

Här är några vanliga fallgropar när du använder Report Builder med Power BI.

## Steg 1. Det gick inte att publicera till Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Schemalagda arbetsböcker som kräver Power BI-publicering är beroende av att Power BI-tjänster är igång. Två huvudorsaker till att publiceringen inte lyckas är:

* Power BI-tjänster kan vara avstängda.
* Användaren som har schemalagt arbetsboken har inte längre giltiga autentiseringsuppgifter för Microsoft-kontot.

Varje schemalagd aktivitet i Report Builder får tre försök per schemalagd körning:

* Efter det första misslyckade försöket får du följande meddelande: &quot;&quot;Det gick inte att publicera den schemalagda arbetsboken till Microsoft Power BI. Vi kommer att försöka igen inom kort.&quot;
* Efter det andra misslyckade försöket får du inget meddelande.
* Efter det tredje misslyckade försöket får du följande meddelande: &quot;Det gick inte att publicera den här arbetsboken till Power BI.&quot;

## Steg 2. Brutna visualiseringar i Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Här följer de viktigaste skälen till att du kan få brutna visualiseringar efter att ha publicerat Report Builder-begäranden till Power BI:

* Du redigerade en begäran i Report Builder, t.ex. ändrade mått eller mått, och publicerade sedan om den till Power BI. Om du redigerar begäranden kan visualiseringarna gå förlorade.
* Du tog bort en begäran som användes i en visualisering.

