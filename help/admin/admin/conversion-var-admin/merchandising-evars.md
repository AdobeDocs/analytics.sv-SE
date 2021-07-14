---
title: Merchandising eVars and Product Finding Methods
description: En djupdykning i begreppen bakom försäljning av eVars och hur de bearbetar och allokerar data.
source-git-commit: 746c2cfd3236df7ec7498749015ddf75c1e558f5
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Merchandising eVars and Product Finding Methods

I det här dokumentet förklaras begreppen bakom försäljning av eVars, som bearbetar och tilldelar data på ett annat sätt än vanliga eVars-variabler. Det förklarar också hur eVars marknadsförs relaterar till metoder för produktsökning.

Även om de flesta webbplatser för detaljhandeln har många sätt att hitta produkter anser Adobe att följande är de grundläggande metoder för produktupptäckt som alla kunder inom detaljhandeln bör följa i Adobe Analytics:

* Interna söknyckelord
* Interna koder för kampanjspårning
* Marknadsföring/bläddringskategorier
* Merförsäljning

I det här dokumentet kan vi mappa några eVars till lösningarna enligt följande:

* eVar2: Interna söknyckelord
* eVar3: Interna koder för kampanjspårning
* eVar4: Marknadsföring/bläddringskategorier
* eVar5: Korsförsäljning

Vi kan använda en extra eVar för att mäta prestandan för alla produktsökningsmetoder i förhållande till varandra. Förutom de sökmetoder som beskrivs ovan kommer eVar att inkludera andra sökmetoder, t.ex. länkar till produktinformationssidor från externa webbplatser, i sin jämförelse.

* eVar1: Metoder för produktsökning

Du bör inte konfigurera någon av dessa variabler som standard-eVars, utan i stället konfigurera dem så att de marknadsför eVars.  Med hjälp av eVars kan du tilldela alla framgångsrika aktiviteter till värden som hämtas av eVars på *per-product*-nivå i stället för på *per-visit/per-order*-nivå. Jag kommer att klargöra skillnaden mellan fördelningen per produkt och per order under resten av detta dokument.

