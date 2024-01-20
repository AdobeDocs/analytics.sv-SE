---
title: Mappa taggdataelement till analysvariabler
description: Tilldela dataelement till Analytics-variabler så att ni kan använda dem som dimensioner i Analysis Workspace.
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 2aef8de290399f234921b09cf094485fc06f1c24
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Mappa taggdataelement till analysvariabler

När du har en databas med taggdataelement kan du tilldela dem till Analytics-dimensioner.

## Förutsättningar

[Mappa datalagerobjekt till dataelement](layer-to-elements.md): Se till att du förstår taggdataelementen och att du har flera att arbeta med.

[Skapa ett dokument för lösningsdesign](../prepare/solution-design.md): Ett dokument för utformning av lösningar är avgörande för att hålla sig välorganiserat. Genom att följa ert lösningsdesigndokument förenklas tilldelningen av dataelement till analysvariabler.

## Tilldela dataelement till analysvariabler

Om du publicerar ett taggbibliotek efter att du har utfört de här stegen kan du använda anpassade dimensioner i Analysis Workspace. Du kan ställa in Analytics-variabler globalt eller i enskilda regler.

### Ange globala variabler

Globala variabler är idealiska om du vill ange variabelvärden på alla sidor där dataelementet finns.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på [!UICONTROL Extensions tab]och sedan klicka [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Klicka på [!UICONTROL Global variables] , som visar gränssnittet för att tilldela globala variabler.

### Ange variabler i regler

Variabler som ställs in i regler är idealiska om du inte vill ha variabler som ställs in på varje sida. Du definierar villkoren i regeln. Se [Regler](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) i dokumentationen för Adobe Experience Platform-taggar.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en).
1. Klicka på [!UICONTROL Add] knapp under [!UICONTROL Actions].
1. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] för att ange variabler.
1. Klicka på ![Dataelement](assets/data-element.png) till höger om den önskade Analytics-variabeln. Din organisations [konstruktionsdokument](../prepare/solution-design.md) anger vilken Analytics-variabel som ska användas.
1. Markera det önskade dataelementet i det modala fönstret. Klicka på [!UICONTROL Select].
1. Dataelementnamnet läggs till i textfältet omgivet av `%` skyltar. Om du t.ex. gav dataelementet namnet&quot;Sidnamn&quot; visas strängen `%Page name%` när ett dataelement tilldelas till en variabel.

>[!TIP]
>
>Du kan sammanfoga dataelement i samma variabel. Om du till exempel har ett dataelement av typen Värdnamn och ett dataelement av typen Sökväg kan du kombinera båda i en enda variabel med `%Hostname%%Pathname%`.

## Nästa steg

[Sidvariabler](../vars/page-vars/page-variables.md): Lär dig vilka sidnivåvariabler du kan använda i implementeringen för att få ut mer av dimensionerna i Analysis Workspace.

[Konfigurationsvariabler](../vars/config-vars/configuration-variables.md): Lär dig vilka konfigurationsvariabler du kan använda i implementeringen för att låsa upp fler funktioner i Adobe Analytics.
