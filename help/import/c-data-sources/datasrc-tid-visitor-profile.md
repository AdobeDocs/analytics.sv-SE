---
description: Använd transaktions-ID i datakällor för att länka samman online- och offlinedata.
title: Transaktions-ID och besökarprofiler
topic-fix: Developer and implementation
feature: Data Sources
exl-id: ca5f9e8d-853f-4444-a8fd-a20933ef33d7
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---

# Transaktions-ID och besökarprofiler

Det här avsnittet innehåller viktig information om data från besökarprofilen som används när data överförs med ett transaktions-ID.

## Transaktions-ID {#section_B248FA93ECC84F6290D237EB83618070}

När ett transaktions-ID registreras sparas en ögonblicksbild av den aktuella besökarprofilen och kopplas till transaktions-ID:t. Den här&quot;ögonblicksbilden&quot; innehåller alla variabelvärden som för närvarande är inställda för besökaren, inklusive bestående variabler (som eVars och kampanjer). Värdena i den här ögonblicksbilden får attribuering för lyckade händelser, inköpshändelser och intäkter som senare överförts med samma transaktions-ID.

När besökarprofilen &quot;snapshot&quot; har skapats uppdateras den inte när den aktuella besökarprofilen ändras (på grund av onlinebeteende), utan uppdateras bara med data som överförs med transaktions-ID-datakällor. Om du ställer in samma transaktions-ID-värde på flera sidor under samma besök kommer den överföring av datakälla som sker senare att vara knuten till den ögonblicksbild som skapades första gången ID:t angavs.

**Flera överföringar**

Flera rader med data kan laddas upp till samma transaktions-ID under hela giltighetsfönstret för transaktions-ID (se nedan).

**Variabel förfallotid**

Variabel förfallotid beaktas inte för transaktions-ID eftersom data för den associerade besökarprofilen är avsedda att återspegla besökarens tillstånd vid tidpunkten för transaktionen. Om exempelvis eVar1 är konfigurerad att upphöra att gälla efter besök får värdet i besökarprofilen &quot;snapshot&quot; kredit även om värdet har upphört att gälla eller har ersatts i den aktuella besökarprofilen när data för transaktions-ID överförs.

**Produkter**

Produktinformation (från `s.products`) finns inte i besökarprofilen &quot;snapshot&quot;, så du måste överföra alla associerade produktdata i datakällfilen tillsammans med transaktions-ID:t. Observera att du bara kan ange en produkt per rad, så du kan behöva överföra flera rader med samma transaktions-ID för att inkludera alla produkter.

**Uppladdad eVar - beständighet**

eVaror som överförts med transaktions-ID-datakällor läggs till i besökarprofilen &quot;snapshot&quot;, de läggs inte till i den aktuella besökarprofilen eller den virtuella cookien. Det innebär att onlinebeteenden som inträffar efter överföringen inte krediteras eVars-variabler som överförts, eftersom dessa värden inte ingår i den aktuella besökarprofilen.

**Förfallofönster för transaktions-ID**

Besökarprofilen &quot;snapshot&quot; som är associerad med ett transaktions-ID kan tas bort efter 90 dagar, men det faktiska raderingsschemat varierar. Om det behövs kan du kontakta Adobe kundtjänst för att förlänga giltighetsperioden. Om en rad överförs efter förfallofönstret för transaktions-ID registreras data i raden, men inga data i besökarprofilen &quot;snapshot&quot; kommer att krediteras om profilen har tagits bort.

## Uppdelningar och segmentering med transaktions-ID:n {#section_A4D39291200A42C496122FDB9EF6EF68}

eVars som överförs med datakällor kan användas för att dela upp eVars som finns i besökarprofilens ögonblicksbild. Eftersom dessa data är åtskilda från den aktuella besökarprofilen kan du inte dela upp med andra eVars som kan ha angetts före eller efter att transaktions-ID:t angavs, men som inte ingår i ögonblicksbilden.

Det finns några sätt att visa associerade besöksdata som kanske inte är tillgängliga i en uppdelning. I data warehouse-rapporter kan du visa transaktions-ID-data med ett besökar-ID som matchar övriga träffar från besökaren. Även om dessa transaktions-ID-rader exkluderas vid inventering av besök/besökare per dag, används de vid beräkning av de flesta mätvärden och i segment.

Det innebär att du kan skapa ett segment med besökare som utför en offlinehändelse som har överförts med datakällor för transaktions-ID. Det returnerar allt besökaren gjorde före och efter händelse för transaktions-ID.

På samma sätt kan du med besökardeltagande se hur transaktions-ID:n och eVars föregått en online-händelse eller hur online-props och eVars föregått en transaktions-ID-händelse.
