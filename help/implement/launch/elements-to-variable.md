---
title: Mappa taggdataelement till analysvariabler
description: Tilldela dataelement till Analytics-variabler så att ni kan använda dem som dimensioner i Analysis Workspace.
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 0%

---

# Mappa taggdataelement till analysvariabler

När du har en databas med taggdataelement kan du tilldela dem till Analytics-dimensioner.

>[!NOTE]
>Adobe Experience Platform Launch har omklassificerats som en serie datainsamlingstekniker i Experience Platform. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad referens till terminologiska ändringar.

## Förutsättningar

[Mappa datalagerobjekt till dataelement](layer-to-elements.md): Se till att du förstår taggdataelementen och att du har flera att arbeta med.

[Skapa ett designdokument](../prepare/solution-design.md): Ett dokument för att utforma lösningar är nödvändigt för att hålla er välorganiserade. Genom att följa ert lösningsdesigndokument förenklas tilldelningen av dataelement till analysvariabler.

## Tilldela dataelement till analysvariabler

Om du publicerar ett taggbibliotek efter att du har utfört de här stegen kan du använda anpassade dimensioner i Analysis Workspace. Du kan ställa in Analytics-variabler globalt eller i enskilda regler.

### Ange globala variabler

Globala variabler är idealiska om du vill ange variabelvärden på alla sidor där dataelementet finns.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på den önskade taggegenskapen.
1. Klicka på [!UICONTROL Extensions tab] och sedan på [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Klicka på dragspelet [!UICONTROL Global variables], som visar gränssnittet för att tilldela globala variabler.

### Ange variabler i regler

Variabler som anges i regler är idealiska om du inte vill ha variabler som anges på varje sida. Du definierar villkoren i regeln. Se [Regler](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) i dokumentationen för Adobe Experience Platform-taggar.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på den önskade taggegenskapen.
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
