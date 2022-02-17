---
description: Steg som beskriver hur klassificeringsdata tas bort eller tas bort.
title: Ta bort klassificeringsdata
feature: Classifications
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 5%

---

# Ta bort klassificeringsdata

Ibland är det nödvändigt att ta bort klassificeringsdata efter att de har överförts. Använd antingen `~empty~` eller `~deletekey~`, beroende på vad du vill ta bort.

## Steg för att ta bort klassificeringsdata

När du tar bort klassificeringsdata måste du överföra en klassificeringsfil som innehåller `~empty~` eller `~deletekey~` i cellerna.

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka på **[!UICONTROL Browser Export]**.
1. Välj den rapportserie och datauppsättning som du vill ta bort klassificeringsdata från.
1. Justera eventuella valfria inställningar för att filtrera specifika data som du letar efter och klicka sedan på **[!UICONTROL Export File]**.
1. När filen har laddats ned öppnar du filen och ersätter eventuella klassificeringsvärden med antingen `~empty~` eller `~deletekey~`.
1. Spara filen som en tabbavgränsad textfil.
1. Klicka **[!UICONTROL Import File]** och överför den sparade klassificeringsfilen tillbaka till Adobe Analytics.

## Ta bort ett enskilt klassificeringsvärde

Flera klassificeringar kan tillhöra samma variabel. Du kan till exempel ha två olika klassificeringar av eVar1. Om du bara vill ta bort ett enda klassificerat värde ersätter du klassificeringsvärdet med `~empty~`. Exempel:

| Lager-SKU (eVar8) | Lagernamn | Lagerkategori |
| --- | --- | --- |
| 857467 | V-halströja | Kläder för kvinnor |
| 948203 | Ankle bracelet | Juveler |
| 174391 | Vita anduella byxor | `~empty~` |

Använda `~empty~` enligt klassificeringen Lagerkategori bevarar fortfarande data för klassificeringen av lagernamn. The `~empty~` värdet tar bara bort klassificeringsdata för den cellen.

## Ta bort en hel klassificeringsrad

Använd `~deletekey~` i en kolumn om du vill ta bort hela klassificeringsraden. Exempel:

| Lager-SKU (eVar8) | Lagernamn | Lagerkategori |
| --- | --- | --- |
| 857467 | V-halströja | Kläder för kvinnor |
| 948203 | Ankle bracelet | Juveler |
| 174391 | Vita anduella byxor | `~deletekey~` |

Använda `~deletekey~` under klassificeringen Lagerkategori tas alla klassificeringsdata för nyckelvärdet bort `174391`. Det blir som om raden aldrig klassificerats.

## Pitfalls- och tips

* Om du använder `~deletekey~`behöver du bara en per rad i en klassificeringsfil.
* `~empty~` och `~deletekey~` måste vara *exakt* matchar. Inga blanksteg eller versaler tillåts.
* Du kan inte ta bort värden i nyckelkolumnen. Dessa värden skickas direkt till variabeln och är permanenta.
* Om du tar bort ett klassificeringsvärde som har underklassificeringar tas även dessa underklassificeringar bort. Klassifikationer kan inte finnas utan ett nyckelvärde, och en underklassificerings överordnade är dess nyckelvärde.
* Det går att ta bort data för underklassificering medan den överordnade klassificeringen förblir oförändrad.
