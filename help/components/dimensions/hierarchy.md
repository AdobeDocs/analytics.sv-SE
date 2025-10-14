---
title: Hierarki
description: (Borttagen) En anpassad dimension som du kan använda vid rapportering.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 0%

---

# Hierarki

>[!IMPORTANT]
>
>Den här dimensionen har tagits bort och är inte en tillgänglig [dimension](overview.md) i Analysis Workspace. Adobe rekommenderar att du använder [eVars](evar.md) och klassificeringar i stället.

Hierarkier är anpassade variabler som du kan använda hur du vill. De finns inte kvar efter den träff de har ställts in. Upp till 5 hierarkier är tillgängliga om ditt kontrakt med Adobe stöder det.

## Fylla i hierarkier med data

Varje hierarki samlar in data från [`h1` - `h5` frågesträngen &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden. Frågesträngsparametern `h1` samlar till exempel in data för hierarki 1, medan frågesträngsparametern `h4` samlar in data för hierarki 4.

AppMeasurementet, som kompilerar JavaScript-variabler till en bildbegäran för datainsamling, använder variablerna `hier1` - `hier5`. Mer information om implementeringsriktlinjer finns i [hier](/help/implement/vars/page-vars/hier.md) i Implementeringsanvändarhandboken.

## Dimensioner

Eftersom hierarkier innehåller anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekt som finns för varje hierarki. Se till att du registrerar syftet med varje hierarki och typiska dimensionsobjekt i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).
