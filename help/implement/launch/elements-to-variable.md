---
title: Mappa Launch-dataelement till Analytics-variabler
description: Tilldela dataelement till Analytics-variabler så att du kan använda dem som mått i Analysis Workspace.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 7%

---


# Mappa Launch-dataelement till Analytics-variabler

När du har en databas med dataelement i Adobe Experience Platform Launch kan du tilldela dem till Analytics-dimensioner.

## Förutsättningar

[Mappa datalagerobjekt till dataelement](layer-to-elements.md): Se till att du förstår dataelement i Launch och att du har flera att arbeta med.

[Skapa ett designdokument](../prepare/solution-design.md): Ett dokument för att utforma lösningar är nödvändigt för att hålla er välorganiserade. Genom att följa ditt lösningsdesigndokument förenklas tilldelningen av dataelement till Analytics-variabler.

## Tilldela dataelement till Analytics-variabler

Om du publicerar ett bibliotek i Launch efter att du har utfört de här stegen kan du använda anpassade dimensioner i Analysis Workspace. Du kan ställa in Analytics-variabler globalt eller i enskilda regler.

### Ange globala variabler

Globala variabler är idealiska om du vill ange variabelvärden på alla sidor där dataelementet finns.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på önskad Launch-egenskap.
1. Klicka på [!UICONTROL Extensions tab]och sedan på [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Klicka på dragspelsfliken, som visar gränssnittet för att tilldela globala variabler. [!UICONTROL Global variables]

### Ange variabler i regler

Variabler som anges i regler är idealiska om du inte vill ha variabler som anges på varje sida. Du definierar villkoren i regeln. Se [Regler](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html) i användarhandboken för Adobe Experience Platform Launch.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på önskad Launch-egenskap.
1. Klicka på [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en).
1. Click the [!UICONTROL Add] button under [!UICONTROL Actions].
1. Ställ in listrutan [!UICONTROL Extension] till Adobe Analytics och listrutan [!UICONTROL Action Type] till Ange variabler.
1. Klicka på ikonen ![Dataelement](assets/data-element.png) till höger om den Analytics-variabel du vill använda. Organisationens [lösningsdesigndokument](../prepare/solution-design.md) bestämmer vilka Analytics-variabler som ska användas.
1. Markera det önskade dataelementet i det modala fönstret. Klicka på [!UICONTROL Select].
1. Dataelementnamnet läggs till i textfältet omgivet av `%` tecken. Om du till exempel gav dataelementet namnet&quot;Sidnamn&quot;, skulle du se strängen `%Page name%` när du tilldelar ett dataelement till en variabel.

>[!TIP]
>
>Du kan sammanfoga dataelement i samma variabel. Om du till exempel har ett dataelement av typen Värdnamn och ett dataelement av typen Sökväg, kan du kombinera båda i en enda variabel med `%Hostname%%Pathname%`.

## Nästa steg

[Sidvariabler](../vars/page-vars/page-variables.md): Lär dig vilka sidnivåvariabler du kan använda i implementeringen för att få ut mer av dimensionerna i Analysis Workspace.

[Konfigurationsvariabler](../vars/config-vars/configuration-variables.md): Lär dig vilka konfigurationsvariabler du kan använda i implementeringen för att låsa upp fler funktioner i Adobe Analytics.
