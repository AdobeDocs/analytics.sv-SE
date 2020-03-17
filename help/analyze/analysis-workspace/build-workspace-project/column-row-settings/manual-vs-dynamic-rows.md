---
description: Så här interagerar du med statiska rader i tabeller.
title: Statiska kontra dynamiska rader
uuid: caf033ef-d252-4f8a-802e-7edbbac5c8c0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Statiska kontra dynamiska rader

Tabellerna för Analysis Workspace genererar&quot;dynamiska&quot; rader när du släpper en dimension i tabellen, vilket innebär att alla objekt som motsvarar dimensionen, för ett givet mått, hämtas till tabellen.

När du till exempel drar webbläsardimensionen till tabellen, alla dess dimensionsobjekt (t.ex. Android-webbläsare, Mobile Safari, Firefox) dras dynamiskt in i bordet.

Om du däremot manuellt markerar och släpper ett visst mått, segment, dataområde eller enskilt dimensionsobjekt i en tabell blir resultatet en hårdkodad eller&quot;statisk&quot; rad eller lista. Du kan nu interagera med en statisk rad på följande sätt:

* Klicka på ikonen Förhandsgranska i statiska rader där du kan förhandsgranska segment, mätvärden och datumintervall.
* Klicka på x-ikonen för att ta bort raden från tabellen.
* Begränsa hur många rader som ska visas och aktivera sidindelning.
* Lägg till&quot;blandade dimensionsobjekt&quot;. Lägg till exempel till en artikel från en webbläsardimension och en annan artikel från en produktdimension.

   Här är en illustration:

   ![](assets/static_rows.png)

Dessutom kan du nu ändra hur kolumnsummor beräknas när du är i statiskt radläge. Klicka bara på kugghjulsikonen och växla mellan dessa två alternativ:

![](assets/column-totals.png)

| Alternativ | Beskrivning |
|---|---|
| (Standard) Beräkna summor genom att summera de värden som finns i varje kolumn. | Med det här alternativet beräknas endast de rader som finns i tabellen. (Beräkning på klientsidan) |
| Beräkna summor baserat på alla rader för varje mätvärde. | Det här alternativet inkluderar alla dimensionsartiklar för den här dimensionen, även de som inte finns med i tabellen. (Beräkning på serversidan) |

