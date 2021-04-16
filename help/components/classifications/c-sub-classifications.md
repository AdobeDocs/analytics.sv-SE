---
description: Adobe Analytics har stöd för både klassificeringsmodeller på en och flera nivåer. Med en klassificeringshierarki kan du tillämpa en klassificering på en klassificering.
subtopic: Classifications
title: Om underklassificeringar
feature: Administratörsverktyg
uuid: 48bd7fc1-54a1-40ef-bc55-395338522f2d
exl-id: 3d22a8c0-743d-47f3-ba15-aaef1ebd4dff
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 8%

---

# Om underklassificeringar

Adobe Analytics har stöd för både klassificeringsmodeller på en och flera nivåer. Med en klassificeringshierarki kan du tillämpa en klassificering på en klassificering.

>[!NOTE]
>
>Delklassificering avser möjligheten att skapa klassificeringar av klassificeringar. Detta är dock inte samma sak som [!UICONTROL Classification Hierarchy] som används för att skapa [!UICONTROL Hierarchy]-rapporter. Mer information om klassificeringshierarkier finns i [Klassificeringshierarkier](/help/admin/admin/conversion-var-admin/classification-hierarchies.md).

Exempel:

![](assets/single-level-popup-C.png)

Varje klassificering i denna modell är oberoende och motsvarar en ny delrapport för den valda rapportvariabeln. Dessutom utgör varje klassificering en datakolumn i datafilen, med klassificeringsnamnet som kolumnrubrik. Exempel:

| NYCKEL | EGENSKAP 1 | EGENSKAP 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

Mer information om datafilen finns i [Klassificeringsdatafiler](/help/components/classifications/importer/c-saint-data-files.md).

Klassificeringar på flera nivåer består av överordnade och underordnade klassificeringar. Exempel:

![](assets/Multi-Level-Class-popup.png)

**Överordnade klassificeringar:** En överordnad klassificering är en klassificering som har en associerad underordnad klassificering. En klassificering kan vara både en överordnad och underordnad klassificering. De översta överordnade klassificeringarna motsvarar klassificeringar på en nivå.

**Underordnade klassificeringar:** En underordnad klassificering är en klassificering som har en annan klassificering som överordnad i stället för variabeln. Underordnade klassificeringar innehåller ytterligare information om deras överordnade klassificering. En [!UICONTROL Campaigns]-klassificering kan till exempel ha en underordnad klassificering för Campaign Owner. [!UICONTROL Numeric] klassificeringar fungerar också som mått i klassificeringsrapporter.

Varje klassificering, antingen överordnad eller underordnad, utgör en datakolumn i datafilen. Kolumnrubriken för en underordnad klassificering med följande namnformat:

`<parent_name>^<child_name>`

Mer information om datafilformatet finns i [Klassificeringsdatafiler](/help/components/classifications/importer/c-saint-data-files.md).

Exempel:

| NYCKEL | EGENSKAP 1 | Egenskap 1^Egenskap 1-1 | Egenskap 1^Egenskap 1-2 | Egenskap 2 |
|---|---|---|---|---|
| 123 | ABC | Grön | Liten | A12B |
| 456 | DEF | Röd | Stor | C3D4 |

Även om filmallen för en klassificering på flera nivåer är mer komplex är styrkan med klassificeringar på flera nivåer att separata nivåer kan överföras som separata filer. Den här metoden kan användas för att minimera mängden data som behöver överföras regelbundet (varje dag, varje vecka och så vidare) genom att gruppera data i klassificeringsnivåer som ändras över tid jämfört med dem som inte gör det.

>[!NOTE]
>
>Om kolumnen [!UICONTROL Key] i en datafil är tom genererar Adobe automatiskt unika nycklar för varje datarad. Om du vill undvika att en fil skadas när du överför en datafil med klassificeringsdata på andra nivån eller högre, ska du fylla i varje rad i [!UICONTROL Key]-kolumnen med en asterisk (*).

## Exempel

![](assets/sample-product-classifications.png)

>[!NOTE]
>
>Produktklassificeringsdata är begränsade till dataattribut som är direkt relaterade till produkten. Uppgifterna är inte begränsade till hur produkterna kategoriseras eller säljs på webbplatsen. Dataelement som försäljningskategorier, noder för webbläsare eller försäljningsobjekt är inte produktklassificeringsdata. I stället hämtas dessa element i rapportkonverteringsvariabler.

När du överför datafiler för den här produktklassificeringen kan du överföra klassificeringsdata som en enda fil eller som flera filer (se nedan). Genom att färgkoden separeras i fil 1 och färgnamnet i fil 2, behöver färgnamnsdata (som bara kan vara ett fåtal rader) bara uppdateras när nya färgkoder skapas. Då tas färgnamnsfältet (CODE^COLOR) bort från den mest uppdaterade filen 1 och filstorleken och komplexiteten minskas när datafilen genereras.

### Produktklassificering - En fil {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| NYCKEL | PRODUKTNAMN | PRODUKTINFORMATION | GENDER | STORLEK | KOD | KOD^FÄRG |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | Polo Shirt, kort sikt (M,01) för män | M | M | 01 | Sten |
| 410390014 | Polo-SS | Polo Shirt, kort sikt (L,03) för män | M | L | 03 | Sidhuvud |
| 410390015 | Polo-LS | Lång sikt för kvinnor (S,23) | F | S | 23 | Turkos |

### Produktklassificering - flera filer (fil 1) {#section_A99F7D0F145540069BA4EEC0597FF13F}

| NYCKEL | PRODUKTNAMN | PRODUKTINFORMATION | GENDER | STORLEK | KOD |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | Polo Shirt, kort sikt (M,01) för män | M | M | 01 |
| 410390014 | Polo-SS | Polo Shirt, kort sikt (L,03) för män | M | L | 03 |
| 410390015 | Polo-LS | Lång sikt för kvinnor (S,23) | F | S | 23 |

### Produktklassificering - flera filer (fil 2) {#section_19ED95C33B174A9687E81714568D56A3}

| NYCKEL | KOD | KOD^FÄRG |
|---|---|---|
| * | 01 | Sten |
| * | 03 | Sidhuvud |
| * | 23 | Turkos |
