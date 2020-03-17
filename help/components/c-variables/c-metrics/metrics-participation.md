---
description: Deltagandestatistik tilldelar fullständig tillgodoräknande av lyckade händelser till alla värden för en eVar som godkändes under ett besök. Deltagandestatistik är användbar för att avgöra vilka sidor, kampanjer eller andra anpassade variabelvärden som mest bidrar till webbplatsens framgång. Deltagandet sker via besök. Alla eVar-värden i ett besök före och inklusive träffen när en händelse inträffar får deltagarkrediter oavsett förfalloinställningen.
title: deltagande
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# deltagande

Deltagandestatistik tilldelar fullständig tillgodoräknande av lyckade händelser till alla värden för en eVar som godkändes under ett besök. Deltagandestatistik är användbar för att avgöra vilka sidor, kampanjer eller andra anpassade variabelvärden som mest bidrar till webbplatsens framgång. Deltagandet sker via besök. Alla eVar-värden i ett besök före och inklusive träffen när en händelse inträffar får deltagarkrediter oavsett förfalloinställningen.

Mer information om hur Ad Hoc Analysis använder deltagandet finns i [Besökardeltagande - Ad Hoc-analys](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) .

Deltagandestatistik har två inställningar per konverteringshändelse:

* **Inaktiverad**: Standardläget för varje konverteringshändelse. Deltagandedata samlas inte in för det här evenemanget.
* **Aktiverad**: Deltagandedata samlas in för det här evenemanget.

> [!NOTE] Du kan aktivera deltagande för upp till 100 anpassade händelser. Utöver detta kan du skapa deltagarvärden i [verktyget för beräkning av](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html) statistik.

När detta är aktiverat blir deltagarstatistik automatiskt tillgänglig i alla konverteringsrapporter. Deltagandestatistik kan dock även visas i specifika trafikrapporter på din begäran. Du kan också begära att deltagarstatistik ska vara tillgänglig i vissa anpassade trafikrapporter.

## Exempel på intäktsdeltagande {#section_DAB6C348201B454BB4ED01313AA777AF}

Anta följande sekvens:

1. En användare navigerar till din webbplats och söker efter &quot;skor&quot;.
1. Användaren söker sedan efter &quot;tennisskor&quot;.
1. Användaren klickar på en länk till produktsidan, lägger till artikeln i kundvagnen och gör ett köp på 120 USD.

När du visar Intäkter i rapporten för interna sökvillkor ser du följande baserat på den valda allokeringen:

* **Första**: &quot;skor&quot; skulle få beröm för 120 dollar. &quot;tennisskor&quot; skulle få $0.
* **Sista**: &quot;tennisskor&quot; skulle få beröm för 120 dollar. &quot;skor&quot; skulle få $0.
* **Linjär**: Varje kampanj skulle få 60 dollar i kredit.

   Deltagandet liknar linjär tilldelning, förutom att fullständig kredit ges till alla värden. Om du använder Intäkter (Deltagande) som mått beaktas inte allokeringen. Intäkter (deltagande) i det här exemplet skulle rapportera 120 USD för båda söktermerna.

>[!MORELIKETHIS]
>
>* [Måttberäkningar](/help/components/c-variables/c-metrics/metrics-calculations.md)

