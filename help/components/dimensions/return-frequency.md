---
title: Returfrekvens
description: Den paketerade tiden mellan det aktuella besöket och det föregående besöket.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---


# Returfrekvens

Dimensionen &#39;Returfrekvens&#39; visar hur lång tid det tar mellan besöken och besökarna. När en besökare kommer tillbaka till er webbplats tittar Adobe på hur länge sedan det förra besöket var och låser träffen i rätt dimensionsvärde. Den här dimensionen är värdefull för att du ska kunna mäta webbplatsens attraktion och relevans för besökarna över tid. Det kan också hjälpa till att identifiera effekten av webbplatsens innehåll och kampanjer för besökarna.

>[!TIP]
>
>Denna dimension omfattar inte förstagångsbesökare.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

Data för denna dimension anges vid den första besöksträffen och gäller tills hela besöket är klart. Värdet kan inte ändras efter mitt besök.

## Dimensionsvärden

Dimensionsvärdena inkluderar tidsbaserade bucklar, beroende på hur lång tid det tar från det föregående besöket.

* Mindre än 1 dag
* 1 till 3 dagar
* 3 till 7 dagar
* 7 till 14 dagar
* 14 dagar till 1 månad
* Längre än 1 månad

## Dimensionsvärden visas under bucket utanför projektets datumintervall

När du anger ett projekts datumintervall är det vanligt att visa dimensionsvärdeattribut för besök utanför datumintervallet. En besökare kommer till exempel till din webbplats i juli och kommer sedan tillbaka två gånger på samma dag i september. Frekvensdimensionen för återvändande för september skulle visa ett besök under&quot;Längre än 1 månad&quot; och ett besök under&quot;Mindre än 1 dag&quot;.