---
title: Webbläsarexport
description: Med webbläsarexport kan du exportera dina klassificeringsdata till en tabbavgränsad fil.
source-git-commit: 8a5c7309b5d4061b2e3241219d9bdb1521294535
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---


# Webbläsarexport

Med webbläsarexport kan du exportera dina klassificeringsdata till en tabbavgränsad fil.

Admin > Klassificeringsimportör

Datauppsättningsfilen är en tabbavgränsad datafil (.tab filename) som stöds av de flesta kalkylbladsprogram.

>[!NOTE]
>Webbläsarexporter har en begränsning på 30 kolumner.

## Fältbeskrivningar

| Element | Beskrivningar |
| --- | --- |
| Välj Report Suite | Välj den rapportsvit som du vill exportera rapportdata från. |
| Datauppsättning som ska klassificeras | Välj den datauppsättning som du vill klassificera i listrutan. |
| Välj antal rader | Ange hur många rader med data som ska exporteras.<ul><li>Välj **[!UICONTROL All]** om du vill hämta alla rapportdata (upp till 50 000 rader).</li><li>Välj **[!UICONTROL Limit Data Rows To]** om du vill ange ett visst antal rader att hämta.</li></ul>Om du vill hämta mer än 50 000 datarader använder du alternativet FTP-nedladdning. |
| Filtrera efter mottagningsdatum | (Valfritt) Filtrera data efter det datum då de togs emot. Ange datumintervallet som du vill hämta data för. |
| Använd datafilter | (Valfritt) Filtrera datauppsättningen efter datavillkor. Du kan filtrera nedladdningen så att den innehåller datarader som innehåller ett visst värde eller datarader med otilldelade kolumnvärden (klassificerings-). Tänk på följande när du tillämpar datafilter:<ul><li>Du kan använda jokertecken när du definierar datafiltret. Använd en asterisk för att matcha noll eller flera tecken och ett frågetecken `?` för att matcha exakt ett tecken. Använd `?*` för att matcha ett eller flera tecken.</li><li>När du använder båda typerna av datafilter på en hämtning hämtas vanligtvis bara rader som matchar båda reglerna. Följande undantag gäller dock:<ul><li>Om rader med tom kolumn = Alla kolumner kontrolleras alla kolumner utom den kolumn som anges i den första regeln för tomhet. Detta undantag säkerställer att systemet hämtar alla rader med en kolumn som matchar den första regeln som också har alla andra kolumner tomma.</li><li>När du hämtar datarader som baseras på tomma kolumner kontrolleras alla kolumner utom de som anges i den första regeln för tomhet.</li><li>Om samma kolumn anges för båda filterreglerna (det är nästan omöjligt att uppfylla båda villkoren) hämtas bara rader som matchar den första regeln.</li></ul></ul> |
| Datafilter | (Valfritt) Filtrera data efter kampanjdata. Du kan bara hämta data från aktiva kampanjer, eller så kan du välja kampanjer som påbörjats (eller avslutats) inom ett visst datumintervall.<br>**Viktigt**: Det här alternativet är inte tillgängligt för rapportsviter som har aktiverats för den nya klassificeringsarkitekturen. |

