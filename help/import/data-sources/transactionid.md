---
title: Datakällor för transaktions-ID
description: Använd lagrade värden från en onlineträff för att berika offlineträffar som delar ett transaktions-ID.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: 0a65114d598b7c6d2871a2446ad4d574b9ca44bb
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%

---

# Datakällor för transaktions-ID

Datakällor för transaktions-ID är en variant av sammanfattningsdatakällor som gör att du kan använda värden som sparats från en träff online på offline-rader som delar samma transaktions-ID. Detta är användbart när du registrerar en transaktion online men senare får information från ett annat system. Primära exempel är produktreturer, bokningsannulleringar eller resultat från kundtjänstinteraktioner.

>[!NOTE]
>
>Innan du använder datakällor för transaktions-ID måste du aktivera det i [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) för den önskade rapportsviten.

## Så här fungerar det

Konceptet med transaktions-ID kräver två delar:

* **Online-träff**: Alla fullständiga Analytics-träffar skickas till en rapportsvit (AppMeasurement, Web SDK, API osv.). På den här träffen anger du implementeringsvariabeln [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **Offline-träff**: En rad överfördes via datakällor. Inkludera kolumnen `transactionID` i filen med ett värde som matchar en onlineträff.

När du skickar en onlineträff som innehåller implementeringsvariabeln `transactionID` tar Adobe en ögonblicksbild av följande dimensioner som var inställda eller beständiga vid den tidpunkten:

* [Kategori](/help/components/dimensions/category.md)
* [Dagar före första köpet](/help/components/dimensions/days-before-first-purchase.md)
* [Dagar sedan senaste köp](/help/components/dimensions/days-since-last-purchase.md)
* [eVars 1-250](/help/components/dimensions/evar.md)
* Funktionsspecifika dimensioner aktiverade i [Rapportsvitens inställningar](/help/admin/admin/c-manage-report-suites/report-suites-admin.md) som beter sig ungefär som eVars. Funktionsspecifika dimensioner som beter sig ungefär som proppar ingår inte.
* [Listvariabler](/help/implement/vars/page-vars/list.md)
* [Marknadsföringskanal](/help/components/dimensions/marketing-channel.md)
* [Marknadskanalsdetaljer](/help/components/dimensions/marketing-detail.md)
* [Mobila dimensioner](/help/components/dimensions/mobile-dimensions.md)
* [Ursprunglig hänvisande domän](/help/components/dimensions/original-referring-domain.md)
* [Produkt](/help/components/dimensions/product.md)
* [Refererande domän](/help/components/dimensions/referring-domain.md)
* [Sökmotor](/help/components/dimensions/search-engine.md)
* [Söknyckelord](/help/components/dimensions/search-keyword.md)
* [Spårningskod](/help/components/dimensions/tracking-code.md)
* [Besöksnummer](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>Mätvärden (till exempel [Beställningar](/help/components/metrics/orders.md) eller [Anpassade händelser](/help/components/metrics/custom-events.md)) ingår inte i ögonblicksbilden.

När du överför en offlineträff via datakällor som innehåller ett matchande transaktions-ID läggs alla tillgängliga dimensioner i ögonblicksbilden automatiskt till på datakällraden. Om en viss dimension förekommer i både online- och offlineträffen används offlineträffvärdet.

>[!IMPORTANT]
>
>Begreppet med datakällor för transaktions-ID hjälper bara till att fylla i datakällrader (offlineträffar). De påverkar inte eller ändrar inte onlineträffen.

## Överväganden för datakälla för transaktions-ID

Transaktions-ID-datakällor har följande egenskaper:

* Onlinedata måste samlas in och behandlas först. Om en transaktions-ID-datakälla överförs innan en rapportserie bearbetar en träff som matchar detta transaktions-ID behandlas data som en sammanfattningsdatakälla.
* Transaktions-ID:n som samlats in från onlineträffar går ut efter 25 månader.
* Datakällor som har överförts med ett transaktions-ID som har gått ut behandlas på liknande sätt som data som har överförts utan ett transaktions-ID.
* Om du anger samma transaktions-ID för flera onlineträffar används endast den första förekomstens&quot;ögonblicksbild&quot;. Efterföljande duplicerade transaktions-ID-onlineträffar behandlas som om de inte hade något transaktions-ID.
* När du har fyllt i ett angivet `transactionID`-värde anses den associerade ögonblicksbilden som oföränderlig tills transaktions-ID:t upphör att gälla.
* Om du anger samma transaktions-ID på flera datakällrader läggs alla tillgängliga dimensioner från onlineträffen till i varje offlineträff. Offlineträffar för samma transaktions-ID vet ingenting om varandra. Data skickas inte mellan offlineträffar.
