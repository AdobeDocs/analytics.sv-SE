---
title: Produktprofiler för Adobe Analytics
description: Lär dig hur produktprofiler kan användas som behörighetsförinställningar som produktadministratörer kan tilldela användare inom en organisation.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 0%

---

# Produktprofiler för Adobe Analytics

Produktprofiler är behörighetsförinställningar som produktadministratörer kan tilldela användare inom en organisation. Om du skapar en produktprofil och tilldelar en Experience Cloud-användare till produktprofilen ärver de behörighetsobjekten som finns i produktprofilen.

Se [Hantera produkter och profiler](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) i användarhandboken för Enterprise om du vill ha allmän information om produktprofiler.

## Produktprofiladministratörer

Produktprofiladministratörer är en valfri grupp som kan lägga till eller ta bort användare i den produktprofilen. Observera att en produktprofiladministratör inte är samma som en produktadministratör:

* Produktprofiladministratörer har inte fullständig åtkomst till Adobe Analytics. Fullständig åtkomst till Adobe Analytics är reserverad för produktadministratörer.
* Produktprofiladministratörer kan justera behörighetsobjekt i sina produktprofiler.
* Produktprofiladministratörer kan tilldela eller ta bort produktprofiler till användargrupper.
* Administratörer av produktprofiler är idealiska för gruppledare eller chefer som behöver ge och hantera åtkomst till Adobe Analytics för sitt team. Enskilda personer behöver inte störa systemadministratörer eller produktadministratörer för att bevilja åtkomst till Adobe Analytics.

## Adobe Analytics behörighetsobjekt

Följande behörigheter krävs i en produktprofil för att få tillgång till Adobe Analytics:

* Produktprofilen måste ha tillgång till minst en rapportserie
* Produktprofilen måste tillhöra behörighetsobjektet Analytics Tools **Analysis Workspace Access** (eller **Rapporter och analysåtkomst**)

### Rapportsviter

Ger åtkomst till rapportsviter som tillhör din Analytics-organisation. En användare måste tillhöra minst en rapportsserie för att kunna använda Adobe Analytics.

### Mätvärden

Ger åtkomst till mätvärden i rapportsviten. Mätvärdena listas som respektive komponent i Analysis Workspace, eller om mätvärdena är tillgängliga i Rapporter och analyser, tillgängliga som ett menyalternativ under Webbplatsmått.

Anpassade mätvärden är märkta med Custom Event 1-1000 för att hålla dem oberoende av rapportsviter. Om Custom Event 1 är ett aktiverat behörighetsobjekt har användaren åtkomst till event1 i alla rapportsviter i produktprofilen.

### Mått

Ger åtkomst till dimensioner i rapportsviten. Dimensionerna listas som respektive komponent i Analysis Workspace, eller om dimensionen är tillgänglig i Rapporter och analyser, tillgängliga som ett menyalternativ.

Anpassade variabler, som eVars, har etiketten Custom Conversion 1-250 för att de ska vara oberoende av rapportsviter. Om Custom Conversion 1 är ett aktiverat behörighetsobjekt har användaren åtkomst till eVar1 i alla rapportsviter i produktprofilen.

### Report Suite-verktyg

Rapportsvitens verktyg ger behörighetsobjekt åtkomst till funktioner som är specifika för de rapportsviter som användaren har tillgång till. Se [Report Suite-verktyg](report-suite-tools.md) för en fullständig lista över behörighetsobjekt och beskrivningar.

### Analysverktyg

Behörighetsobjekt för analysverktyg ger åtkomst till funktioner som är oberoende av inställningarna för rapportsviten. Se [Produktprofilbehörigheter för analysverktyg](analytics-tools.md) för en fullständig lista över behörighetsobjekt och beskrivningar.

## Produktprofilutvecklare

Utvecklare liknar användare, men de har möjlighet att använda Experience Cloud API på Adobe-utvecklare. Se [Hantera utvecklare](https://helpx.adobe.com/enterprise/using/manage-developers.html) i användarhandboken för Enterprise om du vill ha mer information. Om en användare beviljas Developer Access för någon profil kan han/hon få åtkomst till Dev Console (console.adobe.io) och redigera Adobe Analytics-integreringar. De API-anrop och svar för Analytics som är auktoriserade för användaren är beroende av nettobehörigheten för alla profiler där användaren har Developer Access.

Med profilbehörigheter som inkluderar alla mått, alla dimensioner och en rapportsvit kan en utvecklaråtkomstmedlem i profilen göra API-anrop relevanta för alla komponenter i den relevanta sviten. När avvikelseidentifiering har lagts till kan rapporterna innehålla fler svar, vilket lägger till mer avvikelsedata. Som tumregel gäller att om en profil beviljar åtkomst till ett scenario i Adobe Analytics-gränssnittet, så aktiverar Developer Access för en profil som är definierad på liknande sätt motsvarande API-anrop och svar.
