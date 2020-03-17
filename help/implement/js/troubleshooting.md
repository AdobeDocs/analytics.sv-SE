---
title: Felsöka JavaScript-implementering
description: Lär dig mer om vanliga problem och de bästa sätten att felsöka JavaScript-implementeringen.
translation-type: tm+mt
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# Felsöka JavaScript-implementering

Nedan följer flera orsaker till varför din organisation kan ha problem med att hämta data till Adobe Analytics på rätt sätt.

## Använda citattecken

De flesta variabler som skickas till Adobe är strängar. I JavaScript kan du använda enkla citattecken eller dubbla citattecken.

### Blanda citattecken för att definiera en variabel

Det är en god vana att se till att du är konsekvent med de citattyper som du använder. Om ett enkelt citattecken anger början på en sträng måste ett enkelt citattecken användas för att stänga den.

Till exempel är både `s.eVar1 = 'Value'` och `s.eVar1 = "Value"` giltiga. `s.eVar1 = 'Value"` är inte giltigt.

### Inkludera enkla eller dubbla citattecken i en sträng

Ibland är det önskvärt att ta med ett enkelt eller dubbelt citattecken i en sträng. Du vill till exempel inkludera värdet `Alex's sale` eller `John the "Hunter"` i rapporter. Det finns två metoder för att inkludera dessa värden:

* **Använd den andra citattypen**: Till exempel `s.eVar1 = "Alex's sale"` och `s.eVar1 = 'John the "Hunter"'` är båda giltiga.
* **Escape-citattecken**: Använd ett omvänt snedstreck för att undvika citattecken. Till exempel `s.eVar1 = 'Alex\'s sale'` och `s.eVar1 = "John the \"Hunter\""` är båda giltiga.

### Undvik typografiska citattecken

I vissa program konverteras automatiskt neutrala citattecken (`"..."` och `'...'`) till typografiska citattecken (`“...”` och `‘...’`). Undvik att använda dokumentredigerare (t.ex. Microsoft Word) eller skicka kodfragment via e-post. Kurmatecken kan inte användas i JavaScript.

## Referera till Analytics-objektet

Alla variabler som skickas till Adobe använder objektet Analytics. I de flesta implementeringar används `s` objektet. Se till att Analytics-objektet ingår i referensen när du refererar till variabler.

Till exempel `s.eVar1 = 'Value'` är giltig medan `eVar1 = 'Value'` inte är det.

## Definiera varje variabel en gång

När en spårfunktion (`s.t()`) körs, tar AppMeasurement alla definierade variabler och kompilerar dem till en bildbegäran. Om du definierar en variabel mer än en gång i implementeringen används bara det senaste värdet. Kontrollera att alla variabelvärden innehåller rätt värde när spårningsfunktionen körs.

## Korrigera variabelns skiftläge

Vissa variabler använder versaler. JavaScript-variabler är skiftlägeskänsliga. Se till att du använder rätt skiftläge när du definierar variabler. Till exempel `s.eVar1 = 'Value'` är giltig medan `s.evar1 = 'Value'` inte är det.

## Plugin-program

Vissa organisationer använder plugin-program för att förbättra implementeringen av Adobe Analytics. När du uppgraderar AppMeasurement-versioner ska du inte glömma att ta med installerade plugin-program igen. Koden som skapas i [!UICONTROL Code Manager] saknar plugin-kod. Gör en kopia av din befintliga kod om du behöver återställa en tidigare version av AppMeasurement.

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

I det här fallet `document.title` fylls i `s.pageName`som får värdet&quot;Hemsida&quot;. Vissa webbläsare kan dock tolka tomt utrymme på ett annat sätt. Resultatet kan vara något av följande två exempel:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Dessa två variabelvärden betraktas som separata i Adobe Analytics. Det tomma utrymmet tas dock automatiskt bort för visning. Resultatet är en rapport som visar två till synes identiska radobjekt på&quot;hemsidan&quot;. Kontrollera att variabelvärdena inte innehåller blanksteg före eller efter det önskade värdet.
