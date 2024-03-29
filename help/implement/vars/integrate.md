---
title: Integrera modul
description: Med Integrate Module kan Adobe partners integrera sina datainsamlingsaktiviteter med din organisation.
feature: Variables
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 2%

---

# Integrera modul

Med Integrate Module kan Adobe partners integrera sina datainsamlingsaktiviteter med din organisation. Den här integreringen ger möjlighet till en dubbelriktad dataanslutning. Användning av Integrate-modulen styrs vanligtvis av en Adobe-partner.

>[!NOTE]
>
>Om du begär partnerdata i implementeringen kan det öka fördröjningen mellan sidinläsning och data som skickas till datainsamlingsservrar i Adobe. Om en besökare läser in en ny sida innan data skickas, registreras inte den sidan.

## Integrera modularbetsflöde

1. En besökare på webbplatsen läser in en sida som initierar en `get` begäran om partnerdata.
2. Adobe-partnern får `get` begär och paketerar lämpliga variabler i ett JSON-objekt. JSON-objektet returneras.
3. Din webbplats tar emot JSON-objektet och anropar `setVars` för att tilldela Adobe Analytics-variabler informationen i JSON-objektet
4. En bildbegäran skickas till datainsamlingsservrar i Adobe.

## Integrera modulimplementering

En organisation som arbetar med en Adobe-partner kan använda dessa steg för att börja använda Integrate-modulen.

### Hämta integreringsmodulkod

För att få tillgång till modulkod krävs en användare med produktadministratörsåtkomst eller som tillhör en produktprofil med tillgång till Code Manager. Metoden för att hämta modulkod är densamma för alla implementeringsmetoder, inklusive taggar i Adobe Experience Platform.

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
1. I den övre navigeringen klickar du på **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]**.
1. Ladda ned det senaste JavaScript-biblioteket för AppMeasurement.
1. När du laddat ned filen packar du upp den och letar upp `AppMeasurement_Module_Integrate.js`.

### Placera integreringsmodulen i implementeringen

Du måste ha tillgång till Adobe Experience Platform Data Collection för att kunna implementera integreringsmodulen på din webbplats. Om du använder en äldre JavaScript-implementering måste du ha tillgång till organisationens källkod för webbplatsen.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på taggegenskapen som du vill redigera.
1. Klicka på fliken Tillägg och sedan på Konfigurera under Adobe Analytics.
1. Öppna dragspelet Konfigurera spåraren med egen kod och klicka sedan på &lt;/> Öppna redigerare.
1. Klistra in integrate-modulkoden i det modala kodfönstret. Klicka på Spara när du är klar.

## Integrera modulmetoder

När integreringsmodulen har implementerats använder du dessa metoder för att konfigurera den så att den skickar och tar emot data från den önskade Adobe-partnern.

### lägg till

The `add` -metoden instansierar ett partnerobjekt, som fungerar som ett mellanlager av variabeldata när data delas mellan partnersystem och implementeringen. Den här metoden krävs för alla integreringar. Ett separat partnerobjekt måste användas för varje unik partner om flera partner används i en och samma implementering.

```JavaScript
s.Integrate.add("<partner_name>");
```

Din organisation arbetar vanligtvis tillsammans med en Adobe-partner för att fastställa värdet för partnernamnet.

### beacon

The `beacon` skapar en bildbegäran och pekar den mot den angivna URL:en. Dessa bildbegäranden skiljer sig från vanliga bildbegäranden. Beacon-metoden skickar vanligtvis data till partnern Adobe i stället för till datainsamlingsservrarna i Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

Din organisation arbetar vanligtvis tillsammans med Adobe-partnern för att fastställa värdet för partnernamnet. Frågesträngar som ingår i URL:en är valfria och beroende av partner. Modulen Integrera innehåller automatiskt en frågesträng som innehåller ett slumpmässigt tal för att förhindra webbläsarcachelagring.

### fördröjning

Adobe samarbetar internt med team för att få denna metod dokumenterad.

### get

The `get` -metoden gör att en klient kan importera partnervariabler och lagra dem i partnerobjektet. När data finns i partnerobjektet kan de tilldelas Analytics-variabler och skickas i en bildbegäran. Den här metoden anropar en URL som pekar på ett JSON-objekt som innehåller önskade data.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Partnernamn:** Din organisation arbetar vanligtvis tillsammans med Adobe-partnern för att fastställa värdet för partnernamnet.
* **URL till JSON-objekt:** URL:en till ett JSON-objekt som innehåller de partnervariabler som ska inkluderas i en bildbegäran.
* **Frågesträngsparametrar:** Partnerkontoinformation som identifierar din organisation i partnersystemet. Adobe-partnern använder den här informationen för att identifiera din datauppsättning.

Modulen Integrera lägger automatiskt till fler frågesträngar till URL:en. En var-frågesträng anger namnet på det JSON-objekt som modulen förväntar sig från partnern. Ett slumpmässigt tal läggs också till för att förhindra webbläsarcachelagring.

### klar

Adobe samarbetar internt med team för att få denna metod dokumenterad.

### useVars

The `useVars` gör att klientens variabelvärden kan delas med en Adobe-partner.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

Din organisation arbetar vanligtvis tillsammans med en Adobe-partner för att fastställa värdena för partnernamnet och de variabler som partnern använder.

### setVars

The `setVars` gör att klienten kan fylla i Analytics-variabler med partnerdata som hämtats. Partnerdata kan vara resultatet av en `get` -metod, en statisk tilldelning eller någon annan mekanism som fyller i partnerobjektet med data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

Din organisation arbetar vanligtvis tillsammans med en Adobe-partner för att fastställa värdena för partnernamnet och de variabler som partnern använder.

### script

The `script` kan en Adobe-partner anropa ytterligare JavaScript från partnerwebbplatsen om vissa villkor uppfylls (till exempel om kampanjvariabeln är inställd).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

Din organisation arbetar vanligtvis tillsammans med Adobe-partnern för att fastställa värdet för partnernamnet. Frågesträngar som ingår i URL:en är valfria och beroende av partner. Modulen Integrera innehåller automatiskt en frågesträng som innehåller ett slumpmässigt tal för att förhindra webbläsarcachelagring.
