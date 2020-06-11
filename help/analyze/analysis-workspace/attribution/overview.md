---
title: Översikt över attribuering
description: Konceptet för att attribuera kredit för en lyckad händelse till flera dimensionsvärden.
translation-type: tm+mt
source-git-commit: 53f5c4273a7621f3b447e36b19010a797e4ddffe
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 1%

---


# Översikt över attribuering

Attribution ger analytiker möjlighet att anpassa hur dimensionsvärden får kredit för lyckade händelser. Exempel:

1. En besökare på webbplatsen klickar på en betalsöklänk till en av dina produktsidor. Lägg produkten i kundvagnen, men köp den inte.
2. Nästa dag ser du ett inlägg på sociala medier från en av deras vänner, klickar på länken och slutför sedan köpet.

I vissa rapporter kanske du vill ha den beställning som är kopplad till betald sökning. I andra rapporter kanske du vill att ordern ska tillskrivas Social. Attribution låter dig styra den här aspekten av rapportering. Det är tillgängligt för alla organisationer med Adobe Analytics Ultimate, Prime, Select och Foundation. Om du är osäker på vilken typ av kontrakt du har med Adobe kontaktar du din organisations Account Manager.

## Värde för attribuerings-IQ

En viss kundresa är inte linjär och ofta oförutsägbar. Varje kund går i sin egen takt. ofta används andra icke-linjära beteenden som att de backa, stall, startar om eller deltar i andra beteenden. Dessa organiska åtgärder gör det svårt att veta hur marknadsföringen påverkar hela kundresan. Det hämmar också arbetet med att knyta samman flera kanaler med data.

![Attributets IQ-problem](assets/attribution_iq_problem.png)

Adobe Analytics förbättrar attribueringen genom att ni kan:

* Definiera attribuering bortom betalda medier: Alla dimensioner, mätvärden, kanaler och händelser kan tillämpas på modeller (t.ex. intern sökning), inte bara marknadsföringskampanjer.
* Använd obegränsad jämförelse av attribueringsmodell: jämför dynamiskt så många modeller du vill.
* Undvik implementeringsändringar: Med rapporttidshantering och sammanhangsberoende sessioner kan kundresan byggas in och tillämpas vid körning.
* Skapa den session som bäst matchar ditt attribueringsscenario.
* Dela upp attribuering efter segment: Jämför enkelt resultatet i era marknadsföringskanaler i alla viktiga segment (t.ex. nya jämfört med upprepade kunder, produkt X jämfört med produkt Y, lojalitetsnivå eller CLV).
* Inspektera kanalöverskridande analys och multitouch-analys: Använd Venndiagram och histogram samt trendattribueringsresultat.
* Analysera viktiga marknadsföringssekvenser visuellt: utforska banor som leder till visuell konvertering med flernodsflöde och visualiseringar av bortfall.
* Skapa beräknade värden: använda valfritt antal allokeringsmetoder för attribuering.

## Funktioner

Attribution IQ omfattar följande funktioner:

* [Attribution panel](../c-panels/attribution.md): Utnyttja alla dimensioner och mätvärden och jämför dem snabbt med olika attribueringsmodeller.
* [Tillämpa attribuering på ett mätvärde](../build-workspace-project/column-row-settings/column-settings.md): Använd en icke-standardattribuering för alla mätvärden i ett projekt.
* [Tillämpa attribuering på en fördelning](../components/dimensions/t-breakdown-fa.md): Använd en icke-standardattribuering vid en uppdelning.
* [Jämför attribueringsmodeller](../components/apply-create-metrics.md): Se snabbt hur olika attribueringsmodeller jämför olika mätvärden.
