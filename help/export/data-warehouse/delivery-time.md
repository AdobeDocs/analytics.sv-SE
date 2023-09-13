---
title: Felsök leveranstider för Data Warehouse
description: Ta reda på eventuella problem med en Data Warehouse som kan förlänga leveranstiderna.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: fc6a2deabaf2012cefebf4864db19aef1825adf2
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---

# Felsök leveranstider för Data Warehouse

En viss Data Warehouse kan ta var som helst från mindre än en timme till flera dagar eller mer. Det är svårt att uppskatta hur lång tid det tar att behandla en begäran om behandling, på grund av följande faktorer:

* Datumintervallet för begäran
* Hur mycket trafik din rapportsvit tog emot under den begärda tidsperioden
* Antalet regler inom ett segment och vilka variabler inom ett segment som används
* Hur mycket data som inkluderas i segmentet
* Antalet indelningar som används och antalet unika värden inom varje indelning
* Antalet mätvärden som används
* Antalet samtidiga begäranden som behandlas
* VISTA-regler, om de är konfigurerade att gälla för begäranden om DataWarehouse

## Ändra förfrågningar för att snabba upp leveransen

Om det tar lång tid att begära Data Warehouse bör du ändra dina önskemål. Att ändra en begäran är det enda sättet att snabba upp leveransen av en begäran om Data Warehouse.

Om du vill snabba upp leveransen av en begäran om Data Warehouse kan du ändra den på något av följande sätt:

* **Använd ett segment som innehåller ett mindre dataprov**: Ju mindre data en begäran fungerar med, desto snabbare returneras en rapport.
* **Kör begäranden i 14-dagarsintervall eller mindre**: Mindre begäranden behandlas snabbare än stora begäranden.
* **Använd färre uppdelningar:** Många uppdelningar i en begäran ökar tiden det tar att bearbeta den exponentiellt.

## Använd en alternativ metod

Om du behöver dessa typer av rapporter i tid bör du överväga följande alternativ:

* **Analysis Workspace**: Även om ett obegränsat antal dimensionsobjekt inte är tillgängligt innehåller det nästan alla andra användningsfall som Datan Warehouse tillhandahåller.
* **Datafeed**: Tar dagligen med alla rådata i en rapportsserie och skickar den till ett molnmål. Du kan sedan importera data till din egen databas och köra frågor för att få de data du behöver.
* **Anpassade tekniktjänster**: Adobe Engineering Services kan tillhandahålla en anpassad lösning för er organisation till en extra kostnad. Kontakta kontoteamet på Adobe om du vill ha mer information.
