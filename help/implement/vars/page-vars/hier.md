---
title: hierarki
description: Implementera hierarkivariabler i Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# hierarki

Hierarkivariabler är anpassade variabler som du kan använda för att visa en webbplats struktur.

>[!TIP]
>
>Den här variabeln var vanligare i tidigare versioner av Adobe Analytics. Adobe rekommenderar att du använder [eVars](evar.md) och klassificeringar istället.

>[!IMPORTANT]
>
>Hierarki stöds inte vid datainsamling med XDM för Experience Edge.

Den här variabeln är användbar för platser som har mer än tre nivåer i platsstrukturen. En mediewebbplats kan till exempel ha fyra nivåer till avsnittet Sport: `Sports`, `Local Sports`, `Baseball`och `Team name`. Om någon besöker Baseball-sidan, Sport, Local Sports och Baseball återspeglar alla nivåer detta besök.

Adobe stöder upp till 5 hierarkivariabler i implementeringen. När hierarkin är aktiverad bestämmer du vilken avgränsare som ska användas för variabeln och det högsta antalet nivåer för hierarkin. Om avgränsaren till exempel är ett komma ser hierarkin ut ungefär så här:

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Kontrollera att inga av avsnittsnamnen har avgränsaren. Om till exempel ett av avsnitten anropas `Coach Griffin, Jim`väljer du en annan avgränsare än ett komma. Den totala variabelgränsen är 255 byte. Avgränsare kan bestå av flera tecken, t.ex. `||` eller `/|\`, vilket är mindre troligt att de visas i variabelvärden.

## Exempel

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
