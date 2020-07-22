---
title: Prop
description: En anpassad dimension som du kan använda vid rapportering.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---


# Prop

*Den här hjälpsidan beskriver hur utkast fungerar som en dimension. Mer information om hur du implementerar[uttryck finns](/help/implement/vars/page-vars/prop.md)i Implementera användarhandbok.*

Props är anpassade variabler som du kan använda hur du vill. De finns inte kvar efter den träff de har ställts in.

>[!TIP]
>
>Adobe rekommenderar att du använder [eVars](evar.md) i de flesta fall. I tidigare versioner av Adobe Analytics hade props och eVars fördelar och nackdelar för varandra. Adobe har dock förbättrat eVars så att de fyller i nästan alla användningsområden för proppar.

Om du har ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md)kan du tilldela dessa anpassade dimensioner till värden som är specifika för din organisation. Hur många som är tillgängliga beror på ditt avtal med Adobe. Upp till 75 props finns om ditt avtal med Adobe ger support.

## Fylla i uttryck med data

Varje prop samlar in data från frågesträngen [`c1` - `c75` i bildbegäranden](/help/implement/validate/query-parameters.md) . Frågesträngsparametern samlar till exempel in data för prop1, medan frågesträngsparametern samlar in data för prop68 `c1` `c68` .

AppMeasurement, som kompilerar JavaScript-variabler till en bildbegäran för datainsamling, använder variablerna `prop1` - `prop75`. Mer information om implementeringsriktlinjer finns i [beskrivningen](/help/implement/vars/page-vars/prop.md) i Implementera användarhandbok.

## Dimensionsobjekt

Eftersom utkast innehåller anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekt som finns för varje steg. Se till att du registrerar syftet med varje utkast och typiska dimensionsobjekt i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).

## Värde för uttryck över eVars

Adobe rekommenderar att du använder eVars i de flesta fall. Undantag från den här programsatsen är följande:

* Du kan använda props i realtidsrapporter. Det tar minst 30 minuter för variablerna att visas i rapporteringen.
* Props kan bli listruteförvrängningar, som accepterar flera värden i samma träff. Listvariabler är en separat variabel och det finns bara tre listvariabler tillgängliga.
* När du aktiverar panorering på en propp blir dimensionerna [Inmatning](entry-dimensions.md) och [Avslut](exit-dimensions.md) omedelbart tillgängliga. Om du vill ange in- och avslutningsdimensioner för eVars kan du skapa ett segment manuellt.

Se [eVar](evar.md) för fler jämförelser mellan utkast och eVars.
