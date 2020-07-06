---
title: Integrera modul
description: Med Integrate Module kan Adobe-partners integrera sina datainsamlingsaktiviteter med din organisation.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 3%

---


# Integrera modul

Med Integrate Module kan Adobe-partners integrera sina datainsamlingsaktiviteter med din organisation. Den här integreringen ger möjlighet till en dubbelriktad dataanslutning. Användningen av integreringsmodulen styrs vanligtvis av en Adobe-partner.

>[!NOTE]
>
>Om du begär partnerdata i implementeringen kan det öka fördröjningen mellan sidinläsning och data som skickas till Adobes datainsamlingsservrar. Om en besökare läser in en ny sida innan data skickas, registreras inte den sidan.

## Integrera modularbetsflöde

1. En besökare på webbplatsen läser in en sida som initierar en begäran om `get` partnerdata.
2. Adobe-partnern tar emot `get` begäran och paketerar lämpliga variabler i ett JSON-objekt. JSON-objektet returneras.
3. Din webbplats tar emot JSON-objektet och anropar `setVars` för att tilldela information i JSON-objektet till Adobe Analytics-variabler
4. En bildbegäran skickas till Adobes datainsamlingsservrar.

## Integrera modulimplementering

En organisation som arbetar med en Adobe-partner kan använda dessa steg för att börja använda Integrate-modulen.

### Hämta integreringsmodulkod

För att få tillgång till modulkod krävs en användare med produktadministratörsåtkomst eller som tillhör en produktprofil med tillgång till Code Manager. Metoden för att hämta modulkod är densamma för alla implementeringsmetoder, inklusive Adobe Experience Platform Launch.

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
1. In the top navigation, click [!UICONTROL Admin] > [!UICONTROL Code Manager].
1. Hämta det senaste JavaScript AppMeasurement-biblioteket.
1. När du har laddat ned filen packar du upp den och letar upp `AppMeasurement_Module_Integrate.js`.

### Placera integreringsmodulen i implementeringen

Du måste ha tillgång till Adobe Experience Platform Launch för att kunna implementera integreringsmodulen på din webbplats. Om du använder en äldre JavaScript-implementering måste du ha tillgång till organisationens källkod för webbplatsen.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Klicka på den Launch-egenskap som du vill redigera.
3. Klicka på fliken Tillägg och sedan på Konfigurera under Adobe Analytics.
4. Öppna dragspelet Konfigurera spåraren med egen kod och klicka sedan på &lt;/> Öppna redigerare.
5. Klistra in integrate-modulkoden i det modala kodfönstret. Klicka på Spara när du är klar.

## Integrera modulmetoder

När Integrate Module har implementerats använder du dessa metoder för att konfigurera den så att den skickar och tar emot data från önskad Adobe-partner.

### add

Metoden `add` instansierar ett partnerobjekt, som fungerar som ett mellanlager av variabeldata när data delas mellan partnersystem och implementeringen. Den här metoden krävs för alla integreringar. Ett separat partnerobjekt måste användas för varje unik partner om flera partner används i en och samma implementering.

```JavaScript
s.Integrate.add("<partner_name>");
```

Din organisation arbetar vanligtvis tillsammans med en Adobe-partner för att fastställa värdet för partnernamnet.

### beacon

Metoden skapar en bildbegäran och pekar den mot den angivna URL:en. `beacon` Dessa bildbegäranden skiljer sig från vanliga bildbegäranden. Beacon-metoden skickar vanligtvis data till Adobe-partnern i stället för till Adobes datainsamlingsservrar.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

Din organisation arbetar vanligtvis tillsammans med Adobe-partnern för att fastställa värdet för partnernamnet. Frågesträngar som ingår i URL:en är valfria och beroende av partner. Modulen Integrera innehåller automatiskt en frågesträng som innehåller ett slumpmässigt tal för att förhindra webbläsarcachelagring.

### fördröjning

Adobe arbetar internt med team för att dokumentera denna metod.

### get

Med metoden kan `get` en klient importera partnervariabler och lagra dem i partnerobjektet. När data finns i partnerobjektet kan de tilldelas till Analytics-variabler och skickas i en bildbegäran. Den här metoden anropar en URL som pekar på ett JSON-objekt som innehåller önskade data.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Partnernamn:** Din organisation arbetar vanligtvis tillsammans med Adobe-partnern för att fastställa värdet för partnernamnet.
* **URL till JSON-objekt:** URL:en till ett JSON-objekt som innehåller de partnervariabler som ska inkluderas i en bildbegäran.
* **Frågesträngsparametrar:** Partnerkontoinformation som identifierar din organisation i partnersystemet. Adobe-partnern använder den här informationen för att identifiera din datauppsättning.

Modulen Integrera lägger automatiskt till fler frågesträngar till URL:en. En var-frågesträng anger namnet på det JSON-objekt som modulen förväntar sig från partnern. Ett slumpmässigt tal läggs också till för att förhindra webbläsarcachelagring.

### klar

Adobe arbetar internt med team för att dokumentera denna metod.

### useVars

Med den här `useVars` metoden kan klienten dela variabelvärden med en Adobe-partner.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

Din organisation arbetar vanligtvis tillsammans med en Adobe-partner för att fastställa värdena för partnernamnet och de variabler som partnern använder.

### setVars

Med `setVars` metoden kan klienten fylla i Analytics-variabler med partnerdata som hämtats. Partnerdata kan vara resultatet av en `get` metod, en statisk tilldelning eller någon annan mekanism som fyller i partnerobjektet med data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

Din organisation arbetar vanligtvis tillsammans med en Adobe-partner för att fastställa värdena för partnernamnet och de variabler som partnern använder.

### script

Med metoden kan en Adobe-partner anropa ytterligare JavaScript från partnerwebbplatsen om vissa villkor uppfylls (till exempel om kampanjvariabeln är inställd). `script`

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

Din organisation arbetar vanligtvis tillsammans med Adobe-partnern för att fastställa värdet för partnernamnet. Frågesträngar som ingår i URL:en är valfria och beroende av partner. Modulen Integrera innehåller automatiskt en frågesträng som innehåller ett slumpmässigt tal för att förhindra webbläsarcachelagring.
