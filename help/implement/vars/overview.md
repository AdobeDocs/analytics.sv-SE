---
title: Variabler, funktioner, metoder och plugin-program - översikt
description: Lär dig vilka variabler du kan ta med i data som du skickar till Adobe för att förbättra rapporteringen.
keywords: appmeasurement,variabler,var,konfiguration,sida,implementering
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Variabler, funktioner, metoder och plugin-program - översikt

Analytics ger ett antal variabler för att samla in analysdata. Variablerna i det här avsnittet är uppdelade i flera avsnitt:

* **Sidvariabler är** värden som vanligtvis används direkt vid rapportering. Vanliga sidvariabler är `props`, `eVars` och `events`.
* **Konfigurationsvariabler är** inställningsvärden som hjälper till att säkerställa att rätt data når Adobe. Vanliga config-variabler är `trackingServerSecure`, `charSet` och `linkTrackVars`. Konfigurationsvariabler fyller vanligtvis inte i dimensionsobjekt.
* **Funktioner och** metoder är kodbitar som utför en viss uppgift när de refereras. Vanliga funktioner är `t()`, `tl()` och `clearVars()`.

## Variabler och implementeringsmetoder

Adobe erbjuder flera sätt att implementera Adobe Analytics. På varje sida finns ett avsnitt om hur du implementerar variabeln med Launch och AppMeasurement for JavaScript.

## Operationsordning

AppMeasurement-bibliotek som publiceras av Adobe Analytics följer en viss ordning när data skickas till Adobe. Om du utför dessa åtgärder i fel ordning kan data vara ofullständiga.

1. Om webbplatsen använder ett datalager måste alla tillämpliga variabler fyllas i först. Mer information finns i [Datalager](../prepare/data-layer.md).
2. Använd datalagret för att fylla i Analytics-variabler. Om du använder Launch kan du enkelt utföra den här uppgiften genom att använda dataelement och sedan tilldela dataelementet till en variabel. Se [Dataelement](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/data-elements.html) i användarhandboken för Launch.
3. Anropa spårningsfunktionen. De flesta AppMeasurement-bibliotek använder metoden `t()`, men i vissa mobil-SDK:er används `track()`. När spårningsfunktionen anropas skickas alla variabler som stöds i Analytics-objektet till Adobe i form av en bildbegäran.

## Ogiltiga tecken

Följande tecken och strängar tillåts aldrig i JavaScript-variabler.

* Tabb (`0x09`)
* Radretur (`0x0D`)
* Tidslinje (`0x0A`)
* HTML-taggar (t.ex. `<b></b>` eller `&#153`)

Vissa variabler har ytterligare begränsningar eller syntaxkrav. Variabeln [`products`](page-vars/products.md) reserverar t.ex. semikolon och kommatecken som avgränsar olika produkter och kategorier.
