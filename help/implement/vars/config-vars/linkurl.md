---
title: linkURL
description: Åsidosätt den automatiskt genererade länk-URL som AppMeasurement använder i länkspårningsanrop.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 7176e068dd05c5589d741f3194d2ad5d795e017d
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# linkURL

När ett anrop om länkspårning skickas till Adobe identifierar AppMeasurement den URL som klickades på. Den här URL:en hjälper till att fastställa länktypen, t.ex. hämtningslänkar och avslutslänkar. Använd variabeln `linkURL` för att åsidosätta den URL som identifierats.

Det finns inga dimensioner i Analysis Workspace som rapporterar om den här variabeln. Den fyller i kolumnen `page_event_var1` i [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md). Om du vill spåra URL:en för en länk som du klickat på rekommenderar Adobe att du använder en anpassad variabel, till exempel ett [utkast](../page-vars/prop.md).

## Länk-URL med Web SDK

Länk-URL mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` eller `data.__adobe.analytics.pev1`

## Länk-URL med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.linkURL i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.linkURL` är en sträng som innehåller den fullständiga URL:en för den klickade länken. Den här variabeln fyller inte i några dimensioner som är tillgängliga i rapporter.

```js
s.linkURL = "https://example.com";
```

Om det tredje argumentet för metoden [tl()](../functions/tl-method.md) inte har angetts används variabeln `linkURL` i stället.
