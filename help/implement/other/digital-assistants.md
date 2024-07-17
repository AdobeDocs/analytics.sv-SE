---
title: Implementera analyser för digitala assistenter
description: Implementera Adobe Analytics på Digital Assistants, som Amazon Alexa eller Google Home.
feature: Implementation Basics
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '1258'
ht-degree: 0%

---

# Implementera analyser för digitala assistenter

I och med de senaste framstegen när det gäller cloud computing, maskininlärning och naturlig språkbearbetning blir digitala assistenter en del av vardagen. Konsumenterna börjar prata med sina enheter och förväntar sig att de ska förstå och reagera på ett mänskligt sätt. När dessa plattformar blir mer etablerade kan varumärken presentera sina tjänster för konsumenterna på samma realistiska och verklighetstrogna sätt. Konsumenterna kan till exempel ställa frågor som:

* &quot;Alexa, fråga min bil när den behöver en olje.&quot;
* &quot;Cortana, vad är saldot för mitt checkkonto?&quot;
* &quot;Siri, skicka John $20 till middag igår kväll från min bankapp.&quot;

Den här sidan innehåller en översikt över hur du bäst använder Adobe Analytics för att mäta och optimera den här typen av upplevelser.

## Översikt över arkitekturen för digitala upplevelser

![Digital Assistant-arbetsflöde](assets/Digital-Assitants.png)

De flesta digitala assistenter har idag en liknande högnivåarkitektur:

1. **Enhet**: Det finns en enhet (som Amazon Echo eller en telefon) med en mikrofon som gör att användaren kan ställa en fråga.
1. **Digital assistent**: Den enheten interagerar med den tjänst som driver den digitala assistenten. Det är där talet konverteras till maskinläsliga återgivningar och detaljerna i begäran tolkas. När användarens avsikt är klar skickar den digitala assistenten förfrågningens avsikt och information till det program som hanterar begäran.
1. **&quot;App&quot;**: Appen kan antingen vara en app på telefonen eller en röstapp. Programmet ansvarar för att svara på begäran. Den svarar på den digitala assistenten och den digitala assistenten svarar sedan på användaren.

## Var ska Analytics implementeras?

En av de bästa platserna att implementera Analytics är i appen. Appen får återgivning och information från den digitala assistenten och sedan avgör appen hur den ska svara.

Det finns två gånger under en begäran som kan vara till hjälp när du vill skicka data till Adobe Analytics.

1. När förfrågan skickas till din app.
1. När svaret har returnerats från appen.

Om du bara är intresserad av att spela in vad som hände med kunden för framtida optimering skickar du en förfrågan till Adobe Analytics när svaret har returnerats. Du får det fullständiga sammanhanget för vad begäran var och hur systemet svarade.

## Nya installationer

För vissa digitala assistenter får du ett meddelande när någon installerar kompetensen, särskilt när det gäller autentisering. Adobe rekommenderar att du skickar en Install-händelse genom att ange kontextdatavariabeln `a.InstallEvent=1`. Den här funktionen är inte tillgänglig för alla digitala assistenter, men den är användbar när den är till för att se lojalitet. Följande kodexempel skickar värdena Install event, Install Date och AppID till kontextdatavariabler.

