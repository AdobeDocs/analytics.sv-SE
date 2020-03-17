---
description: 'null'
title: Felsökning av segmentering
uuid: 8476d617-4b44-4ff2-9b3a-02685f666afc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Felsökning av segmentering

## Fel: &quot;Inkompatibla element i det här segmentet&quot; {#section_B167EE10A0844E649DD7E14D0BAEDA17}

Det här felet inträffar när du försöker spara ett segment i datalagermappen där segmentet innehåller element som inte är kompatibla med datalagret. Gör något av två för att lösa det här felet:

* Spara segmentet i en annan mapp
* Ta bort eller ändra inkompatibla delar av segmentet.

## Varför returnerar mitt segment inga data alls? {#section_999749CBBE984142AEA49A6E68E6730A}

Möjliga orsaker:

* Invertera kapsling - t.ex. kapsling av en besökarbehållare under en besöksbehållare.
* Rapporten stöder inte segmentering.
* Det finns inga data som matchar segmenteringskriterierna.

## Varför kan jag inte se segmentet jag skapade i segmenthanteraren? {#section_BE0A0930A2694A23BB32DA71696D52CE}

Möjliga orsaker:

* Vissa dimensioner är bara tillgängliga i datalagret och inte i segmenthanteraren.
* Segmentet är inte kompatibelt med rapporter och analyser.
* Segmentet kontrolleras bara för en viss rapportserie.
* Ett delat segment kan ha tagits bort av en annan användare.
* Det gick inte att läsa in segment på grund av ett datacenter- eller webbläsarcachefel.
* Segmentet har inte sparats.
* IP-adressen kan blockeras vid användarens slut.

## Varför verkar de siddata som visas när du har använt ett segment felaktigt? {#section_B226AF69FE06463A8BC5337FDA8D4949}

Möjliga orsaker:

* Regler/operatorer är felaktiga för det obligatoriska resultatet.
* Felaktig användning av behållare i segmentet.
* Trafikvariablerna som används för segmentering är inte korrekt inställda eller har gått ut.

