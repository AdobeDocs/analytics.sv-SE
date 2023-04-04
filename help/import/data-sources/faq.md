---
title: Vanliga frågor om datakällor
description: Vanliga frågor och svar om datakällor.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Vanliga frågor om datakällor

Vanliga frågor och svar om datakällor.

+++Vad kostar det att använda datakällor?
Datakällor medför inga avgifter och räknar inte heller med användning av serversamtal. [Datakällor med fullständig bearbetning](full-processing-eol.md) räknade med serversamtal innan de gick i pension.
+++

+++Hur påverkar datakällor attribuering och förfallodatum för eVars?
Om ett transaktionsID matchar mellan en datakälla och en onlineträff får de associerade eVar samma attribuering och förfallodatum som om de hade angetts vid onlinetötet.

Alla andra data som överförs via datakällor har ingen form av attribuering eller förfallodatum.
+++

+++Hur påverkar datakällor standardvärden, som sidvisningar, besök eller unika besökare?
Data som överförs via datakällor påverkar inte [Sidvyer](/help/components/metrics/page-views.md), [Besök](/help/components/metrics/visits.md), eller [Unika besökare](/help/components/metrics/unique-visitors.md) på något sätt. Det enda standardmåttet som påverkar inkluderar [Förekomster](/help/components/metrics/occurrences.md).
+++

+++Kan jag ta bort data som har importerats från datakällor?

**Nej.** Data som överförs till rapporter med datakällor är **permanent**. Den kan inte tas bort, inte ens av Adobe, när den har importerats. Adobe rekommenderar starkt att du överför data från datakällor till en testrapportssvit innan du överför den till en produktionsrapportsvit.
+++

+++Hur mycket data kan jag importera samtidigt?

Bearbetningen pausas om storleken överstiger 50 MB och inte återupptas förrän summan är under 50 MB. Kontrollera att den totala storleken för alla filer på FTP-platsen är mindre än 50 MB.
+++

+++Vad händer om jag skickar negativa värden till rapporter via datakällor?

Värdet minskas därefter. Vissa organisationer använder negativa värden för datakällor för att försöka korrigera data. Negativa datakällvärden kan påverka rapporter på potentiellt oönskade eller oväntade sätt. Adobe rekommenderar att du bara använder negativa datakällor som en sista utväg.
+++

+++Är filtilläggen skiftlägeskänsliga?
Ja. Filer med filnamnstillägget `.TXT` eller `.FIN` bearbetas inte. Kontrollera att alla filtillägg är gemener.
+++

+++Hur många kolumner kan jag lägga till i en datakällfil?
Du kan inkludera så många kolumner som du vill i en datakällfil, om alla kolumner är giltiga. Se [Filformat](file-format.md) för en lista med giltiga variabel-/kolumnnamn.
+++

+++Kan jag använda datakällor utan att använda FTP-platsen som tillhandahålls av Adobe?
Du kan använda [API för datakällor](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), som gör att du kan skicka API-anrop direkt till Adobe. Dessa API-anrop innehåller en `UploadData` som gör att du kan skicka data med en JSON-objektnyttolast.
+++
