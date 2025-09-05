---
title: Felsöka JavaScript-implementering
description: Lär dig mer om vanliga problem och de bästa sätten att felsöka din JavaScript-implementering.
feature: Implementation Basics
exl-id: e7181e78-65bf-446d-8d5c-b47323dbec1d
role: Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Felsöka JavaScript-implementering

Nedan följer några orsaker till varför ditt företag kan ha problem med att hämta in data korrekt i Adobe Analytics.

## Använda citattecken

De flesta variabler som skickas till Adobe är strängar. I JavaScript kan du använda enkla citattecken eller dubbla citattecken.

### Blanda citattecken för att definiera en variabel

Det är en god vana att se till att du är konsekvent med de citattyper som du använder. Om ett enkelt citattecken anger början på en sträng måste ett enkelt citattecken användas för att stänga den.

Till exempel är både `s.eVar1 = 'Value'` och `s.eVar1 = "Value"` giltiga. `s.eVar1 = 'Value"` är inte giltigt.

### Inkludera enkla eller dubbla citattecken i en sträng

Ibland är det önskvärt att ta med ett enkelt eller dubbelt citattecken i en sträng. Du vill till exempel inkludera värdet `Alex's sale` eller `John the "Hunter"` i rapporter. Det finns två metoder för att inkludera dessa värden:

* **Använd den andra citattypen**: `s.eVar1 = "Alex's sale"` och `s.eVar1 = 'John the "Hunter"'` är till exempel båda giltiga.
* **Escape-citattecken**: Använd ett omvänt snedstreck för att undvika citattecken. Till exempel är både `s.eVar1 = 'Alex\'s sale'` och `s.eVar1 = "John the \"Hunter\""` giltiga.

### Undvik typografiska citattecken

I vissa program konverteras automatiskt neutrala citattecken (`"..."` och `'...'`) till typografiska citattecken (`"..."` och `'...'`). Undvik att använda dokumentredigerare (t.ex. Microsoft Word) eller skicka kodfragment via e-post. Kurmatecken kan inte användas i JavaScript.

## Referera till Analytics-objektet

Alla variabler som skickas till Adobe använder objektet Analytics. De flesta implementeringar använder objektet `s`. Se till att Analytics-objektet ingår i referensen när du refererar till variabler.

`s.eVar1 = 'Value'` är till exempel giltig medan `eVar1 = 'Value'` inte är det.

## Definiera varje variabel en gång

När en spårfunktion (`s.t()`) körs tar AppMeasurement alla definierade variabler och kompilerar dem till en bildbegäran. Om du definierar en variabel mer än en gång i implementeringen används bara det senaste värdet. Kontrollera att alla variabelvärden innehåller rätt värde när spårningsfunktionen körs.

## Korrigera variabelns skiftläge

Vissa variabler använder versaler. JavaScript-variabler är skiftlägeskänsliga. Se till att du använder rätt skiftläge när du definierar variabler. `s.eVar1 = 'Value'` är till exempel giltig medan `s.evar1 = 'Value'` inte är det.

## Plugin-program

Vissa organisationer använder plugins för att förbättra sin implementering av Adobe Analytics. När du uppgraderar AppMeasurement-versioner ska du inte glömma att ta med eventuella installerade plugin-program igen. Koden som skapas i [!UICONTROL Code Manager] har ingen plugin-kod med sig. Gör en kopia av din befintliga kod om du behöver återställa en tidigare version av AppMeasurement.

## Tomt utrymme i variabelvärden

I HTML finns det flera tecken som skapar tomt utrymme. Det kan vara ett mellanslag, en tabb och en radmatning. Titta på följande exempel:

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

I det här fallet fyller `document.title` i `s.pageName`, som får värdet Home Page. Vissa webbläsare kan dock tolka tomt utrymme på ett annat sätt. Resultatet kan vara något av följande två exempel:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Dessa två variabelvärden betraktas som separata i Adobe Analytics. Det tomma utrymmet tas dock automatiskt bort för visning. Resultatet är en rapport som visar två till synes identiska radobjekt på&quot;hemsidan&quot;. Kontrollera att variabelvärdena inte innehåller blanksteg före eller efter det önskade värdet.

## Trunkerade bildbegäranden

Implementeringar som fyller i många variabler med långa värden kan ibland leda till trunkerade bildförfrågningar. Vissa äldre webbläsare, t.ex. Internet Explorer, har en begränsning på 2 083 tecken för bildförfrågnings-URL:er. Om din organisation har mycket långa bildförfrågningar kan du pröva följande:

* **Använd tjänsten Experience Cloud ID**: AppMeasurement Libraries 1.4.1 och senare skickar automatiskt bildbegäranden med HTTP POST om de är för långa. Data som skickas med den här metoden trunkeras inte oavsett längd. Mer information finns i [Adobe Experience Cloud ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=sv-SE).
* **Använd bearbetningsregler**: [Bearbetningsregler](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) kan kopiera värden från en variabel till en annan. Med den här metoden kan du inte ange samma värde i flera variabler. Exempel:

  Kör alltid:<br>
Skriv över värdet för prop1 med eVar1 <br>
Skriv över värdet för eVar2 med eVar1 <br>
Skriv över värdet för prop2 med eVar1 <br>

  Ställ sedan in eVar1 i implementeringen:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  ```

* **Använd dynamiska variabler**: Om implementeringen fyller i många variabler med samma värde kan du använda [dynamiska variabler](/help/implement/vars/page-vars/dynamic-variables.md) för att korta ned URL:en för begäran:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  s.eVar2 = "D=v1";
  s.prop1 = "D=v1";
  s.prop2 = "D=v1";
  ```

* **Använd klassificeringar**: Om produkt- eller sidnamn är ovanligt långa kan du använda ett identifierande värde eller en identifierande kod och sedan använda [klassificeringar](/help/components/classifications/classifications-overview.md) för att visa ett mer användarvänligt namn.