```text
GET
/b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://example.data.adobedc.net">
  example.data.adobedc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Flera assistenter eller flera appar

Det är troligt att din organisation vill ha appar för flera plattformar. Det bästa sättet är att inkludera ett program-ID i varje begäran. Den här variabeln kan anges i datavariabeln `a.AppID` context. Följ formatet för `[AppName] [BundleVersion]`, till exempel BigMac för Alexa 1.2:

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Användar-/besökaridentifiering

Adobe Analytics använder [Adobe Experience Cloud identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html) för att knyta interaktioner över tiden till samma person. De flesta digitala assistenter returnerar en `userID` som du kan använda för att behålla aktiviteten för olika användare. I de flesta fall är det här värdet vad du kan skicka in som en unik identifierare. Vissa plattformar returnerar en identifierare som är längre än 100 tecken. I dessa fall rekommenderar Adobe att du hash-kodar den unika identifieraren till ett fast längdvärde med hjälp av en standardhash-algoritm som MD5 eller Sha1.

Att använda ID-tjänsten ger mest värde när du mappar ECID:n på olika enheter (till exempel webb till digital assistent). Om din app är en mobilapp använder du Experience Platform SDK:n som den är och skickar användar-ID:t med metoden `setCustomerID`. Om din app är en tjänst använder du användar-ID:t som tillhandahålls av tjänsten som ECID och anger det i `setCustomerID`.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Sessioner

Eftersom digitala assistenter är konversationer har de ofta begreppet session. Exempel:

**Kund:** &quot;OK Google, ring mig en taxi&quot;

**Google:**: &quot;Visst, vilken tid vill du ha?&quot;

**Konsument:** &quot;20:30&quot;

**Google:** &quot;Låter bra, drivrutinen är vid 08:30&quot;

Sessioner är viktiga för att hålla sammanhanget och för att hjälpa till att samla in mer information för att göra den digitala assistenten mer naturlig. När Analytics implementeras i en konversation finns det två saker att göra när en ny session startas:

1. **Nå ut till Audience Manager**: Hämta relevanta segment som en användare är en del av så att du kan anpassa svaret. (Den här personen är till exempel berättigad till rabatt i flera kanaler.)
2. **Skicka i en ny session eller en starthändelse**: När du skickar det första svaret till Analytics inkluderar du en starthändelse. Vanligtvis kan detta skickas genom att kontextdata för `a.LaunchEvent=1` anges.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Återgivning

Var och en av de digitala assistenterna har algoritmer som identifierar metoder och sedan skickar metoden vidare till&quot;appen&quot; så att appen vet vad den ska göra. Dessa metoder är en kort representation av begäran.

Om en användare till exempel säger&quot;Siri, Skicka John $20 för middag igår kväll från min bankapp&quot; kan avsikten vara något som *sendMoney*.

Genom att skicka in var och en av dessa förfrågningar som eVar kan du köra målningsrapporter för var och en av avsikterna med konversationsappar. Se till att appen även kan hantera förfrågningar utan avsikt. Adobe rekommenderar att du skickar &quot;Ingen metod har angetts&quot; till datavariabeln för intent-kontext, i stället för att utelämna variabeln.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.adobedc.net
Cache-Control: no-cache
```

eller

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Parametrar/platser/entiteter

Förutom avsikten har digitala assistenter ofta en uppsättning nyckel/värde-par som ger information om avsikten. Dessa kan kallas fack, enheter eller parametrar. &quot;Siri, Send John $20 for middag igår kväll from my Banking app&quot; har till exempel följande parametrar:

* Who = John
* Belopp = 20
* Varför = Middag

Det finns vanligtvis ett begränsat antal av dessa värden i din app. Om du vill spåra dessa värden i Analytics skickar du dem till kontextdatavariabler och mappar sedan parametrarna till en eVar.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Fellägen

Ibland förser den digitala assistenten appen med indata som den inte kan hantera. Till exempel&quot;Siri, Send John 20 påsar kol till middag igår kväll från min bankapp&quot;

När det här inträffar ber din app om klargöranden. Skicka dessutom data till Adobe som anger att programmet har ett feltillstånd tillsammans med en eVar som anger vilken typ av fel som uppstod. Se till att du inkluderar fel där indata inte är korrekta och fel där programmet hade problem.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Enhetsfunktioner

De flesta plattformar visar inte den enhet som användaren pratade med, men de visar faktiskt enhetens funktioner. Till exempel ljud, skärm, video osv. Den här informationen är användbar eftersom den definierar vilka typer av innehåll som kan användas när du interagerar med användarna. När du mäter enhetsfunktioner är det bäst att sammanfoga dem (i alfabetisk ordning).

Exempel: `":Audio:Camera:Screen:Video:"`

Inledande och avslutande kolon är till hjälp när du skapar segment. Visa till exempel alla träffar med `:Audio:`-funktioner.

* [Amazon Capabilities](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) med Amazon Alexa
* [Google Capabilities](https://developers.google.com/actions/assistant/surface-capabilities) med funktionsmakron i Google

## Exempel

| Person | Enhetssvar | Åtgärd/återgivning | Begäran om GET |
|---|---|---|---|
| Installera Spoofify | Inget svar | Installera | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Spela upp Spoofify | &quot;Okej, spela Spoofify&quot; | Spela upp | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Ändra låt | &quot;Vilken låt vill du ha?&quot; | ChangeSong | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Spela &quot;Baby Shark&quot; | &quot;Okej, spela &quot;Baby Shark&quot; av PinkFong&quot; | ChangeSong | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Ändra spelningslista | &quot;Vilken spellista vill du ha?&quot; | ChangePlaylist | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Spela upp min favoritspellista | &quot;Okej, spela din favoritspellista&quot; | ChangePlaylist | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Stäng av musik | Inget svar, musiken stängs av | Av | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
