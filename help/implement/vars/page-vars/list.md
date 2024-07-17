---
title: list
description: Anpassade variabler som innehåller flera värden i samma träff.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# list

Listvariabler är anpassade variabler som du kan använda hur du vill. De fungerar på liknande sätt som eVars, förutom att de kan innehålla flera värden i samma träff. Listvariabler har ingen teckengräns.

Se till att du spelar in hur du använder varje listvariabel och deras logik i [lösningsdesigndokumentet](../../prepare/solution-design.md).

>[!NOTE]
>
>Listvariabler lagrar de senaste värdena per besökare baserat på dess [!UICONTROL Max values]-inställning i [Rapportsvitens inställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Upp till 250 värden stöds. Om det finns mer unika värden än vad inställningen [!UICONTROL Max values] tillåter, kommer de äldsta värdena inte att tillskrivas mätvärden.

## Ställ in listvariabler i rapportsvitens inställningar

Se till att du konfigurerar varje listvariabel i inställningarna för rapportsviten innan du använder dem i implementeringen. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md) i administrationshandboken. Det här steget gäller alla implementeringsmetoder.

## Visa variabler med Web SDK

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) använder listvariabler XDM-fälten `xdm._experience.analytics.customDimensions.lists.list1.list[]` till `xdm._experience.analytics.customDimensions.lists.list3.list[]`. Varje arrayelement innehåller ett `"value"`-objekt som innehåller varje sträng. Du behöver inte ange någon avgränsare. Datainsamlingsservrar i Adobe identifierar och tar automatiskt med rätt avgränsare i [rapportsvitens inställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

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
>Adobe XDM-schemat innehåller `key` objekt förutom `value` objekt i varje `list[]` -array. Adobe använder inte dessa `key`-objekt när data skickas till Adobe Analytics.

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) använder listvariabler `data.__adobe.analytics.list1` - `data.adobe.analytics.list3` följande AppMeasurementen syntax. Kontrollera att du använder rätt avgränsare i [Rapportsvitens inställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

```json
"data": {
  "__adobe": {
    "analytics": {
      "list1": "Example value 1,Example value 2,Example value 3"
    }
  }
}
```

## Visa variabler med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.list1 - s.list3 i AppMeasurementet och den anpassade kodredigeraren i Analytics-tillägget

Varje listvariabel är en sträng som innehåller anpassade värden som är specifika för din organisation. Den här variabeln har inte ett maximalt antal byte, men varje enskilt värde har en maxgräns på 255 byte. Avgränsaren som du använder bestäms när du ställer in variabeln i [Rapportsvitens inställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Använd inte blanksteg när du avgränsar flera objekt.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Om du anger dubblettvärden i samma träff dupliceras alla instanser av dessa värden med Adobe. Om du till exempel anger `s.list1 = "Brick,Brick";` räknas en instans i rapporter.

## Jämför listekurser med listvariabler

Listutkast och listvariabler kan båda innehålla flera värden i samma träff. Det finns dock flera viktiga skillnader mellan dessa två variabeltyper.

* Alla propp kan bli en listpropp. Du kan ha upp till 75 proppar i listan om varje propp är en listprop. Det finns bara tre listvar tillgängliga.
* Listutkast har en gräns på 100 byte för hela variabeln. Listvariabler har en gräns på 255 byte per värde och ingen total bytegräns.
* Listproppar finns inte kvar efter den träff de ställs in. Listvariabler har en förfalloinställning som du vill ha. Med [rapporttidsbearbetning](/help/components/vrs/vrs-report-time-processing.md) kan du dock använda anpassad attribuering på både listutkast och listvariabler.
