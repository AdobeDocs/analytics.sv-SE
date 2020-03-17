---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Produktprofiler i Adobe Analytics

Produktprofiler är en behörighetsförinställning som produktadministratörer kan tilldela användare inom en organisation. Om du skapar en produktprofil och tilldelar en Experience Cloud-användare till produktprofilen ärver de behörighetsobjekten som finns i produktprofilen.

Se [Hantera produkter och profiler](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) i Enterprise-användarhandboken för allmän information om produktprofiler.

## Produktprofiladministratörer

Produktprofiladministratörer är en valfri grupp som kan lägga till eller ta bort användare i den produktprofilen. Observera att en produktprofiladministratör inte är samma som en produktadministratör:

* Administratörer av produktprofiler ansvarar endast för användarlistan för en produktprofil.
* Produktprofiladministratörer har inte fullständig åtkomst till Adobe Analytics. Fullständig åtkomst till Adobe Analytics är reserverad för produktadministratörer.
* Produktprofiladministratörer kan inte justera behörighetsobjekt i sin produktprofil. en produktadministratör måste göra justeringar av behörighetsobjekt.
* Administratörer av produktprofiler är idealiska för gruppledare eller chefer som bara behöver ge och hantera åtkomst till Adobe Analytics för sitt team. Enskilda personer behöver inte störa systemadministratörer eller produktadministratörer för att ge åtkomst till Adobe Analytics.

## Behörighetsobjekt för Adobe Analytics

Följande behörigheter krävs i en produktprofil för att få tillgång till Adobe Analytics:

* Produktprofilen måste ha tillgång till minst en rapportserie
* Produktprofilen måste tillhöra behörighetsobjektet Analytics Tools **Analysis Workspace Access** (eller **Reports &amp; Analytics Access**)

### Rapportsviter

Ger åtkomst till rapportsviter som tillhör din Analytics-organisation. En användare måste tillhöra minst en rapportsserie för att få tillgång till Adobe Analytics.

### Mått

Ger åtkomst till mätvärden i rapportsviten. Mätvärdena listas som respektive komponent i Analysis Workspace, eller om mätvärdena är tillgängliga i Rapporter och analyser, som är tillgängliga som ett menyalternativ under Site Metrics.

Anpassade mätvärden är märkta med Custom Event 1-1000 för att hålla dem oberoende av rapportsviter. Om Custom Event 1 är ett aktiverat behörighetsobjekt har användaren åtkomst till event1 i alla rapportsviter i produktprofilen.

### Dimensioner

Ger åtkomst till dimensioner i rapportsviten. Dimensionerna listas som respektive komponent i Analysis Workspace, eller om dimensionen är tillgänglig i Rapporter och analyser, tillgängliga som ett menyalternativ.

Anpassade variabler, som eVars, har etiketten Custom Conversion 1-250 för att de ska vara oberoende av rapportsviter. Om Custom Conversion 1 är ett aktiverat behörighetsobjekt har användaren åtkomst till eVar1 i alla rapportsviter i produktprofilen.

### Report Suite-verktyg

Rapportsvitens verktyg ger behörighetsobjekt åtkomst till funktioner som är specifika för de rapportsviter som användaren har tillgång till. En fullständig lista över behörighetsobjekt och beskrivningar finns i [Report Suite-verktygen](report-suite-tools.md) .

### Analysverktyg

Behörighetsobjekt för analysverktyg ger åtkomst till funktioner som är oberoende av inställningarna för rapportsviten. En fullständig lista över behörighetsobjekt och beskrivningar finns i [Analytics Tools](analytics-tools.md) .

## Produktprofilutvecklare

Utvecklare liknar användare, förutom att de har möjlighet att använda Experience Cloud-API:t på Adobe I/O. Mer information finns i [Hantera utvecklare](https://helpx.adobe.com/enterprise/using/manage-developers.html) i användarhandboken för Enterprise.
