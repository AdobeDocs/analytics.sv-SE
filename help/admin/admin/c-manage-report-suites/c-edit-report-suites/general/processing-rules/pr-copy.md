---
title: Kopiera bearbetningsregler
description: Lär dig hur du kopierar bearbetningsregler från en rapportserie till en annan.
feature: Processing Rules
role: Admin
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---

# Kopiera bearbetningsregler mellan rapportsviter

Genom att kopiera bearbetningsregler slipper du manuellt återskapa samma logik i flera rapportsviter. Du kan använda kopieringsfunktionen för att enkelt dela bearbetningsregelfunktioner mellan många rapportsviter, eller för att kopiera testade funktioner från en utvecklingsrapportsvit till en produktionsrapportserie.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]** > **[!UICONTROL Copy processing rules]**

Gränssnittet tillåter två alternativ:

* **Ersätt alla bearbetningsregler**: Det här alternativet tar bort alla bearbetningsregler från målrapportsviten och lägger sedan till alla bearbetningsregler i målrapportsviten i samma ordning. Du kan inte välja ett begränsat antal bearbetningsregler som ska ersättas.
* **Lägg till specifika bearbetningsregler**: Med det här alternativet kan du välja en eller flera bearbetningsregler. Tillagda regler läggs till i slutet av bearbetningsregellistan i varje målrapportsserie. Överväg att bearbeta regelordning och regler som redan finns när regler läggs till i varje målrapportsserie.

När du väljer bearbetningsregler att lägga till eller rapportera programsviter att kopiera till kan du använda `Ctrl`/`Cmd` + `Click` för att välja flera bearbetningsregler eller rapportsviter. När du har valt vilka rapportsviter du vill kopiera till väljer du **[!UICONTROL Copy]** och bekräftar det modala fönstret som visas.

>[!WARNING]
>
>Bearbetning av regler påverkar direkt datainsamlingen och kan orsaka dataförlust om de används felaktigt. Testa alltid bearbetningsregler i en utvecklingsrapportsserie innan du kopierar dem till en produktionsrapportsserie för att minska problem med datakvaliteten.
