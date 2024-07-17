---
title: Mappa taggdataelement till analysvariabler
description: Tilldela dataelement till Analytics-variabler så att ni kan använda dem som dimensioner i Analysis Workspace.
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Mappa taggdataelement till analysvariabler

När du har en databas med taggdataelement kan du tilldela dem till Analytics-dimensioner.

## Förutsättningar

[Mappa datalagerobjekt till dataelement](layer-to-elements.md): Kontrollera att du förstår taggdataelement och att du har flera att arbeta med.

[Skapa ett lösningsdesigndokument](../prepare/solution-design.md): Ett lösningsdesigndokument är nödvändigt för att du ska kunna hålla ordning. Genom att följa ert lösningsdesigndokument förenklas tilldelningen av dataelement till analysvariabler.

## Tilldela dataelement till analysvariabler

Om du publicerar ett taggbibliotek efter att du har utfört de här stegen kan du använda anpassade dimensioner i Analysis Workspace. Du kan ställa in Analytics-variabler globalt eller i enskilda regler.

### Ange globala variabler

Globala variabler är idealiska om du vill ange variabelvärden på alla sidor där dataelementet finns.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på [!UICONTROL Extensions tab] och sedan på [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Klicka på dragspelsfliken [!UICONTROL Global variables], som visar gränssnittet för att tilldela globala variabler.

### Ange variabler i regler

Variabler som ställs in i regler är idealiska om du inte vill ha variabler som ställs in på varje sida. Du definierar villkoren i regeln. Se [Regler](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) i dokumentationen för Adobe Experience Platform-taggar.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en).
1. Klicka på knappen [!UICONTROL Add] under [!UICONTROL Actions].
1. Ställ in listrutan [!UICONTROL Extension] på Adobe Analytics och listrutan [!UICONTROL Action Type] på Ange variabler.
1. Klicka på ikonen ![Dataelement](assets/data-element.png) till höger om den önskade Analytics-variabeln. Organisationens [lösningsdesigndokument](../prepare/solution-design.md) anger vilken Analytics-variabel som ska användas.
1. Markera det önskade dataelementet i det modala fönstret. Klicka på [!UICONTROL Select].
1. Dataelementnamnet läggs till i textfältet omgivet av `%` tecken. Om du till exempel gav dataelementet namnet&quot;Sidnamn&quot;, skulle du se strängen `%Page name%` när du tilldelar ett dataelement till en variabel.

>[!TIP]
>
>Du kan sammanfoga dataelement i samma variabel. Om du till exempel har ett dataelement av typen Värdnamn och ett dataelement av typen Sökväg, kan du kombinera båda i en enda variabel med `%Hostname%%Pathname%`.

## Nästa steg

[Sidvariabler](../vars/page-vars/page-variables.md): Lär dig vilka sidnivåvariabler du kan använda i implementeringen för att få ut mer av dimensionerna i Analysis Workspace.

[Konfigurationsvariabler](../vars/config-vars/configuration-variables.md): Lär dig vilka konfigurationsvariabler du kan använda i implementeringen för att låsa upp fler funktioner i Adobe Analytics.
