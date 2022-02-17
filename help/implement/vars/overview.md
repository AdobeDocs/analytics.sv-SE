---
title: Variabler, funktioner, metoder och plugin-program - översikt
description: Lär dig vilka variabler du kan ta med i data som du skickar till Adobe för att förbättra rapporteringen.
keywords: appmeasurement,variabler,var,konfiguration,sida,implementering
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# Variabler, funktioner, metoder och plugin-program - översikt

Analytics ger ett antal variabler för att samla in analysdata. Variablerna i det här avsnittet är uppdelade i flera avsnitt:

* **Sidvariabler** är värden som vanligtvis används direkt vid rapportering. Vanliga sidvariabler inkluderar `props`, `eVars`och `events`.
* **Konfigurationsvariabler** är inställningsvärden som gör att rätt data når Adobe. Vanliga config-variabler inkluderar `trackingServerSecure`, `charSet`och `linkTrackVars`. Konfigurationsvariabler fyller vanligtvis inte i dimensionsobjekt.
* **Funktioner och metoder** är koddelar som utför en viss uppgift när de refereras. Vanliga funktioner inkluderar `t()`, `tl()`och `clearVars()`.

## Variabler och implementeringsmetoder

Adobe erbjuder flera sätt att implementera Adobe Analytics. På varje sida finns ett avsnitt om hur du implementerar variabeln med hjälp av taggar i Adobe Experience Platform och AppMeasurement for JavaScript.

Här är en video om hur du konfigurerar variabler i Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/28755/?quality=12)

## Operationsordning

AppMeasurement-bibliotek som publiceras av Adobe Analytics följer en viss ordning när data skickas till Adobe. Om du utför dessa åtgärder i fel ordning kan data vara ofullständiga.

1. Om webbplatsen använder ett datalager måste alla tillämpliga variabler fyllas i först. Se [Datalager](../prepare/data-layer.md) för mer information.
2. Använd datalagret för att fylla i Analytics-variabler. Om du använder taggar i Adobe Experience Platform kan du enkelt utföra den här uppgiften genom att använda dataelement och sedan tilldela dataelementet till en variabel. Se [Dataelement](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html).
3. Anropa spårningsfunktionen. De flesta AppMeasurement-bibliotek använder `t()` -metod, men vissa av de mobila SDK:s använder `track()`. När spårningsfunktionen anropas skickas alla variabler som stöds i Analytics-objektet till Adobe i form av en bildbegäran.

## Ogiltiga tecken

Följande tecken och strängar tillåts aldrig i JavaScript-variabler.

* Tabb (`0x09`)
* Radbrytning (`0x0D`)
* Newline (`0x0A`)
* HTML-taggar (t.ex. `<b></b>` eller `&#153`)

Vissa variabler har ytterligare begränsningar eller syntaxkrav. Till exempel [`products`](page-vars/products.md) variabelreserverar semikolon och kommatecken för att avgränsa separata produkter och kategorier.
