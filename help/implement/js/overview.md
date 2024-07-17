---
title: Implementera Adobe Analytics med AppMeasurement för JavaScript
description: Lär dig implementera Adobe Analytics med JavaScript utan tagghanteringssystem.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 4%

---

# Implementera Adobe Analytics med AppMeasurement för JavaScript

AppMeasurement för JavaScript har tidigare varit ett vanligt sätt att implementera Adobe Analytics. Men om Tag Management Systems blir allt populärare bör du använda [taggar i Adobe Experience Platform](../launch/overview.md).

Översikt över implementeringsuppgifterna på hög nivå:

![Så här implementerar du Adobe Analytics med AppMeasurement för JavaScript, enligt beskrivningen i det här avsnittet.](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Uppgift</b></th><th style="width:20%"><b>Mer information</b></th>
</tr>

<tr>
<td>1</td><td>Kontrollera att du har <b>definierat en rapportserie</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td><td><b>Hämta nödvändig JavaScript-kod för AppMeasurementet</b> från kodhanteraren. Zippa upp filen.</td><td><a href="../../admin/admin/code-manager-admin.md">Kodhanteraren</a></td>
</tr>

<tr>
<td>3</td><td><b>Lägg till <code>AppMeasurement.js</code> i webbplatsens mallfil</b>. Koden innehåller de bibliotek som krävs för att skicka data till Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Definiera konfigurationsvariabler i <code>AppMeasurement.js</code></b>. När Analytics-objektet instansieras ser dessa variabler till att datainsamlingsinställningarna är korrekta.

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">Konfigurationsvarabler</a></td>
</tr>

<tr>
<td>5</td><td><b>Definiera sidnivåvariabler i webbplatsens sidkod</b>. Variablerna avgör vilka mått och mätvärden som skickas till Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Sidvariabler</a></td>
</tr>

<tr>
<td>6</td><td><b>Skicka data till Adobe med <code>t()</code> method</b> när alla sidvariabler är definierade.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t(), metod</a></td>
</tr>

<tr>
<td>7</td><td><b>Utöka och validera implementeringen</b> innan du skickar ut den till produktion.</b></td><td></td>
</tr>

</table>

## Ytterligare resurser

- [Variabler, funktioner, metoder och plugin-program - översikt](../vars/overview.md)
