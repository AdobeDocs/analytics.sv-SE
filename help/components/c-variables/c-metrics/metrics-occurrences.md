---
description: Antalet gånger som ett specifikt värde hämtas, plus antalet sidvyer som det angivna värdet bevaras för. Med andra ord är förekomster summan av sidvyer och sidhändelser. Förekomster är tillgängliga i Analysis Workspace och i Ad Hoc Analysis.
title: Förekomster
topic: Metrics
uuid: ff999fba-fcb7-4b16-9446-001facd0f15d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Förekomster

Antalet gånger som ett specifikt värde hämtas, plus antalet sidvyer som det angivna värdet bevaras för. Med andra ord är förekomster summan av sidvyer och sidhändelser. Förekomster är tillgängliga i Analysis Workspace och i Ad Hoc Analysis.

## Jämföra instanser och förekomster {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Två mätvärden som verkar vara lika visas:

**[Instanser](/help/components/c-variables/c-metrics/metrics-instance.md)**: Antalet gånger som ett värde har angetts för en variabel.

**Förekomster**: Det totala antalet gånger som ett värde har angetts eller befunnits.

| Situationen | Beskrivning |
|---|---|
| Förekomster högre än förekomster | Detta förväntas för konverteringsvariabler, eftersom förekomster även innehåller det antal gånger som variabeln definierades (förekomster). |
| Förekomster högre än förekomster | Detta är inte möjligt vid rapportering, eftersom alla instanser också registreras som förekomster. |
| Förekomster som är lika med förekomster | Detta är vanligast för trafikvariabler, eftersom de till sin natur inte finns kvar efter bildbegäran. |

>[!MORELIKETHIS]
>
>* [Instanser](/help/components/c-variables/c-metrics/metrics-instance.md)

