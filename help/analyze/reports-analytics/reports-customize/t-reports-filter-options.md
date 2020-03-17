---
description: Med filter kan du begränsa rapporten så att den omfattar eller exkluderar radobjekt som matchar ett filter.
title: Filtrera rapportdata
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrera rapportdata {#concept_09DC5B986A644738B12204DAC76A90E1}

Med filter kan du begränsa rapporten så att den omfattar eller exkluderar radobjekt som matchar ett filter.

## Enkelt filter {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

Det enkla filtret visas i de flesta rapporter så att du snabbt kan hitta specifika radposter. I enkla filter används inga specialtecken, så `-, ", ', +` och andra specialtecken matchar det litterala värdet i rapporten. Du kan söka efter radobjekt som innehåller flera termer med hjälp av ett blanksteg.

Exempel:

```
help search
```

Matchar följande sidor:

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## Avancerade filter {#section_E016626C084640E8A066B2FDA5B932BF}

Med avancerade filter kan du styra omfattningen av sökningen med hjälp av en samling filter. Du kan välja att matcha alla filter eller alla filter.

![](assets/advanced_filter.png)

**Innehåller**

Matchar om termen hittas någonstans i radobjektet. Detta fungerar på samma sätt som det enkla filtret.

> [!NOTE] Blanksteg kan inte användas i filter eftersom blanksteg är avgränsare i sökningar

**Innehåller inte**

Matchar om termen inte hittas någonstans i radobjektet. Du kan filtrera &quot;unspecified&quot;, &quot;none&quot;, &quot;keyword unavailable&quot; och andra [specialvärden](https://marketing.adobe.com/resources/help/en_US/reference/none-unspecified-unknown-other.html) från rapporter med &quot;does not contain&quot;.

Innehåller inte: `none`

För ett mer exakt filter kan du använda ett avancerat specialteckenfilter:

* Avancerat (specialtecken): `-^none$`
* Avancerat (specialtecken): `-"keyword unavailable"`

Följande radobjekt filtreras till exempel av villkoret&quot;Innehåller inte&quot;, men filtreras inte av villkoret&quot;Avancerat (specialtecken)&quot;:

```
help:Rename the None classification key
```

**Innehåller en av**

Matchar om några termer, avgränsade med blanksteg, hittas i radobjektet. Följande filter visar alla sidor som innehåller &quot;men&quot; eller &quot;sales&quot;:

Innehåller en av: `mens sale`

Matchar följande sidor:

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**Lika med**

Matchar om hela radobjektet, inklusive blanksteg och andra tecken, matchar den angivna frasen.

Lika med: `mens:desk & travel`

`Mens:Desk & Travel`

**Börjar med**

Matchar om radobjektet, inklusive blanksteg och andra tecken, börjar med den angivna frasen.

Börjar med: `mens`

Matchar följande sidor:

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Slutar med**

Matchar om radobjektet, inklusive blanksteg och andra tecken, slutar med den angivna frasen.

Slutar med: `jean`

Matchar följande sidor:

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Avancerat (specialtecken) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Med Avancerat kan du utföra jokertecken och andra komplexa sökningar.

| Avancerat (specialtecken) | Beskrivning |
|--- |--- |
| `" "` | Matcha exakt fras. |
| `*` | Vildkort, girig matchning. <br>Matchar till exempel `r*p` &quot;Registrering&quot;. |
| `^` | Börjar med. <br>Använd inte blanksteg mellan specialtecknet och sökfrasen. |
| `$` | Slutar med. <br>Använd inte blanksteg mellan specialtecknet och sökfrasen. |
| `-` | Nej. <br>Använd inte blanksteg mellan specialtecknet och sökfrasen. |
| `|` | <br>OrNote:  Du måste inkludera ett mellanslag på varje sida av lodstreck `" | "`. |

## Skapa rapportspecifika filter {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Steg som beskriver hur du skapar filter för rapporter.

<!-- 

t_reports_filter_specific.xml

 -->

Vissa rapporter innehåller ett filter som är specifikt för den rapporten. Med en [!UICONTROL Purchase Conversion Funnel Report] kan du till exempel filtrera efter webbsidor. Med ett [!UICONTROL Geosegmentation Report] filter kan du filtrera efter geografisk region. Ytterligare rapporter har andra filter som är specifika för dessa rapporter.

När du använder dessa filter kan du visa rapportvärden för de objekt som anges i listan.

**Skapa rapportspecifika filter**

1. Generera en rapport, till exempel en [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. Klicka på **[!UICONTROL Filter]** länken i rapportrubriken.
1. Klicka på [!UICONTROL Filter Selector] sidan **[!UICONTROL Apply a Filter]** och välj sedan en filtertyp.
1. Om du vill söka efter ett objekt skriver du en teckensträng i **[!UICONTROL Search]** fältet.
1. Klicka på **[!UICONTROL OK]**.

## Lägg till ett korrelationsfilter {#task_065042E384DA4BF3864C58AF2B88D6E2}

Steg som beskriver hur du lägger till ett korrelationsfilter.

<!-- 

t_reports_correlation_filter.xml

 -->

I vissa rapporter kan du lägga till anpassade korrelationsfilter. Om du t.ex. visar [!UICONTROL Pages Report] en rapport för en rapportsvit som har platsavsnitt som är kopplade till en kvinnosida, kan du skapa en filterregel som genererar en rapport som visar de vanligaste sidorna när Webbplatsavsnitt = Kvinnor.

Du kan filtrera data som visas i en korrelationsrapport med hjälp av valfri tillgänglig korrelation. Exemplet här visar hur du lägger till ett korrelationsfilter för sökmotor.

**Lägga till ett korrelationsfilter**

1. Kör en rapport som stöder korrelationer. (Se [Köra en fördelningsrapport](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. Klicka på **[!UICONTROL Correlation Filter]** länken i rapportrubriken.
1. Under [!UICONTROL Filter Rule Creator]väljer du en kategori att korrelera med en artikel.
1. Klicka på **[!UICONTROL OK.]**
