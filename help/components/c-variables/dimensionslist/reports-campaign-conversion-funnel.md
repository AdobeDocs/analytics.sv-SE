---
description: Visar medelvärden för mätvärden i rapporteringsgruppen för kampanjer. Standardvärden är klickfrekvens, total försäljning, beställningar och intäkter.
title: Kampanjkonverteringsström
topic: Reports
uuid: b0a90917-e4c7-40da-854e-58649de09742
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Kampanjkonverteringsström

Visar medelvärden för mätvärden i rapporteringsgruppen för kampanjer. Standardvärden är klickfrekvens, total försäljning, beställningar och intäkter.

**[!UICONTROL Campaigns]** > **[!UICONTROL Campaign Conversion Funnel]**

Den översta delen av en trattbild visar konverteringsdata. Nerifrån visas statistik för alla händelser i det övre området, baserat på order och upp till två andra mått, Intäkter och Enheter.

Tänk på följande information när du tolkar konverteringstrattdata:

* Statistik för aktuella tidsperioder kanske inte slutförs när du visar data, vilket kan påverka trender från en tidigare dag till den aktuella.
* När inget filter tillämpas på tratten representerar Visits-mätvärdet konverteringsbesök eller besök där kampanjvariabeln, variabeln eVar eller en success-händelse utlöstes. Besök under vilka ingen av dessa egenskaper skickades till rapporter inkluderas inte i detta totala antal.
* När ett filter används på tratten representerar Visits-måttet instanser (eller klickningar). Detta värde är det totala antalet gånger som den angivna variabeln fylldes i av användare på din plats, exklusive de instanser som inte uppfyller filterkraven. Ett enda besök kan omfatta flera instanser.
* Djupare nivåer i tratten kan rapportera högre tal än lägre nivåer. Du kan till exempel se fler order än klickningar, eller fler utcheckningar än produktvyer. Det finns många skäl till att denna situation uppstår:

   * Du har fler order än klickningar om variabeln Spårningskod är inställd på en lång cookie-förfallotid (till exempel en månad), och användarna bara utför en klickning men returnerar flera gånger och lägger order under perioden, innan värdet för spårningskod går ut.
   * Du har fler utcheckningar än produktvyer om användaren kan hoppa över produktvysidan (som vid en merförsäljningssida) eller om användaren kan spara sin kundvagn och gå tillbaka senare för att slutföra beställningen. Om produktvyn visas före det valda datumintervallet och utcheckningen sedan visas en utcheckning och ingen produktvy alls. Om du upptäcker en sådan diskrepans betyder det inte att du har problem med rapporteringen eller ens ett implementeringsfel. I stället kan ni använda dessa data för att förstå hur användarna interagerar med webbplatsen, även om de inte passar in i tratten på det sätt ni förväntar er.

