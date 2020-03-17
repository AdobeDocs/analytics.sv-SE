---
title: hövding
description: Implementera hierarkivariabler i Adobe Analytics.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# hövding

Hierarkivariabler är anpassade variabler som du kan använda för att visa en webbplats struktur.

Den här variabeln är mest användbar för webbplatser som har fler än tre nivåer i platsstrukturen. En mediewebbplats kan till exempel ha fyra nivåer till avsnittet Sport: Sport, Local Sports, Baseball och Red Sox. Om någon besöker Baseball-sidan, Sport, Local Sports och Baseball återspeglar alla nivåer detta besök.

Det finns fem [!UICONTROL hierarchy] variabler som måste aktiveras av Adobes kundtjänst. När hierarkin är aktiverad bör du bestämma en avgränsare för variabeln och det maximala antalet nivåer för hierarkin. Om avgränsaren till exempel är ett komma kan sporthierarkin visas enligt följande.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Kontrollera att inga av avsnittsnamnen har avgränsaren. Om ett av avsnitten till exempel heter &quot;Koppla stödraster, Jim&quot; ska du välja en annan avgränsare än kommatecken. Varje hierarkiavsnitt är begränsat till 255 byte, medan den totala variabelgränsen är 255 byte. När en avgränsare har valts (när hierarkin skapades) är det inte så lätt att ändra den.

Kontakta Adobes kundtjänst om du vill ändra avgränsaren för en befintlig hierarki. Avgränsare kan också bestå av flera tecken, t.ex.|| eller /|\, vilket är mindre troligt att de visas i ett hierarkiavsnitt.

## Syntax och möjliga värden

Placera inte något blanksteg mellan varje avgränsare. I följande exempelsyntax är N ett tal mellan ett och fem.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Använd inte avgränsaren förutom för att avgränsa nivån i hierarkin. Avgränsaren kan vara valfritt tecken eller tecken.

## Exempel

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

## Pitfalls, frågor och tips

* Avgränsaren kan inte ändras efter att hierarkin har konfigurerats. Om avgränsaren för din hierarki måste ändras kontaktar du Adobes kundtjänst.
* Antalet nivåer kan inte ändras efter att hierarkin har konfigurerats.

> [!NOTE] Ändringar i hierarkier kan medföra en avgift.
