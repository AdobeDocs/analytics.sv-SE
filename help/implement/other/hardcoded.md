---
title: Implementera med hårdkodade bildbegäranden
description: Implementera Adobe Analytics med en HTML-bildtagg (hårdkodad bildbegäran)
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
source-git-commit: de0424db27f9d1a3ce07632df8fd5e76b4d7bb4c
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Implementera med hårdkodade bildbegäranden

AppMeasurement-bibliotek från Adobe kompilerar variabler som finns på sidan och skickar dem sedan som en bildbegäran till Adobe. Du kan kringgå AppMeasurement-bibliotek helt och hållet och manuellt skicka en bildbegäran till Adobe. Den här metoden kräver att du manuellt formulerar bildbegäran och frågesträngen.

Den här implementeringsmetoden kan användas på alla plattformar som visar bilder från externa källor. Den förlitar sig inte alls på JavaScript.

>[!NOTE]
>
>Maskinkodade bildbegäranden är enkla att konfigurera, men de är svåra att felsöka, underhålla och skala i större projekt. Kontrollera att hårdkodade bildbegäranden är det bästa alternativet för dig innan du fortsätter.

## Syntax för bildbegäran

Följande är ett exempel på hårdkodad bildbegäran med HTML:

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` anger protokollet. Matcha det protokoll som används i bildbegäran med det protokoll som används av resten av din plats.
* `example.data.adobedc.net` är värdet i  [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variabeln.
* `/b/ss/` ingår i alla bildbegäranden. Den ingår i filstrukturen för bilder som lagras på datainsamlingsservrar i Adobe.
* `examplersid` är det rapportsvit-ID som du vill skicka data till. Separera ID:n med kommatecken och inga mellanslag (till exempel `examplersid1,examplersid2`) för flera rapportsviter.
* `/1/` är träffkällan. Se `hit_source` under [Datakolumnreferens](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) i användarhandboken för Export. Styr i vilken ordning cookies och andra metoder används för att identifiera besökare.
* Allt efter frågesträngsavgränsaren (`?`) är data som du vill ta med i rapporter. Se [Frågeparametrar för datainsamling](../validate/query-parameters.md) för en fullständig lista över parametrar som du kan ta med i en bildbegäran.

## Maskinkodade bildbegäranden i Microsoft Outlook

Eftersom de flesta e-postmeddelanden är HTML-baserade går det att spåra e-postmeddelanden som är öppna och skicka dessa data till Adobe Analytics. Observera följande om din organisation väljer att använda den här metoden:

* Varje e-postrendering kan öka antalet fakturerbara serversamtal.
* Endast e-postklienter som stöder HTML och tillåter bilder spåras. Vissa e-postklienter, till exempel Microsoft Outlook, blockerar externa bilder som standard. Dessa e-postmeddelanden spåras inte förrän mottagaren väljer att hämta externa bilder.

Så här skapar du ett Outlook-e-postmeddelande som innehåller en bildbegäran:

1. Öppna en HTML-redigerare. Om en HTML-redigerare inte är tillgänglig fungerar även en vanlig textredigerare.
2. I en ny HTML-fil infogar du en hårdkodad bildbegäran `<img>`-tagg i en `<body>`-tagg.
3. Spara HTML-filen.
4. Öppna Microsoft Outlook och skapa ett e-postmeddelande.
5. Gå till fliken Infoga och klicka på **Bifoga fil**. Välj en HTML-fil för bildbegäran.
6. Klicka på snabbmenyn bredvid Infoga och välj **Infoga som text**. Om du klickar på knappen Infoga utan snabbmenyn, blir HTML-filen en bifogad fil som inte fungerar.

E-postmeddelandet verkar inte ändras eftersom bildbegäran är en 1x1-genomskinlig pixel. Om du vill se bildbegäran för testning ändrar du HTML-filen så att den innehåller en kantlinje, ytterligare text eller annat innehåll.

## Vanliga frågor

Lär dig mer om vanliga frågor med hjälp av hårdkodade bildbegäranden.

### Är frågesträngsparametrar skiftlägeskänsliga?

Ja. Kontrollera att frågesträngsparametrarna matchar varandra exakt, annars registreras de inte. Till exempel är `pagename` inte en giltig frågesträngsparameter, medan `pageName` är det.

### Kan jag inkludera blanksteg i frågesträngen?

Värdena för var och en av frågesträngsparametrarna är URL-kodade. URL-kodning konverterar tecken som normalt är ogiltiga i URL-adresser till giltiga tecken. Ett blankstegstecken konverteras till exempel till `%20`. Kontrollera att alla tecken som inte är alfanumeriska är URL-kodade. Adobe URL-avkodar automatiskt värden när bildbegäranden når datainsamlingsservrar.

Mer information om hur URL-kodning fungerar finns i [HTML URL-kodningsreferens](https://www.w3schools.com/tags/ref_urlencode.asp) på W3Schools.

### Vilket är det högsta antalet tecken ett enskilt värde kan ha?

Varje variabel har olika maxlängd. De flesta trafikvariabler innehåller upp till 100 byte, medan de flesta konverteringsvariabler innehåller upp till 255 byte. När en bildbegäran når datainsamlingsservrar trunkerar Adobe automatiskt dessa värden till sin maximala längd.
