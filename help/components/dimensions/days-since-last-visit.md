---
title: Dagar sedan senaste besök
description: Antalet dagar mellan den aktuella träffen och den senaste gången de besökte.
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 0%

---

# Dagar sedan senaste besök

Dagar sedan senaste besök [dimension](overview.md) mäter hur lång tid som förflutit mellan besökarens aktuella träff och deras tidigare besök (om det finns något). Den här dimensionen hjälper dig att förstå det beteende besökare gör efter att ha besökt din webbplats. Exempel:

* Hur ofta återbesöker användarna webbplatsen?
* Hur korrelerar returfrekvensen med konvertering? Besök återkommande köpare ofta eller sällan?
* Återkommer användare som klickar på kampanjer ofta?

Nybörjarbesökare ingår inte i den här dimensionen.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Dimensionen omfattar antalet dagar mellan besökarens senaste besök och den aktuella träffen. Varje antal dagar är ett separat dimensionsobjekt där `"Same day"` förekommer där en besökares senaste besök och den aktuella träffen inträffade samma dag.
