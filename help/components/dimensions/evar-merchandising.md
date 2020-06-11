---
title: eVar (Merchandising)
description: Egna variabler som är kopplade till produktdimensionen.
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---


# eVar (Merchandising)

*Den här hjälpsidan beskriver hur e-handel fungerar som en dimension. Mer information om hur du implementerar eVars finns i[eVars](/help/implement/vars/page-vars/evar.md)i Implementeringshandboken.*

När ni mäter framgångarna med externa kampanjer eller externa söktermer vill ni vanligtvis ha ett enda värde för att ta emot poäng för alla framgångshändelser som inträffar. Om en kund t.ex. klickar på en länk i en e-postkampanj för att besöka webbplatsen, bör alla inköp som görs som ett resultat tillskrivas kampanjen.

Vad gäller för händelser som styrs av intern sökning eller kategoribläddring när en kund letar efter flera objekt? En kund söker till exempel efter platsen `"goggles"`och lägger sedan till ett par i kundvagnen:

![Exempel på växlar](assets/merch-example-goggles.png)

Innan du går till kassan söker kunden efter `"winter coat"`och lägger sedan till en kavaj i kundvagnen:

![Exempel på Coat](assets/merch-example-coat.png)

När besökaren har slutfört köpet får du en intern sökning efter `"winter coat"` som krediteras med köpet av ett par glasögon (förutsatt att eVar använder standardallokeringen för&quot;Senaste&quot;). Bra för `"winter coat"`men dåligt för marknadsföringsbeslut:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | $157 |

## Hur variabler för marknadsföring löser det här problemet

Med eVars kan du tilldela en produkt det aktuella värdet för en eVar när en lyckad händelse inträffar. Det här värdet är kopplat till den produkten, även om ett eller flera nya värden senare anges för den aktuella eVar.

Om du har aktiverat varuexponering för eVar i det föregående exemplet `"goggles"` är söktermen knuten till snön och söktermen `"winter coat"` är knuten till jackan. Merchandising eVars tilldelar intäkter på produktnivå, så varje term får en uppskattning av intäktsbeloppet för den produkt som termen var kopplad till:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | $119 |
| glasögon | $38 |

Se [Merchandising eVars](/help/implement/vars/page-vars/evar-merchandising.md) för implementeringsinstruktioner.

## Instanser av försäljningsvariabler

Instansmåttet [rekommenderas inte för](../metrics/instances.md) försäljningsvariabler.

* För variabler som används i produktsyntax ökas inte antalet instanser alls.
* För marknadsföringsvariabler som använder konverteringsvariabelsyntax räknas instanser varje gång eVar anges. Den kopplar dock till dimensionsvärdet `"None"` såvida inte allt av följande inträffar i samma träff:
   * eVar för varuexponering anges med ett värde.
   * Variabeln `products` definieras med ett värde.
   * En bindningshändelse har angetts.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Eftersom de flesta användningsfall för konvertering av variabelsyntax kräver variabeln eVar och products i olika träffar är det inte realistiskt att använda måttet &quot;Instances&quot;.
