---
title: Implementera med hårdkodade bildbegäranden
description: Implementera Adobe Analytics med en HTML-bildtagg (hårdkodad bildförfrågan)
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Implementera med hårdkodade bildbegäranden

AppMeasurement-bibliotek från Adobe kompilerar variabler som finns på sidan och skickar dem sedan som en bildförfrågan till Adobe. Du kan kringgå AppMeasurement-bibliotek helt och hållet och manuellt skicka en bildbegäran till Adobe. Den här metoden kräver att du manuellt formulerar bildbegäran och frågesträngen.

Den här implementeringsmetoden kan användas på alla plattformar som visar bilder från externa källor. Den förlitar sig inte alls på JavaScript.

> [!NOTE] Maskinkodade bildbegäranden är enkla att konfigurera, men de är svåra att felsöka, underhålla och skala i större projekt. Kontrollera att hårdkodade bildbegäranden är det bästa alternativet för dig innan du fortsätter.

## Syntax för bildbegäran

Följande är ett exempel på hårdkodad bildbegäran med HTML:

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` anger protokollet. Matcha det protokoll som används i bildbegäran med det protokoll som används av resten av din plats.
* `example.sc.omtrdc.net` är värdet i `trackingServer` variabeln.
* `/b/ss/` ingår i alla bildbegäranden. Den ingår i filstrukturen för bilder som lagras på Adobes datainsamlingsservrar.
* `examplersid` är det rapportsvit-ID som du vill skicka data till.
* `/1/` är träffkällan. Se `hit_source` under [Datakolumnreferens](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) i användarhandboken för Export. Styr i vilken ordning cookies och andra metoder används för att identifiera besökare.
* Allt efter frågesträngsavgränsaren (`?`) är data som du vill ta med i rapporter. Se Frågeparametrar [för](../validate/query-parameters.md) datainsamling för en fullständig lista över parametrar som du kan ta med i en bildbegäran.

## Vanliga frågor

Lär dig mer om vanliga frågor med hjälp av hårdkodade bildbegäranden.

**Är frågesträngsparametrar skiftlägeskänsliga?**

Ja. Kontrollera att frågesträngsparametrarna matchar varandra exakt, annars registreras de inte. Till exempel `pagename` är inte en giltig frågesträngsparameter, medan `pageName` är .

**Kan jag inkludera blanksteg i frågesträngen?**

Värdena för var och en av frågesträngsparametrarna är URL-kodade. URL-kodning konverterar tecken som normalt är ogiltiga i URL-adresser till giltiga tecken. Ett blankstegstecken konverteras till exempel till `%20`. Kontrollera att alla tecken som inte är alfanumeriska är URL-kodade. Adobe URL avkodar automatiskt värden när bildbegäranden når datainsamlingsservrar.

Mer information om hur URL-kodning fungerar finns i [HTML URL-kodningsreferens](https://www.w3schools.com/tags/ref_urlencode.asp) för W3Schools.

**Vilket är det högsta antalet tecken ett enskilt värde kan ha?**

Varje variabel har olika maxlängd. De flesta trafikvariabler innehåller upp till 100 byte, medan de flesta konverteringsvariabler innehåller upp till 255 byte. När en bildbegäran når datainsamlingsservrar trunkerar Adobe automatiskt dessa värden till sin maximala längd.
