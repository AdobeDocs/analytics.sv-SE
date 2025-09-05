---
title: Vanliga frågor om datakällor
description: Vanliga frågor om datakällor.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# Vanliga frågor om datakällor

Vanliga frågor om datakällor.

+++Vad kostar det att använda datakällor?
Datakällor medför inga avgifter och räknar inte heller med användning av serversamtal. [Datakällor med fullständig bearbetning](full-processing-eol.md) har räknats med serveranrop innan de tas ur bruk.
+++

+++Hur påverkar datakällor attribuering och förfallodatum för eVars?
Datakällor har ingen typ av attribuering eller förfallodatum.
+++

+++Hur påverkar datakällor mätvärden som sidvisningar, besök eller unika besökare?
Data som överförs via datakällor påverkar inte [sidvisningar](/help/components/metrics/page-views.md), [besök](/help/components/metrics/visits.md) eller [unika besökare](/help/components/metrics/unique-visitors.md) på något sätt. Det enda standardmått som de påverkar är [förekomster](/help/components/metrics/occurrences.md).
+++

+++Körs data som överförs via datakällor genom ytterligare bearbetning, som bearbetningsregler?
Nej. Data överförda via datakällor:

* Går inte igenom [Bearbetar regler](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
* Går inte igenom [Bearbetningsregler för marknadsföringskanaler](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
* Går inte igenom [VISTA-regler](/help/technotes/vista.md)
+++

+++Kan jag ta bort data som har importerats från datakällor?
Ja. Du kan ta bort dessa data med [API:t för datareparation](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/). Adobe rekommenderar starkt att du överför data från datakällor till en testrapportssvit innan du överför den till en produktionsrapportsvit för att minska behovet av att ta bort data.
+++

+++Hur mycket data kan jag importera samtidigt?
Bearbetningen pausas om storleken överstiger 50 MB och inte återupptas förrän summan är under 50 MB. Kontrollera att den totala storleken för alla filer på FTP-platsen är mindre än 50 MB.
+++

+++Vad händer om jag skickar negativa värden till rapporter via datakällor?
Värdet minskas därefter. Vissa organisationer använder negativa värden för datakällor för att försöka korrigera data. Negativa datakällvärden kan påverka rapporter på potentiellt oönskade eller oväntade sätt. Adobe rekommenderar att du bara använder negativa värden i datakällor som en sista utväg.
+++

+++Är filtilläggen skiftlägeskänsliga?
Ja. Filer med filnamnstillägget `.TXT` eller `.FIN` bearbetas inte. Kontrollera att alla filtillägg är gemener.
+++

+++Hur många kolumner kan jag lägga till i en datakällfil?
Du kan inkludera så många kolumner som du vill i en datakällfil, om alla kolumner är giltiga. En lista med giltiga variabel-/kolumnnamn finns i [Filformat](file-format.md).
+++

+++Kan jag använda datakällor utan att använda den FTP-plats som tillhandahålls av Adobe?
Du kan använda [API:t för datakällor](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/) som gör att du kan skicka API-anrop direkt till Adobe. Dessa API-anrop innehåller en `UploadData`-metod som gör att du kan skicka data via en JSON-objektnyttolast.
+++
