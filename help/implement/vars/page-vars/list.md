---
title: lista
description: Anpassade variabler som innehåller flera värden i samma träff.
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# lista

Listvariabler är anpassade variabler som du kan använda hur du vill. De fungerar på liknande sätt som eVars, förutom att de kan innehålla flera värden i samma träff. Listvariabler har ingen teckengräns.

Se till att du spelar in hur du använder varje listvariabel och deras logik i [lösningsdesigndokumentet](../../prepare/solution-design.md).

>[!NOTE]
>
>Listvariabler lagrar de senaste 250 värdena per besökare. Om det finns mer än 250 unika värden för en viss besökare, tillskrivs de äldsta värdena inte mätvärden.

## Ställ in listvariabler i rapportsvitens inställningar

Se till att du konfigurerar varje listvariabel i inställningarna för rapportsviten innan du använder dem i implementeringen. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/list-var-admin.md) i Admin Guide.

## Visa variabler med hjälp av taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.list1 - s.list3 i AppMeasurement och anpassad kodredigerare

Varje listvariabel är en sträng som innehåller anpassade värden som är specifika för din organisation. De har inte ett högsta antal byte. Varje värde får dock innehålla högst 255 byte. Avgränsaren som du använder bestäms när du ställer in variabeln i inställningarna för rapportsviten. Använd inte blanksteg när du avgränsar flera objekt.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Om du anger dubblettvärden i samma träff dupliceras alla instanser av dessa värden med Adobe. Om du till exempel anger `s.list1 = "Example,Example";` räknas en instans i rapporter.

## Jämför listekurser med listvariabler

Listutkast och listvariabler kan båda innehålla flera värden i samma träff. Det finns dock flera viktiga skillnader mellan dessa två variabeltyper.

* Alla propp kan bli en listpropp. Du kan ha upp till 75 proppar i listan om varje propp är en listprop. Det finns bara tre listvar tillgängliga.
* Listutkast har en gräns på 100 byte för hela variabeln. Listvariabler har en gräns på 255 byte per värde och ingen total bytegräns.
* Listproppar finns inte kvar efter den träff de ställs in. Listvariabler har en förfalloinställning som du vill ha. Med [rapporttidsbearbetning](/help/components/vrs/vrs-report-time-processing.md) kan du dock använda anpassad attribuering på både listutkast och listvariabler.
