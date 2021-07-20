---
title: eVar (Merchandising)
description: Egna variabler som är kopplade till produktdimensionen.
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: 2e3f078500b80eefa2ca7c4a67de5bd0e91e764f
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---

# eVar (Merchandising)

*Den här hjälpsidan beskriver hur e-handel fungerar som en dimension. Mer information om hur du implementerar eVars för varuexponering finns i [eVars](/help/implement/vars/page-vars/evar.md) i användarhandboken för implementering.*

En detaljerad diskussion om hur eVars marknadsförs finns i [Merchandising eVars and product finding methods](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=en).

När ni mäter framgångarna med externa kampanjer eller externa söktermer vill ni vanligtvis ha ett enda värde för att ta emot poäng för alla framgångshändelser som inträffar. Om en kund t.ex. klickar på en länk i en e-postkampanj för att besöka webbplatsen, bör alla inköp som görs som ett resultat tillskrivas kampanjen.

Vad gäller för händelser som styrs av intern sökning eller kategoribläddring när en kund letar efter flera objekt? En kund söker till exempel efter `"goggles"` på din webbplats och lägger sedan till ett par i kundvagnen:

![Exempel på växlar](assets/merch-example-goggles.png)

Före utcheckningen söker kunden efter `"winter coat"` och lägger sedan till en kavaj i kundvagnen:

![Exempel på Coat](assets/merch-example-coat.png)

När besökaren har slutfört köpet får du en intern sökning efter `"winter coat"` som har krediterats med köpet av ett par glasögon (förutsatt att eVar använder standardallokeringen för &#39;Senaste&#39;). Bra för `"winter coat"`, men dåligt för marknadsföringsbeslut:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | 157 dollar |

## Hur variabler för marknadsföring löser det här problemet

Med eVars kan du tilldela en eVar det aktuella värdet när en lyckad händelse inträffar. Det här värdet är kopplat till den produkten även om ett eller flera nya värden senare anges för den aktuella eVar.

Om du har aktiverat varuexponering för eVar i det föregående exemplet är söktermen `"goggles"` knuten till snöglasen och söktermen `"winter coat"` är kopplad till jackan. Merchandising eVars tilldelar intäkter på produktnivå, så varje term får en uppskattning av intäktsbeloppet för den produkt som termen var kopplad till:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | 119 dollar |
| glasögon | 38 dollar |

Se [Merchandising eVars](/help/implement/vars/page-vars/evar-merchandising.md) för implementeringsinstruktioner.

## Instanser av marknadsföringsvariabler

Måttet [Instanserna](../metrics/instances.md) rekommenderas inte för användning i försäljningsvariabler.

* För variabler som används i produktsyntax ökas inte antalet instanser alls.
* För marknadsföringsvariabler som använder konverteringsvariabelsyntax räknas instanser varje gång eVar anges. Det attribut till dimensionsobjektet `"None"` såvida inte allt av följande inträffar i samma träff:
   * Försäljningsvärdet anges med ett eVar.
   * Variabeln `products` definieras med ett värde.
   * En bindningshändelse har angetts.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Eftersom de flesta användningsfall för konvertering av variabelsyntax kräver variabeln eVar och products i olika träffar är det inte realistiskt att använda mätvärdet för &#39;Instances&#39;.
