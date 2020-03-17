---
description: Steg som beskriver hur klassificeringsdata tas bort eller tas bort.
subtopic: Classifications
title: Ta bort klassificeringsdata
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ta bort klassificeringsdata

Ibland är det nödvändigt att ta bort klassificeringsdata efter att de har överförts. Använd antingen `~empty~` eller `~deletekey~`, beroende på vad du vill ta bort.

## Steg för att ta bort klassificeringsdata

När du tar bort klassificeringsdata måste du överföra en klassificeringsfil som innehåller `~empty~` eller `~deletekey~` finns i rätt celler.

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

När du använder `~empty~` lagerkategoriklassificeringen bevaras fortfarande data för klassificeringen av lagernamn. Värdet tar bara bort `~empty~` klassificeringsdata för den cellen.

## Ta bort en hel klassificeringsrad

Använd `~deletekey~` i valfri kolumn för att ta bort hela klassificeringsraden. Exempel:

| Lager-SKU (eVar8) | Lagernamn | Lagerkategori |
| --- | --- | --- |
| 857467 | V-halströja | Kläder för kvinnor |
| 948203 | Ankle bracelet | Juveler |
| 174391 | Vita anduella byxor | `~deletekey~` |

Om du använder `~deletekey~` under klassificeringen Lagerkategori tas alla klassificeringsdata för nyckelvärdet bort `174391`. Det blir som om raden aldrig klassificerats.

## Pitfalls- och tips

* Om du använder `~deletekey~`det behöver du bara en per rad i en klassificeringsfil.
* `~empty~` och `~deletekey~` måste vara *exakta* träffar. Inga blanksteg eller versaler tillåts.
* Du kan inte ta bort värden i nyckelkolumnen. Dessa värden skickas direkt till variabeln och är permanenta.
* Om du tar bort ett klassificeringsvärde som har underklassificeringar tas även dessa underklassificeringar bort. Klassifikationer kan inte finnas utan ett nyckelvärde, och en underklassificerings överordnade är dess nyckelvärde.
* Det går att ta bort data för underklassificering medan den överordnade klassificeringen förblir oförändrad.
