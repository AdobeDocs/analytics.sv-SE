---
title: lista
description: Anpassade variabler som innehåller flera värden i samma träff.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: 84a4d38a65769f028bac4aa5817cb4002c4b1f97
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# lista

Listvariabler är anpassade variabler som du kan använda hur du vill. De fungerar på liknande sätt som eVars, förutom att de kan innehålla flera värden i samma träff. Listvariabler har ingen teckengräns.

Se till att du spelar in hur du använder varje listvariabel och deras logik i [konstruktionsdokument](../../prepare/solution-design.md).

>[!NOTE]
>
>Listvariabler lagrar de senaste 250 värdena per besökare. Om det finns mer än 250 unika värden för en viss besökare, tillskrivs de äldsta värdena inte mätvärden.

## Ställ in listvariabler i rapportsvitens inställningar

Se till att du konfigurerar varje listvariabel i inställningarna för rapportsviten innan du använder dem i implementeringen. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md) i administrationshandboken. Det här steget gäller alla implementeringsmetoder.

## Visa variabler med Web SDK

Listvariabler är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fälten `_experience.analytics.customDimensions.lists.list1.list[]` till `_experience.analytics.customDimensions.lists.list3.list[]`. Varje arrayelement innehåller en `"value"` -objekt som innehåller varje sträng. Ingen avgränsare behövs; det inkluderas automatiskt med det värde som anges i [Rapportsvitsinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Om ett komma (&#39;`,`&#39;) är konfigurerad som avgränsare för listvariabel 1, fylls följande XDM-objekt i `list1` variabel med `"Example value 1,Example value 2,Example value 3"`.

```json
"xdm": {
    "_experience": {
        "analytics": {
            "customDimensions": {
                "lists": {
                    "list1": {
                        "list": [
                            {
                                "value": "Example value 1"
                            },
                            {
                                "value": "Example value 2"
                            },
                            {
                                "value": "Example value 3"
                            }
                        ]
                    }
                }
            }
        }
    }
}
```

>[!NOTE]
>
>Adobe XDM-schemat innehåller `key` förutom `value` objekt i varje `list[]` array. Adobe använder inte dessa `key` objekt när data skickas till Adobe Analytics.

## Visa variabler med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.list1 - s.list3 i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

Varje listvariabel är en sträng som innehåller anpassade värden som är specifika för din organisation. De har inte ett högsta antal byte. Varje värde får dock innehålla högst 255 byte. Avgränsaren som du använder bestäms när du ställer in variabeln i [Rapportsvitsinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Använd inte blanksteg när du avgränsar flera objekt.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Om du anger dubblettvärden i samma träff dupliceras alla instanser av dessa värden med Adobe. Om du till exempel anger `s.list1 = "Brick,Brick";`, en instans räknas i rapporter.

## Jämför listekurser med listvariabler

Listutkast och listvariabler kan båda innehålla flera värden i samma träff. Det finns dock flera viktiga skillnader mellan dessa två variabeltyper.

* Alla propp kan bli en listpropp. Du kan ha upp till 75 proppar i listan om varje propp är en listprop. Det finns bara tre listvar tillgängliga.
* Listutkast har en gräns på 100 byte för hela variabeln. Listvariabler har en gräns på 255 byte per värde och ingen total bytegräns.
* Listproppar finns inte kvar efter den träff de ställs in. Listvariabler har en förfalloinställning som du vill ha. Med [bearbeta rapporttid](/help/components/vrs/vrs-report-time-processing.md)kan du använda anpassad attribuering för både listutkast och listvariabler.
