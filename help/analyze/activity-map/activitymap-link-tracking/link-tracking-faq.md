---
description: Frågor och svar om länkspårning i Activity Map.
title: Vanliga frågor om länkspårning
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 1%

---

# Vanliga frågor om länkspårning

Frågor och svar om länkspårning i Activity Map.

>[!CAUTION]
>
>Genom att aktivera spårning av Activity Map kan **du samla in data om personligt identifierbar information (PII).** Dessa data kan användas fristående eller tillsammans med annan information för att identifiera, kontakta eller hitta en person, eller för att identifiera en individ i sitt sammanhang.

Här är några kända fall där PII-data kan samlas in med Activity Map Tracking:

* `Mailto` länkar. En mailto-länk är en typ av HTML-länk som aktiverar standardklienten för e-post på datorn för att skicka ett e-postmeddelande.
* `User ID` länkar som kan visas i sidhuvudet/sidfoten på en webbplats när användaren har loggat in.
* För finansinstitut kan kontonumret visas som en länk. Om du klickar på den hämtas länktexten.
* Vårdwebbplatser kan också ha PII-data som visas som länkar. Om du klickar på de här länkarna samlas länktexten in, vilket innebär att PII-data samlas in.

## När inträffar länkspårning?

Länk- och regionsidentifiering i Activity Map inträffar när användare klickar på en sida.

## Vad spåras som standard?

Om en klickningshändelse inträffar för ett element måste elementet genomgå vissa kontroller för att avgöra om AppMeasurement kommer att behandla det som en länk. Detta är kontrollerna:

* Är detta en `A`- eller `AREA`-tagg med en `href`-egenskap?
* Finns det ett `onclick`-attribut som anger en `s_objectID`-variabel?
* Är det här en `INPUT`-tagg eller `SUBMIT`-knapp med ett värde eller en underordnad text?
* Är detta en `INPUT`-tagg med typen `IMAGE` och en `src`-egenskap?
* Är detta en `BUTTON`?

Om svaret är Ja på någon av frågorna ovan behandlas elementet som en länk och spåras.

>[!IMPORTANT]
>
>Button-taggar med attributet type=&quot;button&quot; betraktas inte som länkar av AppMeasurement. Ta bort type=&quot;button&quot; i knapptaggarna och lägg till role=&quot;button&quot; eller submit=&quot;button&quot; i stället.

>[!IMPORTANT]
>
>En ankartagg med href som börjar med # betraktas som en intern målplats med AppMeasurement, inte som en länk (eftersom du inte lämnar sidan). Som standard spårar inte Activity Map dessa interna målplatser. Det spårar bara länkar som navigerar användaren till en ny sida.

## Hur spårar Activity Map andra visuella HTML-element?

a. Via funktionen `s.tl()`.

Om klickhändelsen inträffade via ett `s.tl()`-anrop får Activity Map även klickhändelsen och avgör om en `linkName`-strängvariabel hittades. Under `s.tl()`-körningen anges detta linkName som Activity Map Link-ID. Det element som klickades på och som härstammar från `s.tl()`-anropet används för att avgöra regionen. Exempel:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Via variabeln `s_objectID`. Exempel:

    &quot;
    
    &lt;a>&lt;img>&lt;/a>
    
    &lt;a>Länka text här&lt;/a>
    
    
    &quot;

>[!IMPORTANT]
>
>Ett avslutande semikolon (;) krävs när du använder `s_objectID` i Activity Map.

## Kan du ge mig några exempel på länkar som kommer att spåras?

### Exempel 1

```
  <a hef="/home?lang=en>Home</a>
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

1. Orsak: Ankartaggen har ingen giltig `href`:
   `<a name="innerAnchor">Section header</a>`

1. Orsak: Varken `s_ObjectID` eller `s.tl()` finns:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Orsak: Varken `s_ObjectID` eller `s.tl()` finns:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Orsak: Egenskapen &quot;src&quot; saknar ett formulärelement:

   `<input type="image"/>`
