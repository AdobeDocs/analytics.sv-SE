---
description: 'null'
keywords: Analytics Implementation
title: Översikt över försäljningsvariabler
topic: Developer and implementation
uuid: 2ccf516a-a7ee-48ab-92aa-414228a4102f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Översikt över försäljningsvariabler

När ni mäter framgångarna med externa kampanjer eller externa söktermer vill ni vanligtvis ha ett enda värde för att ta emot poäng för alla framgångshändelser som inträffar. Om en kund t.ex. klickar på en länk i en e-postkampanj för att besöka webbplatsen, bör alla inköp som görs som ett resultat tillskrivas kampanjen.

Men hur är det med händelser som styrs av intern sökning eller kategorisökning när en kund letar efter flera objekt? En kund söker till exempel efter&quot;glasögon&quot; på webbplatsen och lägger sedan till ett par i kundvagnen:

![](assets/merch-example-goggles.png)

Före utcheckningen söker kunden efter&quot;vinterjacka&quot; och lägger sedan till en jacka i korgen:

![](assets/merch-example-coat.png)

När köpet är slutfört, förutsatt att allokeringen inte ändrats från Senaste, får du en intern sökning efter&quot;vinterrock&quot; som krediteras med köpet av ett par glasögon. Bra för &quot;vinterrock&quot;, men dåligt för marknadsföringsbeslut:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | $157 |

**Hur variabler för marknadsföring löser det här problemet**

Med hjälp av variabler för kategoriövergripande marknadsföring, eller&quot;marknadsföringsvariabler&quot;, kan du tilldela en produkt det aktuella värdet för en eVar när en lyckad händelse inträffar. Det här värdet är kopplat till den produkten, även om ett eller flera nya värden senare anges för den aktuella eVar.

Om eVar är aktiverat för försäljning i det föregående exemplet är söktermen&quot;glasögon&quot; knuten till Fernie Snow Goggles och söktermen&quot;vinterrock&quot; är knuten till elementet El Gordon Down. I marknadsföringsvariabler fördelas intäkter på produktnivå, vilket innebär att varje term får en uppskattning av intäktsbeloppet för den produkt som termen var kopplad till:

| Intern sökterm | Intäkter |
|---|---|
| vinterrock | $119 |
| glasögon | $38 |

