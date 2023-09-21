---
title: eVar (marknadsdimension)
description: Egna variabler som är kopplade till produktdimensionen.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 2%

---

# eVar (varuexponering)

*Den här hjälpsidan beskriver hur e-handel fungerar som en [dimension](overview.md). Mer information om hur du implementerar eVars för marknadsföring finns i [eVar (variabel för försäljning)](/help/implement/vars/page-vars/evar-merchandising.md) i användarhandboken för implementering.*

Mer information om hur du marknadsför eVars finns i [Merchandising eVars and product finding methods](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html).

När ni mäter framgångarna med externa kampanjer eller externa söktermer vill ni vanligtvis ha ett enda värde för att ta emot poäng för alla framgångshändelser som inträffar. Om en kund t.ex. klickar på en länk i en e-postkampanj för att besöka webbplatsen, bör alla inköp som görs som ett resultat tillskrivas kampanjen.

Vad gäller för händelser som styrs av intern sökning eller kategoribläddring när en kund letar efter flera objekt? En kund söker till exempel efter `"goggles"`lägger sedan till ett par i kundvagnen:

![Exempel på växlar](assets/merch-example-goggles.png)

Före utcheckningen söker kunden efter `"winter coat"`lägger sedan till en jacka i kundvagnen:

![Exempel på Coat](assets/merch-example-coat.png)

När besökaren är klar med köpet har du en intern sökning efter `"winter coat"` krediteras med köp av ett par glasögon (förutsatt att eVarna använder standardallokeringen för&quot;Senaste&quot;). Bra för `"winter coat"`men dåligt för marknadsföringsbeslut:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | $157 |

## Hur variabler för marknadsföring löser det här problemet

Med eVars kan du tilldela en eVar det aktuella värdet när en lyckad händelse inträffar. Detta värde är kopplat till den produkten även om ett eller flera nya värden senare anges för den aktuella eVarna.

Om marknadsföring är aktiverat för eVarna i det föregående exemplet, söktermen `"goggles"` är knutet till snön och söktermen `"winter coat"` är knuten till koftan. Merchandising eVars tilldelar intäkter på produktnivå, så varje term får en uppskattning av intäktsbeloppet för den produkt som termen var kopplad till:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | $119 |
| glasögon | $38 |

Se [Merchandising eVars](/help/implement/vars/page-vars/evar-merchandising.md) för implementeringsinstruktioner.

## Instanser av marknadsföringsvariabler

The [Instanser](../metrics/instances.md) metriska värden rekommenderas inte för användning på försäljningsvariabler.

* För variabler som används i produktsyntax ökas inte antalet instanser alls.
* För marknadsföringsvariabler som använder syntax för konverteringsvariabler räknas instanser varje gång eVarna ställs in. Det är emellertid attribut till dimensionsobjektet `"None"` om inte allt av följande inträffar i samma träff:
   * EVarna för varuexponering anges med ett värde.
   * The `products` variabeln definieras med ett värde.
   * En bindningshändelse har angetts.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Eftersom de flesta användningsfall för konvertering av variabelsyntax kräver variabeln eVar och products i olika träffar är det inte realistiskt att använda mätvärdet för &#39;Instances&#39;.
