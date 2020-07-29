---
title: Felsöka leveranstider för Data warehouse-begäran
description: Ta reda på eventuella problem med en Data warehouse-begäran som kan förlänga leveranstiden.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Felsöka leveranstider för Data warehouse-begäran

En viss begäran från Data warehouse kan ta en plats från mindre än en timme till flera dagar eller mer. Det är svårt att uppskatta hur lång tid det tar att behandla en begäran om behandling, på grund av följande faktorer:

* Datumintervallet för begäran
* Hur mycket trafik din rapportsvit tog emot under den begärda tidsperioden
* Antalet regler inom ett segment och vilka variabler inom ett segment som används
* Hur mycket data som inkluderas i segmentet
* Antalet indelningar som används och antalet unika värden inom varje indelning
* Antalet mätvärden som används
* Antalet samtidiga begäranden som behandlas
* VISTA-regler, om de är konfigurerade att gälla för DataWarehouse-begäranden

Om det tar lång tid att se förfrågningar från data warehouse kan du ändra dem så att du får plats med följande:

* **Använd ett segment som innehåller ett mindre dataprov**: Ju mindre data en begäran fungerar med, desto snabbare returneras en rapport.
* **Kör begäranden i 14-dagarsintervall eller mindre**: Mindre begäranden behandlas snabbare än stora.
* **Använd färre uppdelningar:** Många uppdelningar i en Data warehouse-begäran ökar bearbetningstiden exponentiellt.

>[!IMPORTANT]
>
> *Det finns inget sätt att snabba upp leveransen av en förfrågan från Data warehouse.*

Om du behöver dessa typer av rapporter i tid bör du överväga följande alternativ:

* **Analysis Workspace**: Även om det inte finns ett obegränsat antal dimensionsobjekt, innehåller det nästan alla andra användningsfall som Data warehouse tillhandahåller.
* **Dataflöde**: Tar dagligen med alla rådata i en rapportserie och skickar den till en FTP-plats. Du kan sedan importera dessa data till din egen databas och köra frågor för att hämta de data du söker.
* **Lösningen** Custom Engineering Services: Adobe Engineering Services kan ge er en anpassad lösning till en extra kostnad. Kontakta din organisations kontoansvarige om du vill ha mer information.
