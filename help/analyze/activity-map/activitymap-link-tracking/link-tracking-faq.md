---
description: Frågor och svar om länkspårning i Activity Map.
title: Vanliga frågor om länkspårning
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: a0b8f61c3728c5867640ce20768614c8d79ca657
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 1%

---

# Vanliga frågor om länkspårning

Frågor och svar om länkspårning i Activity Map.

>[!CAUTION]
>
>Genom att aktivera spårning av Activity Map, **du kan samla in uppgifter om personligt identifierbar information.** Dessa data kan användas fristående eller tillsammans med annan information för att identifiera, kontakta eller hitta en person, eller för att identifiera en individ i sitt sammanhang.

Här är några kända fall där PII-data kan samlas in med Activity Map Tracking:

* `Mailto` länkar. En mailto-länk är en typ av HTML-länk som aktiverar standardklienten för e-post på datorn för att skicka ett e-postmeddelande.
* `User ID` länkar som kan visas i sidhuvudet/sidfoten på en webbplats när användaren har loggat in.
* För finansinstitut kan kontonumret visas som en länk. Om du klickar på den hämtas länktexten.
* Vårdwebbplatser kan också ha PII-data som visas som länkar. Om du klickar på de här länkarna samlas länktexten in, vilket innebär att PII-data samlas in.

## När inträffar länkspårning?

Länk- och regionsidentifiering i Activity Map inträffar när användare klickar på en sida.

## Vad spåras som standard?

Om en klickningshändelse inträffar för ett element måste elementet genomgå vissa kontroller för att avgöra om AppMeasurementet kommer att behandla det som en länk. Detta är kontrollerna:

* Är det här en `A` eller `AREA` tagg med `href` egenskap?
* Finns det en `onclick` ett attribut som anger `s_objectID` variabel?
* Är det här en `INPUT` eller `SUBMIT` en knapp med ett värde eller underordnad text?
* Är det här en `INPUT` tagg med text `IMAGE` och `src` egenskap?
* Är det här en `BUTTON`?

Om svaret är Ja på någon av frågorna ovan behandlas elementet som en länk och spåras.

>[!IMPORTANT]
>
>Button-taggar med attributet type=&quot;button&quot; betraktas inte som länkar som AppMeasurement. Ta bort type=&quot;button&quot; i knapptaggarna och lägg till role=&quot;button&quot; eller submit=&quot;button&quot; i stället.

>[!IMPORTANT]
>
>En ankartagg med &quot;href&quot; som börjar med &quot;#&quot; betraktas som en intern målplats som AppMeasurement, inte som en länk (eftersom du inte lämnar sidan.) Som standard spårar inte Activity Map dessa interna målplatser. Det spårar bara länkar som navigerar användaren till en ny sida.

## Hur spårar Activity Map andra visuella HTML-element?

a. Via `s.tl()` funktion.

Om klickningen inträffade via en `s.tl()` anrop, får Activity Map också klickhändelsen och avgör om ett `linkName` strängvariabel hittades. Under `s.tl()` kommer linkName att anges som Activity Map Link ID. Det element som användaren klickade på och som gav upphov till `s.tl()` används för att avgöra regionen. Exempel:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Via `s_objectID` variabel. Exempel:

    &quot; 
    
    &lt;img onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot; src=&quot;someimageurl.png&quot; />
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot;>
    Länka text hit
    &lt;/a>
    
    &quot;

>[!IMPORTANT]
>
>Ett avslutande semikolon (;) krävs när du använder `s_objectID` i Activity Map.

## Kan du ge mig några exempel på länkar som kommer att spåras?

### Exempel 1

```
  <a href="/home>Home</a>
```

### Exempel 2

```
 <input type="submit" value="Submit"/>
```

### Exempel 3

```
  <input type="image" src="submit-button.png"/>
```

### Exempel 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### Exempel 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Kan du ge mig några exempel på länkar som INTE kommer att spåras?

1. Orsak: Ankartaggen har inte en giltig `href`:
   `<a name="innerAnchor">Section header</a>`

1. Orsak: Ingendera `s_ObjectID` eller `s.tl()` närvarande:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Orsak: Ingendera `s_ObjectID` eller `s.tl()` närvarande:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Orsak: &quot;src&quot;-egenskapen saknar ett formulärelement:

   `<input type="image"/>`

