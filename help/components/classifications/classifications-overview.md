---
title: Klassificeringsöversikt
description: Anpassa grupperingen av dimensionsobjekt.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 3701aa7a2a1528cd735c70fc7b061755a15b34a6
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Klassificeringsöversikt

En klassificering är ett sätt att kategorisera Analytics-variabeldata och sedan visa data på olika sätt när du genererar rapporter. Du upprättar en relation mellan ett variabelvärde och metadata som är relaterade till det värdet. Klassificeringar kan användas på de flesta anpassade dimensioner, till exempel [Spårningskod](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) och [eVars](/help/components/dimensions/evar.md).

**Klassificeringsuppsättningar** är det primära sättet att klassificera data. **Klassificeringsreglerna** och **Klassificeringsimporteraren** är äldre metoder för att klassificera data. Dessa metoder är föråldrade och kommer inte att vara tillgängliga efter den 31 augusti 2026.

* **Klassificeringsuppsättningar**: Skapa och hantera klassificeringar i ett enda, förenklat gränssnitt.
* **Klassificeringsregler** (äldre): Skapa regler som tilldelar ett givet dimensionsobjekt till ett klassificeringsdimensionsobjekt. Den här metoden för att klassificera data är bäst när en dimension ofta stöter på nya unika värden eller där manuella klassificeringar är vanliga och betungande.
* **Klassificeringsimportör** (äldre): Exportera ett mallkalkylblad med dimensionsobjekt på varje rad. Kolumner representerar varje klassificering för en dimension. Den här metoden för att klassificera data är bäst när alla dimensionsobjekt är kända och kräver ingen frekvent uppdatering.

En enda dimension kan ha flera klassificeringsdimensioner. Du kan till exempel klassificera [!UICONTROL Product IDs] med ytterligare produktattribut, som produktnamn, färg, storlek, beskrivning och SKU. Var och en av dessa attribut skulle vara en separat klassificeringsdimension som tillhör samma överordnade dimension. Genom att förbättra dina rapporter med dessa attribut får du djupare och mer komplexa rapporteringsmöjligheter. När en dimension innehåller klassificeringsdata är klassificeringsdimensionen tillgänglig i rapporter som endast innehåller klassificeringsdimensionsobjekt. Alla överordnade dimensionsobjekt som inte innehåller något klassificeringsvärde grupperas under [Ospecificerade](/help/technotes/unspecified.md)
