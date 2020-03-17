---
description: Numeriska 2-klassificeringar ger anpassade, flexibla mätvärden som du kan importera till Adobe Experience Cloud via importören.
subtopic: Classifications
title: Översikt över Numeric 2-klassificeringar
topic: Admin tools
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Översikt över Numeric 2-klassificeringar

Numeriska 2-klassificeringar ger anpassade, flexibla mätvärden som du kan importera till Adobe Experience Cloud via importören.

>[!IMPORTANT]
>
>Möjligheten att importera Numeric 2- och Date-Enabled-klassificeringar har tagits bort från kodbasen. Denna ändring träder i kraft i underhållsutgåvan från juli 2019. Om du har numeriska eller datumaktiverade kolumner i importfilen, ignoreras dessa celler och alla andra data i filen importeras som vanligt. Befintliga klassificeringar kan fortfarande exporteras via standardarbetsflödet för klassificering och kommer att vara tillgängliga i rapporter.

> [!NOTE] I Analytics Maintenance-utgåvan 10 maj 2018 började Adobe begränsa funktionaliteten för datumaktiverade och numeriska klassificeringar. Dessa klassificeringstyper har tagits bort från gränssnitten Admin och Klassificeringsimporter. Inga nya datumaktiverade och numeriska klassificeringar kan läggas till. Befintliga klassificeringar kan fortfarande hanteras (överföras till, tas bort) via standardarbetsflödet för klassificering, och kommer även i fortsättningen att vara tillgängliga vid rapportering.

Ett vanligt sätt att använda numeriska 2-klassificeringar är för numeriska variabler som ändras över tid för olika artiklar, t.ex. kostnaden för sålda varor. I admin kan du skapa klassificeringar på [!UICONTROL Conversion Classification] sidan och sedan använda importverktyget för att exportera en fil, göra ändringar och sedan importera filen tillbaka till Adobe. När du har importerat data kan du använda de numeriska klassificeringarna när du skapar beräknade värden.

>[!IMPORTANT]
>
>Analysis Workspace och Ad Hoc Analysis stöder inte Numeric 2-klassificeringar.

I följande tabell visas skillnaderna mellan klassificeringstyper:

| FUNKTION | TEXT | NUMERIC 1.0 | NUMERIC 2.0 |
|---|---|---|---|
| Visar som en rapport | Ja | Nej | Nej |
| Kan användas som mått | Nej | Ja | Ja |
| Kan skapas utifrån basrapporten | Ja | Nej | Ja |
| Beräknas baserat på händelser | Nej | Ja | Ja |
| Flera rader per nyckel | Nej | Nej | Ja |
| Kan ha olika värden för olika tidsperioder | Nej | Nej | Ja |
| Kan användas i beräknade värden | Nej | Ja | Ja |

