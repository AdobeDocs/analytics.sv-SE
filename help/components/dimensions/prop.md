---
title: Prop
description: En anpassad dimension som du kan använda vid rapportering.
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Prop

*Den här hjälpsidan beskriver hur utkast fungerar som en [dimension](overview.md). Mer information om hur du implementerar uttryck finns i [props](/help/implement/vars/page-vars/prop.md) i användarhandboken för implementering.*

Props är anpassade variabler som du kan använda hur du vill. De finns inte kvar efter den träff de har ställts in.

>[!TIP]
>
>Adobe rekommenderar att du använder [eVars](evar.md) i de flesta fall. I tidigare versioner av Adobe Analytics hade props och eVars fördelar och nackdelar för varandra. Adobe har dock förbättrat eVars så att de fyller i nästan alla användningsområden för proppar.

Om du har ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md) kan du tilldela dessa anpassade dimensioner till värden som är specifika för din organisation. Antalet tillgängliga props beror på ditt kontrakt med Adobe. Upp till 75 props finns om ditt avtal med Adobe stöder det.

## Fylla i uttryck med data

Varje utkast samlar in data från [`c1` - `c75` frågesträngen &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden. Frågesträngsparametern `c1` samlar till exempel in data för prop1, medan frågesträngsparametern `c68` samlar in data för prop68.

AppMeasurementet, som kompilerar JavaScript-variabler till en bildbegäran för datainsamling, använder variablerna `prop1` - `prop75`. Mer information om implementeringsriktlinjer finns i [prop](/help/implement/vars/page-vars/prop.md) i Implementeringsanvändarhandboken.

## Dimensioner

Eftersom utkast innehåller anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekt som finns för varje steg. Se till att du registrerar syftet med varje utkast och typiska dimensionsobjekt i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).

## Skiftlägeskänslighet

Props är som standard inte skiftlägeskänsliga. Om du skickar samma värde i olika fall (till exempel `"DOG"` och `"Dog"`) grupperar Analysis Workspace dem tillsammans i samma dimensionsobjekt. Det fall där det första värdet som anges i början av rapportmånaden används. Datan Warehouse visar det första värdet som påträffades under begärandeperioden.

Du kan göra vilket som helst skiftlägeskänsligt. Du kan även inaktivera skiftlägeskänslighet för alla uttryck när det är aktiverat. Kontakta Adobe kundtjänst med rapportsvitens-ID och de variabler du vill använda för att växla skiftlägeskänslighet.

>[!WARNING]
>
>Växla skiftlägeskänslighet kan klippa ut dimensionsobjekt, skapa oväntade resultat med segment och orsaka problem med filter. Adobe rekommenderar starkt att du växlar den här inställningen mellan två större tidsperioder, till exempel början av en månad eller ett år.

## Värde för uttryck över eVars

Adobe rekommenderar att du använder eVars i de flesta fall. Undantag från den här programsatsen är följande:

* Du kan använda props i realtidsrapporter. Det tar minst 30 minuter för variablerna att visas i rapporteringen.
* Props kan bli listruteförvrängningar, som accepterar flera värden i samma träff. Listvariabler är en separat variabel och det finns bara tre listvariabler tillgängliga.
* När du aktiverar målning för ett utkast blir dimensionerna [Ingång](entry-dimensions.md) och [Avslut](exit-dimensions.md) omedelbart tillgängliga. Om du vill ange in- och avslutningsdimensioner för eVars kan du skapa ett segment manuellt.

Se [eVar](evar.md) för fler jämförelser mellan utkast och eVars.
