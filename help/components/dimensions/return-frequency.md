---
title: Returfrekvens
description: Den paketerade tiden mellan det aktuella besöket och det föregående besöket.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Returfrekvens

Dimensionen &#39;Returfrekvens&#39; visar den tid som går mellan besök från återkommande besökare. När en besökare kommer tillbaka till er webbplats tittar Adobe på hur länge sedan det förra besöket var och låser träffen i rätt dimensionsobjekt. Den här dimensionen är värdefull för att du ska kunna mäta webbplatsens attraktion och relevans för besökarna över tid. Det kan också hjälpa till att identifiera effekten av webbplatsens innehåll och kampanjer för besökarna.

>[!TIP]
>
>Denna dimension omfattar inte förstagångsbesökare.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

Data för denna dimension anges vid den första besöksträffen och gäller tills hela besöket är klart. Värdet kan inte ändras efter mitt besök.

## Dimensioner

Dimensionen innehåller tidsbaserade bucklor, beroende på hur lång tid de har passerat från sitt tidigare besök.

* Mindre än 1 dag
* 1 till 3 dagar
* 3 till 7 dagar
* 7 till 14 dagar
* 14 dagar till 1 månad
* Längre än 1 månad

## Dimensioner visas under bucket utanför projektets datumintervall

När du anger ett projekts datumintervall är det vanligt att visa attribut för dimensionsobjekt för besök utanför datumintervallet. En besökare kommer till exempel till din webbplats i juli och kommer sedan tillbaka två gånger på samma dag i september. Frekvensdimensionen för återvändande för september skulle visa ett besök under&quot;Längre än 1 månad&quot; och ett besök under&quot;Mindre än 1 dag&quot;.
