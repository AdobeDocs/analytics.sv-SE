---
title: Produktprofiler för Adobe Analytics
description: Lär dig hur produktprofiler kan användas som behörighetsförinställningar som produktadministratörer kan tilldela användare inom en organisation.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
source-git-commit: ed7b25491de5c1238e846997ec903df4fd4ee18c
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 0%

---

# Produktprofiler för Adobe Analytics

Produktprofiler är behörighetsförinställningar som produktadministratörer kan tilldela användare inom en organisation. Om du skapar en produktprofil och tilldelar en Experience Cloud-användare till produktprofilen ärver de behörighetsobjekten i produktprofilen.

Allmän information om produktprofiler, inklusive hur du skapar produktprofiler och tilldelar användare, finns i [Hantera produktprofiler för företagsanvändare](https://helpx.adobe.com/se/enterprise/using/manage-product-profiles.html) i användarhandboken för Enterprise.

## Produktprofiladministratörer

Produktprofiladministratörer är en valfri grupp som kan lägga till eller ta bort användare i den produktprofilen. Observera att en produktprofiladministratör inte är samma som en produktadministratör:

* Produktprofiladministratörer har inte fullständig åtkomst till Adobe Analytics. Fullständig åtkomst till Adobe Analytics är reserverad för produktadministratörer.
* Produktprofiladministratörer kan inte justera behörighetsobjekt i sina produktprofiler.
* Produktprofiladministratörer kan tilldela eller ta bort produktprofiler till användargrupper.
* Administratörer av produktprofiler är idealiska för gruppledare eller chefer som behöver ge och hantera åtkomst till Adobe Analytics för sitt team. Enskilda personer behöver inte störa systemadministratörer eller produktadministratörer för att bevilja åtkomst till Adobe Analytics.

Mer information om hur du tilldelar produktprofiladministratörer finns i avsnittet Hantera produktprofiladministratörer i artikeln [Hantera produktprofiler för företagsanvändare](https://helpx.adobe.com/se/enterprise/using/manage-product-profiles.html) i användarhandboken för Enterprise.

## Adobe Analytics behörighetsobjekt

Följande behörigheter krävs i en och samma produktprofil för att få tillgång till Adobe Analytics:

* Produktprofilen måste ha tillgång till minst en rapportserie
* Produktprofilen måste tillhöra behörighetsobjektet **Analysis Workspace Access** för Analytics-verktygen.

### Rapportsviter

Ger åtkomst till rapportsviter som tillhör din Analytics-organisation. En användare måste tillhöra minst en rapportsserie för att kunna använda Adobe Analytics.

### Mätvärden

Ger åtkomst till mätvärden i rapportsviten. Mätvärden anges som respektive komponent i Analysis Workspace.

Anpassade mätvärden är märkta med Custom Event 1-1000 för att hålla dem oberoende av rapportsviter. Om Custom Event 1 är ett aktiverat behörighetsobjekt har användaren åtkomst till event1 i alla rapportsviter i produktprofilen.

### Mått

Ger åtkomst till dimensioner i rapportsviten. Dimensioner anges som respektive komponent i Analysis Workspace.

Anpassade variabler, som eVars, har etiketten Custom Conversion 1-250 för att de ska vara oberoende av rapportsviter. Om Custom Conversion 1 är ett aktiverat behörighetsobjekt har den användaren åtkomst till eVar1 i alla rapportsviter i produktprofilen.

### Report Suite-verktyg

Rapportsvitens verktyg ger behörighetsobjekt åtkomst till funktioner som är specifika för de rapportsviter som användaren har tillgång till. En fullständig lista över behörighetsobjekt och beskrivningar finns i [Report Suite-verktygen](report-suite-tools.md).

### Analysverktyg

Behörighetsobjekt för analysverktyg ger åtkomst till funktioner som är oberoende av inställningarna för rapportsviten. En fullständig lista över behörighetsobjekt och beskrivningar finns i [Produktprofilbehörigheter för analysverktyg](analytics-tools.md).

## Produktprofilutvecklare

Utvecklare liknar användare, förutom att de har möjlighet att använda Experience Cloud API på Adobe Developer. Mer information finns i [Hantera utvecklare](https://helpx.adobe.com/se/enterprise/using/manage-developers.html) i användarhandboken för Enterprise. Om en användare beviljas utvecklaråtkomst för någon profil kan han/hon få åtkomst till Dev Console (console.adobe.io) och redigera Adobe Analytics-integreringar. De API-anrop och svar för Analytics som är auktoriserade för användaren är beroende av nettobehörigheten för alla profiler som användaren har utvecklaråtkomst till.

Med profilbehörigheter som innehåller alla mätvärden, alla dimensioner och en rapportsvit kan utvecklaren göra API-anrop relevanta för alla komponenter i rapportsviten. Om behörighetsobjektet för avvikelseidentifiering läggs till kan API-svar innehålla avvikande data. Som tumregel gäller att om en profil beviljar åtkomst till ett scenario i Adobe Analytics-gränssnittet, kommer utvecklare att ha tillgång till en profil som har definierats på liknande sätt att aktivera motsvarande API-anrop och svar.
