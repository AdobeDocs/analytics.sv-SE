---
title: Hierarki
description: En anpassad dimension som du kan använda vid rapportering.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
source-git-commit: 42ff5018411dae64039ed6f12ec2b8ed12aceff4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Hierarki

>[!IMPORTANT]
>
>Den här dimensionen är pensionerad och inte en tillgänglig dimension i Analysis Workspace. Adobe rekommenderar att du använder [eVars](evar.md) och klassificeringar istället.

Hierarkier är anpassade variabler som du kan använda hur du vill. De finns inte kvar efter den träff de har ställts in. Upp till 5 hierarkier är tillgängliga om ditt kontrakt med Adobe stöder det.

## Fylla i hierarkier med data

Varje hierarki samlar in data från [`h1` - `h5` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. Till exempel `h1` frågesträngsparametern samlar in data för hierarki 1, medan `h4` frågesträngsparametern samlar in data för hierarki 4.

AppMeasurement, som kompilerar JavaScript-variabler till en bildbegäran för datainsamling, använder variablerna `hier1` - `hier5`. Se [hövding](/help/implement/vars/page-vars/hier.md) i Implementeringsanvändarhandboken för implementeringsriktlinjer.

## Dimensioner

Eftersom hierarkier innehåller anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekt som finns för varje hierarki. Se till att du registrerar syftet med varje hierarki och typiska dimensionsobjekt i en [konstruktionsdokument](/help/implement/prepare/solution-design.md).
