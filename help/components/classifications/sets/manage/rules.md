---
title: Klassificeringsuppsättningsregler
description: Visa och redigera regler för en enskild klassificeringsuppsättning.
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Klassificeringsuppsättningsregler

Klassificeringsuppsättningsregler gör att du automatiskt kan klassificera värden baserat på värdet som variabeln är inställd på. Dessa regler gäller för alla inkommande variabelvärden för alla prenumerationer av klassificeringsuppsättningen.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Klicka på önskat namn > **[!UICONTROL Rules]**

## Regelinställningar

Inställningar som gäller för hela uppsättningen regler.

* **[!UICONTROL Rules overwrite]**: Bestämmer beteendet för alla regler i fall där det finns ett klassificeringsvärde.
   * **[!UICONTROL Apply to all values]**: Om en regel matchar skriver du alltid över klassificeringsvärdet.
   * **[!UICONTROL Apply only to unset values]**: Om en regel matchar skriver du bara klassificeringsvärdet om det är tomt. Om det finns ett klassificeringsvärde gör du ingenting.
* **[!UICONTROL Lookback window]**: När den här regeln är aktiverad körs alla regler mot alla unika värden som visas i det uppslagsfönster som anges här.

## Regler

En lista med regler som körs för varje unikt värde.

* **[!UICONTROL Search]**: En sökruta där du kan filtrera regler efter matchningskriterier.
* **[!UICONTROL Add rule]**: Lägger till en tom rad i regeltabellen.
* **[!UICONTROL Test rule set]**: Öppnar ett testgränssnitt där du kan validera dina regler. Till vänster kan du skriva nyckelvärden manuellt eller dra och släppa en klassificeringsfil för att importera många värden att testa mot. Till höger finns en tabell som visar preliminära resultat av vilka klassificerade värden som skulle se ut om regeluppsättningen aktiverades. Eftersom det här gränssnittet bara är till för validering klassificeras inga värden.

Markera en eller flera regler genom att klicka i kryssrutan bredvid önskad regel. Om du väljer en regel visas följande alternativ:

* **[!UICONTROL Delete]**: Tar bort raden från regeltabellen.
* **[!UICONTROL Duplicate]**: Kopierar de markerade raderna till nya rader i regeltabellen.

## Regelregister

Regeltabellen är lodrätt uppdelad i två huvuddelar: matchningsvillkor och klassificeringsåtgärd. Varje rad (en enskild regel) innehåller ett matchande villkor och en klassificeringsåtgärd.

* **Regelnummer**: Regler körs i samma ordning som du konfigurerar regeltabellen. If [!UICONTROL Rules overwrite] är inställd på [!UICONTROL Apply to all values], skriver den senaste matchande regeln över alla tidigare regler för samma klassificeringsdimension. If [!UICONTROL Rules overwrite] är inställd på [!UICONTROL Apply to only unset values], gäller den första regeln som anger ett klassificeringsvärde.
* **[!UICONTROL Select rule type]**: Regelvillkoret. Alternativen inkluderar [!UICONTROL Contains], [!UICONTROL Ends with], [!UICONTROL Regular expression], [!UICONTROL Regular expression]och [!UICONTROL Starts with].
* **[!UICONTROL Enter match criteria]**: Textsträngen som ska matchas. Om du väljer [!UICONTROL Regular expression] Som regeltyp visas en övertäckning där du kan ange värdet, testa det reguljära uttrycket och ange exempelsyntax.
* **[!UICONTROL Set classification]**: En nedrullningsbar lista som anger den klassificeringsdimension som du vill tilldela ett värde till. Giltiga alternativ innehåller element i [schema](schema.md).
* **[!UICONTROL To]**: Textsträngen som det klassificerade värdet ska anges till. Om regeltypen är [!UICONTROL Regular expression]kan du inkludera en kombination av text och matchningsgrupper.
