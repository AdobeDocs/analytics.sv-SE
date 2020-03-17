---
description: Olika rapporter i Adobe Analytics kan visa Ospecificerad, Annan eller Okänd, beroende på vilken rapport som visas. I allmänhet innebär det här radobjektet att variabeln inte var definierad eller på annat sätt otillgänglig.
title: Ospecificerad, annan och okänd vid rapportering
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# &quot;Ospecificerad&quot;, &quot;Annan&quot; och &quot;Okänd&quot; vid rapportering

Olika rapporter i Adobe Analytics kan visa Ospecificerad, Annan eller Okänd, beroende på vilken rapport som visas. I allmänhet innebär det här radobjektet att variabeln inte var definierad eller på annat sätt otillgänglig. Nedan finns en omfattande lista över hur varje rapport kan innehålla en av dessa radposter.

## &quot;Ospecificerad&quot; i rapportering

&quot;Ospecificerad&quot; är ett vanligt radobjekt i rapporter.

* **En händelse utlöses utan en konverteringsvariabel:** En användare kommer till exempel till din webbplats och gör ett köp utan något eVar1-värde. Om du visar order med dimensionen eVar1 finns det inget värde att tilldela den här ordningen till. Därför tilldelas den automatiskt till&quot;Ospecificerad&quot;.
* **Oklassificerade data i klassificeringsrapporter:** När klassificeringsdata visas returneras &quot;Ospecificerad&quot; om ett värde inte har data associerade med den aktuella klassificeringen. Du löser det här problemet genom att klassificera det överordnade variabelvärdet.
* **Uppdelningsrapporter där endast en variabel utlöses:** När du tillämpar en uppdelning på en variabel måste alla instanser av variabeln tas med i beräkningen. Om den andra variabeln inte kunde ses, eller om den kvarstod från en tidigare träff, är dimensionsvärdet &quot;Ospecificerat&quot;.
* **Icke-mobila träffar i mobilrapporter:** Alla träffar som inte är mobila i mobilrapporter listas som Ospecificerade (&quot;Inte mobilt&quot; i Rapporter och analyser).

## ’Övrigt’ i rapporteringen

Även om det är något sällsynt i rapporteringen kan &quot;Annat&quot; förekomma under flera omständigheter:

* **Sidor utlöses utanför interna URL-filter:** Detta värde finns på plats för att skydda dig mot databedrägeri, som om en annan organisation stjäl din källkod och implementerar den på sin egen webbplats. Kontrollera att alla URL:er som koden är implementerad på matchar de interna URL-filtren i rapportsvitens inställningar för att åtgärda problemet.
* **Besökare som använder en webbläsare som inte används så ofta:** I rapporten Webbläsartyper visas&quot;Annat&quot; som en uppdelning om besökarna använder en webbläsare som inte är en populär webbläsartyp. Det finns många organisationer som producerar webbläsare. Alla webbläsare som inte har skapats av större organisationer är inkapslade i &quot;Annat&quot; för att förhindra att rapporten blir rörig.

## &quot;Okänd&quot; i rapportering

&quot;Okänd&quot; kan inträffa under flera omständigheter:

* **Träffar som inte är webbläsare vid visning av tekniska rapporter:** Om ett AppMeasurement-bibliotek inte kan avgöra om en funktion stöds visas Okänd i rapporteringen.
* **Använda segment där komponenter inte är tillgängliga:** Kontrollera att variabler som används i ett segment är aktiverade och att användarna har tillgång till dem. Om en användare inte har åtkomst till en segmentkomponent, eller om en variabel är inaktiverad, visas Okänd.

## Filtrera dessa värden vid rapportering {#section_5536E2B419D445D39C932E8F12C0070C}

I de flesta fall är det säkert att ignorera dessa radobjekt. Du kan använda sökfiltret för att ta bort dem om du vill.

Vissa backend-datavariabler använder värdet `::unspecified::` vid rapportering, men det visas inte i gränssnittet. Om ett sökfilter inte kan exkludera data kan du prova att använda det här värdet (inklusive kolonerna).
