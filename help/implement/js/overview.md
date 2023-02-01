---
title: Implementera Adobe Analytics med AppMeasurement for JavaScript
description: Lär dig hur du implementerar Adobe Analytics med JavaScript utan ett tagghanteringssystem.
feature: Implementation Basics
source-git-commit: aef1d613437688b7eed704b227c41e4fbe4677dd
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 7%

---

# Implementera Adobe Analytics med AppMeasurement for JavaScript

AppMeasurement for JavaScript har historiskt sett varit en vanlig metod för att implementera Adobe Analytics. Men Tag Management Systems blir allt populärare med [taggar i Adobe Experience Platform](../launch/overview.md) rekommenderas.

Översikt över implementeringsuppgifterna:

![Implementera Adobe Analytivs med AppMeasurement - översikt](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Uppgift</b></th><th style="width:20%"><b>Mer information</b></th>
</tr>

<tr>
<td>1</td><td>Se till att du har <b>har definierat en rapportserie</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Hanterare för rapportsvit</a></td>
</tr>

<tr>
<td>2</td><td><b>Hämta den JavaScript-kod som krävs för AppMeasurement</b> från Code Manager. Zippa upp filen.</td><td><a href="../../admin/admin/code-manager-admin.md">Kodhanteraren</a></td>
</tr>

<tr>
<td>3</td><td><b>Lägg till <code>AppMeasurement.js</code> till webbplatsens mallfil</b>. Koden innehåller de bibliotek som krävs för att skicka data till Adobe.

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

</td><td><a href="../vars/config-vars/configuration-variables.md">Konfigurationsvariabler</a></td>
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
<td>6</td><td><b>Skicka data till Adobe med <code>t()</code> method</b>, när alla sidvariabler är definierade.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t(), metod</a></td>
</tr>

<tr>
<td>7</td><td><b>Utöka och validera implementeringen</b> innan det går till produktion.</b></td><td></td>
</tr>

</table>

## Ytterligare resurser

- [Variabler, funktioner, metoder och plugin-program - översikt](../vars/overview.md)
