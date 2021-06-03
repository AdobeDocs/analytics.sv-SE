---
title: Mappa Launch-dataelement till Analytics-variabler
description: Tilldela dataelement till Analytics-variabler så att ni kan använda dem som dimensioner i Analysis Workspace.
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 5%

---

# Mappa Launch-dataelement till Analytics-variabler

När du har en databas med dataelement i Adobe Experience Platform Launch kan du tilldela dem till Analytics-dimensioner.

## Förutsättningar

[Mappa datalagerobjekt till dataelement](layer-to-elements.md): Se till att du förstår dataelement i Launch och att du har flera att arbeta med.

[Skapa ett designdokument](../prepare/solution-design.md): Ett dokument för att utforma lösningar är nödvändigt för att hålla er välorganiserade. Genom att följa ert lösningsdesigndokument förenklas tilldelningen av dataelement till analysvariabler.

## Tilldela dataelement till analysvariabler

Om du publicerar ett bibliotek i Launch efter att du har utfört de här stegen kan du använda anpassade dimensioner i Analysis Workspace. Du kan ställa in Analytics-variabler globalt eller i enskilda regler.

### Ange globala variabler

Globala variabler är idealiska om du vill ange variabelvärden på alla sidor där dataelementet finns.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på önskad Launch-egenskap.
1. Klicka på [!UICONTROL Extensions tab] och sedan på [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Klicka på dragspelet [!UICONTROL Global variables], som visar gränssnittet för att tilldela globala variabler.

### Ange variabler i regler

Variabler som anges i regler är idealiska om du inte vill ha variabler som anges på varje sida. Du definierar villkoren i regeln. Se [Regler](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/rules.html) i användarhandboken för Adobe Experience Platform Launch.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på önskad Launch-egenskap.
1. Klicka på fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en).
1. Klicka på knappen [!UICONTROL Add] under [!UICONTROL Actions].
1. Ställ in listrutan [!UICONTROL Extension] på Adobe Analytics och listrutan [!UICONTROL Action Type] på Ange variabler.
1. Klicka på ikonen ![Dataelement](assets/data-element.png) till höger om den önskade Analytics-variabeln. Organisationens [lösningsdesigndokument](../prepare/solution-design.md) bestämmer vilken Analytics-variabel som ska användas.
1. Markera det önskade dataelementet i det modala fönstret. Klicka på [!UICONTROL Select].
1. Dataelementnamnet läggs till i textfältet omgivet av `%`-tecken. Om du till exempel gav dataelementet namnet&quot;Sidnamn&quot;, skulle du se strängen `%Page name%` när du tilldelar ett dataelement till en variabel.

>[!TIP]
>
>Du kan sammanfoga dataelement i samma variabel. Om du till exempel har ett dataelement av typen Värdnamn och ett dataelement av typen Sökväg, kan du kombinera båda i en enda variabel med `%Hostname%%Pathname%`.

## Nästa steg

[Sidvariabler](../vars/page-vars/page-variables.md): Lär dig vilka sidnivåvariabler du kan använda i implementeringen för att få ut mer av dimensionerna i Analysis Workspace.

[Konfigurationsvariabler](../vars/config-vars/configuration-variables.md): Lär dig vilka konfigurationsvariabler du kan använda i implementeringen för att låsa upp fler funktioner i Adobe Analytics.
