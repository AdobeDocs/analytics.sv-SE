---
title: Implementera med hårdkodade bildbegäranden
description: Implementera Adobe Analytics med en HTML-bildtagg (hårdkodad bildbegäran)
feature: Implementation Basics
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 0%

---

# Implementera med hårdkodade bildbegäranden

AppMeasurement-bibliotek från Adobe kompilerar variabler som finns på sidan och skickar dem sedan som en bildbegäran till Adobe. Du kan kringgå bildbiblioteken helt och hållet och skicka en bildbegäran manuellt till Adobe. Den här metoden kräver att du manuellt formulerar bildbegäran och frågesträngen.

Den här implementeringsmetoden kan användas på alla plattformar som visar bilder från externa källor. Den förlitar sig inte alls på JavaScript.

>[!NOTE]
>
>Maskinkodade bildbegäranden är enkla att konfigurera, men de är svåra att felsöka, underhålla och skala i större projekt. Kontrollera att hårdkodade bildbegäranden är det bästa alternativet för dig innan du fortsätter.

## Syntax för bildbegäran

Följande är ett exempel på maskinkodad bildbegäran med HTML:

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1/s234234238479?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` anger protokollet. Matcha det protokoll som används i bildbegäran med det protokoll som används av resten av din plats.
* `example.data.adobedc.net` är värdet som finns i [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variabel.
* `/b/ss/` ingår i alla bildbegäranden. Den ingår i filstrukturen för bilder som lagras på datainsamlingsservrar i Adobe.
* `examplersid` är det rapportsvit-ID som du vill skicka data till. Separera ID:n med kommatecken och inga mellanslag (t.ex. `examplersid1,examplersid2` och så vidare).
* `/1/` är träffkällan. Se `hit_source` under [Referens för datakolumn](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) i Exportera användarhandbok. Styr i vilken ordning cookies och andra metoder används för att identifiera besökare.
* `/s234234238479` (`"s"` + ett slumpmässigt tal) hindrar webbläsaren från att cachelagra bildbegäran.
* Allt efter frågesträngsavgränsaren (`?`) är data som du vill inkludera i rapporter. Se [Frågeparametrar för datainsamling](../validate/query-parameters.md) om du vill ha en fullständig lista över parametrar som du kan ta med i en bildbegäran.

## Maskinkodade bildbegäranden i Microsoft Outlook

Eftersom de flesta e-postmeddelanden är HTML-baserade går det att spåra e-postmeddelanden som är öppna och skicka dessa data till Adobe Analytics. Observera följande om din organisation väljer att använda den här metoden:

* Varje e-postrendering kan öka antalet fakturerbara serversamtal.
* Endast e-postklienter som stöder HTML och tillåter bilder spåras. Vissa e-postklienter, till exempel Microsoft Outlook, blockerar externa bilder som standard. Dessa e-postmeddelanden spåras inte förrän mottagaren väljer att hämta externa bilder.

Så här skapar du ett Outlook-e-postmeddelande som innehåller en bildbegäran:

1. Öppna en HTML-redigerare. Om det inte finns någon HTML-redigerare fungerar även en vanlig textredigerare.
2. Infoga en hårdkodad bildbegäran i en ny HTML-fil `<img>` tagg som omsluts av `<body>` -tagg.
3. Spara filen HTML.
4. Öppna Microsoft Outlook och skapa ett e-postmeddelande.
5. Gå till fliken Infoga och klicka på **Bifoga fil**. Markera HTML-filen för bildförfrågan.
6. Klicka på snabbmenyn bredvid Infoga och välj **Infoga som text**. Om du klickar på knappen Infoga utan snabbmenyn blir HTML-filen en bifogad fil som inte fungerar.

E-postmeddelandet verkar inte ändras eftersom bildbegäran är en 1x1-genomskinlig pixel. Om du vill visa bildbegäran för testning ändrar du filen HTML så att den innehåller en kantlinje, ytterligare text eller annat innehåll.

## Vanliga frågor och svar

Lär dig mer om vanliga frågor med hjälp av hårdkodade bildbegäranden.

### Är frågesträngsparametrar skiftlägeskänsliga?

Ja. Kontrollera att frågesträngsparametrarna matchar varandra exakt, annars registreras de inte. Till exempel: `pagename` är inte en giltig frågesträngsparameter, medan `pageName` är.

### Kan jag inkludera blanksteg i frågesträngen?

Värdena för var och en av frågesträngsparametrarna är URL-kodade. URL-kodning konverterar tecken som normalt är ogiltiga i URL-adresser till giltiga tecken. Ett blanksteg konverteras till exempel till `%20`. Kontrollera att alla tecken som inte är alfanumeriska är URL-kodade. Adobe URL-avkodar automatiskt värden när bildbegäranden når datainsamlingsservrar.

Se [HTML URL-kodningsreferens](https://www.w3schools.com/tags/ref_urlencode.asp) på W3Schools för mer information om hur URL-kodning fungerar.

### Vilket är det högsta antalet tecken ett enskilt värde kan ha?

Varje variabel har olika maxlängd. De flesta trafikvariabler innehåller upp till 100 byte, medan de flesta konverteringsvariabler innehåller upp till 255 byte. När en bildbegäran når datainsamlingsservrar trunkerar Adobe automatiskt dessa värden till sin maximala längd.
