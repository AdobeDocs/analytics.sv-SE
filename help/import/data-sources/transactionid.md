---
title: Datakällor för transaktions-ID
description: Lär dig det allmänna arbetsflödet med att använda datakällor för transaktions-ID.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: e281d43204e1c5b10508661f04b880125fe8671c
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---

# Datakällor för transaktions-ID

Datakällor för transaktions-ID är en variation på sammanfattningsdatakällor som gör att du kan koppla samman online- och offlinedata. Det kräver att variabeln [`transactionID`](/help/implement/vars/page-vars/transactionid.md) används i din Analytics-implementering.

* Om en rad i en datakällfil innehåller ett transaktions-ID som matchar ett transaktions-ID som redan samlats in av AppMeasurementet, läggs mått och mått till i onlinesatsen.
* Om en rad i en datakällfil innehåller ett transaktions-ID som inte innehåller någon matchning behandlas raden på samma sätt som sammanfattningsdatakällor.

>[!NOTE]
>
>Innan du använder datakällor för transaktions-ID måste du aktivera det i [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) för den önskade rapportsviten.

När du skickar en onlineträff som innehåller ett [`transactionID`](/help/implement/vars/page-vars/transactionid.md)-värde tar Adobe en ögonblicksbild av alla variabler som angetts eller befunnits sedan. Om ett matchande transaktions-ID som överförts via datakällor hittas knyts offline- och onlinedata ihop.

Transaktions-ID-datakällor har följande egenskaper:

* Onlinedata måste samlas in och behandlas först. Om en transaktions-ID-datakälla överförs innan en rapportserie bearbetar en träff som matchar transaktions-ID:t, länkas inte data.
* Transaktions-ID:n som samlas in via AppMeasurementet går ut efter 25 månader.
* Datakällor som har överförts med ett transaktions-ID som har gått ut behandlas på liknande sätt som data som har överförts utan ett transaktions-ID.
* Om samma variabel ingår i både online-träffen och transaktions-ID-datakällan används värdet från transaktions-ID-datakällan.
* Om en variabel ingår i en onlineträff men inte i en matchande datakällträff för transaktions-ID bevaras träffvariabeln online.
* Om du anger samma transaktions-ID för flera onlineträffar ändras endast den första förekomsten med data från en matchande transaktions-ID-datakälla.
* Om du anger samma transaktions-ID på flera datakällrader för samma dimensioner, används den senaste dimensionsobjektet.

Exempel:

1. Du skickar in en sidvy från AppMeasurementet där:
   * `eVar1` är lika med `blue`
   * `eVar2` är lika med `water`
   * `events` är lika med `event1`
   * `transactionID` är lika med `1256`
2. När träffen har samlats in och bearbetats överför du en transaktions-ID-datakälla där:
   * `eVar1` är lika med `yellow`
   * `eVar3` är lika med `bird`
   * `events` är lika med `event2`
   * `transactionID` är lika med `1256`
3. När datakällorna har träffats visas en rapport på arbetsytan. Data skulle visa följande:
   * `eVar1` är lika med `yellow`
   * `eVar2` är lika med `water`
   * `eVar3` är lika med `bird`
   * `events` är lika med `event2`

EVar1-värdet `blue` och `event1`-måttet finns inte i rapporteringen eftersom transaktions-ID:t skrev över dessa respektive värden.
