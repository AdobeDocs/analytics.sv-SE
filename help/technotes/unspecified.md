---
description: Olika rapporter i Adobe Analytics kan visa Ospecificerad, Ingen, Annan eller Okänd, beroende på vilken rapport som visas. I allmänhet innebär det här radobjektet att variabeln inte var definierad eller på annat sätt otillgänglig.
title: Ospecificerad, Ingen, Annan och Okänd vid rapportering
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
source-git-commit: 0f5890679ea73c1bbea9f5d2939e89c6775c85da
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# &quot;Ospecificerad&quot;, &quot;Ingen&quot;, &quot;Annan&quot; och &quot;Okänd&quot; vid rapportering

Olika rapporter i Adobe Analytics kan visa &quot;Ospecificerad&quot;, &quot;Annan&quot; eller &quot;Okänd&quot;, beroende på vilken rapport som visas. I allmänhet innebär det här radobjektet att variabeln inte var definierad eller på annat sätt otillgänglig. Nedan finns en omfattande lista över hur varje rapport kan innehålla en av dessa radposter.

## &quot;Ospecificerad&quot; (eller &quot;Ingen&quot;) vid rapportering {#reporting}

&quot;Ospecificerad&quot; är ett vanligt radobjekt i rapporter. Den kallas även&quot;ingen&quot;.

* **En händelse utlöses utan en konverteringsvariabel:** En användare kommer till din webbplats och gör ett köp utan något eVar1-värde. Om du visar order med dimensionen eVar1 finns det inget värde att tilldela ordern till. Därför tilldelas den automatiskt till&quot;Ospecificerad&quot;.
* **Oklassificerade data i klassificeringsrapporter:** När klassificeringsdata visas returnerar alla värden som inte har associerade data för den aktuella klassificeringen &quot;Ospecificerade&quot;. Kontrollera att det finns ett klassificeringsvärde som är associerat med varje överordnad dimensionspost för att lösa problemet.
* **Uppdelningsrapporter där bara en variabel utlöstes:** När du tillämpar en uppdelning på en variabel måste alla instanser av variabeln beaktas. Om den andra variabeln inte kunde ses eller om den bestod från en tidigare träff är dimensionsobjektet &quot;Ospecificerat&quot;.
* **Träffar som inte är mobila i mobilrapporter:** Alla träffar som inte är mobila i mobilrapporter listas som Ospecificerade (&quot;Inte mobil&quot; i Reports and Analytics).

## ’Övrigt’ i rapporteringen {#other}

Även om det är något sällsynt i rapporteringen kan &quot;Annat&quot; förekomma under flera omständigheter:

* **Sidor utlöses utanför interna URL-filter:** Det här värdet finns på plats för att skydda dig mot databedrägeri, som om en annan organisation stjäl din källkod och implementerar den på sin egen webbplats. Kontrollera att alla URL:er som koden är implementerad på matchar de interna URL-filtren i rapportsvitens inställningar för att åtgärda problemet.
* **Besökare som använder en webbläsare som inte används så ofta:** I rapporten Webbläsartyper visas &quot;Annan&quot; som ett fel om besökarna använder en webbläsare som inte är en populär webbläsartyp. Det finns många organisationer som producerar webbläsare. Alla webbläsare som inte har skapats av större organisationer är inkapslade i &quot;Annat&quot; för att förhindra att rapporten blir rörig.

## &quot;Okänd&quot; i rapportering {#unknown}

&quot;Okänd&quot; kan inträffa under flera omständigheter:

* **Icke-webbläsare träffar vid visning av teknikrapporter:** Om ett AppMeasurement-bibliotek inte kan avgöra om en funktion stöds visas Okänd i rapporteringen.
* **Använda segment där komponenter inte är tillgängliga:** Kontrollera att variabler som används i ett segment är aktiverade och att användarna har tillgång till dem. Om en användare inte har åtkomst till en segmentkomponent, eller om en variabel är inaktiverad, visas Okänd.

## Filtrera dessa värden vid rapportering {#filter}

I de flesta fall är det säkert att ignorera dessa radobjekt. Du kan använda sökfiltret för att ta bort dem om du vill.

Vissa backend-datavariabler använder värdet `::unspecified::` i rapporteringen, men det visas inte i gränssnittet. Om ett sökfilter inte kan exkludera data kan du prova att använda det här värdet (inklusive kolonerna).
