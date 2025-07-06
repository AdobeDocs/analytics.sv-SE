---
description: Lär dig hantera äldre segment.
title: Vanliga frågor om äldre segment
feature: Segmentation
exl-id: 316e2a2e-55d3-4c23-9985-9a6d90390e86
source-git-commit: c44bffa45ab8ed29ea28b91b2b3dc51811ab25fe
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 0%

---

# Äldre segment

I den här artikeln besvaras vanliga frågor och svar om de bästa sätten att hantera äldre segment. Äldre segment är segment som skapades före 2014.

## Hantera äldre segment {#legacy}

+++ **Vad hände med mina befintliga segment?**

Dina befintliga segment fortsätter att fungera som de gjorde tidigare. Rapporter som använder dessa segment fungerar fortfarande korrekt.

De flesta tidigare fördefinierade och suite-segment migreras som segmentmallar till segmentbyggaren. Segmentmallar används för att snabbt skapa anpassade segment med gemensamma målgrupper. Segmentmallar kan inte användas direkt i en rapport, men de kan enkelt sparas i ett anpassat segment.

Segmentmallar markeras med en speciell ikon, ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg), i segmentbyggaren.



+++

+++ **Vad hände med schemalagda rapporter som har segment tillämpade?**

Schemalagda rapporter fortsätter att fungera korrekt med de segment som du har definierat.

När du tar bort ett segment fortsätter schemalagda rapporter och instrumentpaneler som använder det här segmentet att fungera som vanligt, dvs. segmentet eller instrumentpanelen fortsätter att använda det borttagna segmentet.

Schemalagda rapporter uppdateras inte när du redigerar ett segment med samma namn. Här är ett exempel: Låt oss anta att du har två segment med samma namn i olika rapportsviter:

![](assets/duplicate_seg_names.png)

Du har en visualisering som refererar till segmentet för rapportsviten **[!UICONTROL mainprod]**. Sedan tar du bort segmentet eftersom det är en dubblett. Visualiseringen fortsätter att köras och refererar till definitionen för det borttagna segmentet. Om du ändrar segmentdefinitionen för maindev-segmentet till att omfatta Catalinön och Tijuana, Mexiko, ändras inte segmentet som används för visualiseringen utan den gamla definitionen används. Om du vill använda den nya definitionen uppdaterar du visualiseringen så att den refererar till den nya definitionen. Om du är osäker på om en visualiserings-, projekt- eller schemalagd rapport använder ett borttaget segment, ändrar du namnet på det återstående segmentet för att visa om visualiseringen använder det återstående segmentet.

+++

+++ **Vad hände med Data Warehouse-segmenten?**

Alla befintliga Data Warehouse-segment fungerar fortfarande i Data Warehouse. De flesta Data Warehouse-segment fungerar även i andra komponenter som Analysis Workspace.

Du kan skapa eller redigera nya Data Warehouse-segment i segmentbyggaren/segmenthanteraren. Produktkompatibilitetsmekanismen i segmentbyggaren avgör automatiskt om ett segment är kompatibelt med Data Warehouse.

+++

+++ **Vad hände med förkonfigurerade segment?**

* **Besök på en sida**
* **Besök från mobila enheter**
* **Besök från naturlig sökning**
* **Besök från betald sökning**
* **Besök med cookie-fil för besökar-ID**

Dessa segment migreras som segmentmallar till segmentbyggaren. Befintliga rapporter som använder dessa segment fungerar fortfarande korrekt.

+++

+++ **Vad hände med Experience Cloud-segment (Suite):**

* Icke-köpare
* Inköpare
* Första gången du besöker
* Besök från sociala webbplatser
* Besök under mer än 10 minuter*
* Besök med 5+ tidigare besök*
* Besök från Facebook*

De flesta av dessa segment (utom de som är markerade med en asterisk *) flyttades över som segmentmallar till segmentbyggaren. Dessutom har flera nya segmentmallar lagts till.

Befintliga rapporter som använder dessa segment fungerar fortfarande korrekt.

+++

+++ **Vad hände med administratörssegment (kallas även&quot;globala&quot; segment)?**

**Admin**-segment migreras till det nya segmentgränssnittet och visas som segment som delas med alla.

Ägaren till dessa segment anges till administratören med det äldsta kontot för administratörsanvändare. Alla administratörer kan dock ta bort, redigera och dela dessa segment.

Segmenthanteringsgränssnittet i Admin Console där administratörer skapade och hanterade dessa globala segment är inte längre tillgängligt. Administratörer bör nu använda det nya segmentverktyget för att skapa segment och dela dem med lämpliga grupper eller individer eller med alla.

Befintliga segment som använder logik som har ändrats enligt beskrivningen i det här dokumentet fortsätter att fungera korrekt, men segmenten måste uppdateras innan de kan sparas igen. Om du till exempel har ett befintligt segment där **[!UICONTROL US States]** **[!UICONTROL contains]** `New York` fortsätter det segmentet att fungera korrekt. Nästa gång du redigerar segmentet måste du uppdatera segmentet så att det använder den uppräknade typen med ett **[!UICONTROL equals]**-villkor.

+++

+++ **Vad ska jag göra med duplicerade segment som har samma namn men som kan ha olika definitioner?**
Nu när segment fungerar i flera rapportsviter kan det finnas flera segment med samma namn. Du bör:

* Byt namn på segment som har samma namn men olika definitioner, eller
* Ta bort segment som inte längre behövs.

+++

+++ **Vad rekommenderar Adobe när det gäller att rensa upp segment?**

* Tagga alla segment med äldre tagg.
* Granska de segment du har.
* Lägg till dem i segmentbiblioteket där det är tillämpligt.
* Godkänn kanoniska segment.
* Tagga segment enligt [bästa praxis](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

+++

### Migreringstips

Följande tips hjälper dig att migrera gemensamma dimensioner:

* Geo-stad/region/land - sök efter och välj specifika städer, regioner eller länder i stället för att använda en partiell matchning.
* Webbläsare - använd dimensionen Webbläsartyper för att få alla webbläsare i en typ, till exempel Google Chrome
* Operativsystem - Använd dimensionerna för OS-typer för att få alla operativsystem i en typ, till exempel Microsoft Windows.
* Se &quot;Nya och namnändrade dimensioner&quot; (se nedan)

## Nya dimensioner med nytt namn {#renamed}

Följande tabell innehåller en lista med dimensioner som har fått ett nytt namn i segmentbyggaren.

| Nytt Dimension-namn | Tidigare namn | Anteckningar |
|--- |--- |--- |
| Operativsystemstyper | Nyhet | Lades till våren 2015. |
| Webbläsarbredd - paketerad | Bredd på webbläsare | Den här dimensionen är kompatibel med alla gränssnitt och delas upp i en numrerad lista med intervall i stället för specifika heltalsvärden. Om du behöver segmentera specifika värden använder du den detaljerade versionen av dimensionen i ett Data Warehouse-segment. |
| Webbläsarhöjd - paketerad | Webbläsarhöjd | Den här dimensionen är kompatibel med alla gränssnitt och delas upp i en numrerad lista med intervall i stället för specifika heltalsvärden. Om du behöver segmentera specifika värden använder du den detaljerade versionen av dimensionen i ett Data Warehouse-segment. |
| Webbläsarbredd - Detaljerad | Bredd på webbläsare | Dimensionens namn har ändrats och är nu endast kompatibelt med Data Warehouse. När du definierar segment som är kompatibla med alla gränssnitt använder du den uppräknade typen Webbläsarbredd - Bucketed. |
| Webbläsarhöjd - granulerad | Webbläsarhöjd | Dimensionens namn har ändrats och är nu endast kompatibelt med Data Warehouse. När du definierar segment som är kompatibla med alla gränssnitt ska du använda den uppräknade typen Webbläsarhöjd - Bucketed. |
| Cookie-stöd | Cookies | - |
| Färgdjup | Skärmfärgdjup | - |
| - | &quot;App - *&quot; | Prefixen &quot;App -&quot; har tagits bort från ett antal dimensionstyper. Eftersom mobilappsdata vanligtvis samlas in i en rapportserie som inte innehåller webbdata var dessa prefix inte nödvändiga. |
| Inmatningssidans originalformat | Ursprunglig startsida | - |
| Java aktiverat | Java | - |
| Högsta URL-längd för mobil webbläsare | URL-längd för mobil webbläsare | - |
| Dekoration av mobilpost | Stöd för e-post för mobildekoration | - |
| Mobil enhet | Namn på mobil enhet | - |
| Max bokmärkeslängd för mobil | URL-längd för maximalt bokmärke för mobil | - |
| Maximal e-postlängd för mobil | Högsta URL-längd för mobil e-post | - |
| Mobiloperativsystem (inaktuellt) | Mobiloperativsystem | Använd operativsystemsdimensionen och lägg in besök från mobilsegmenten istället. |
| Mobil push to Talk | Mobil PTT | - |
| Undersökningsvisning | Totalt antal undersökningsvisningar | - |
| Undersökningssvar | Totalt antal undersökningssvar | - |
| Besöksdjup | Banlängd | - |
| Postnummer | Postnummer | - |

{style="table-layout:auto"}

## Ändrar till strängbaserade dimensioner med kända värden {#string-based-dims}

Strängbaserade dimensioner med en känd uppsättning värden har ändrats till uppräknade typer. När du skapar ett segment med de här dimensionerna fylls listan i med alla kända värden och den enda operatorn som stöds är **[!UICONTROL equals]**. Med den här värdeuppsättningen kan du snabbt segmentera de exakta värden som du sökte efter utan att markera oönskade värden när du använder mindre begränsande matchning.

Följande dimensioner ändrades till uppräknade listor:

| Dimension name | Dimension name | Dimension name |
| --- | --- | --- |
| mobiltillverkare | mobil e-postlängd | färgdjup |
| mobilskärmstorlek | mobilenhetsnummer | bildskärmsupplösning |
| mobilskärmshöjd | mobilpush för att prata | plugin |
| stöd för mobilcookies | mobilmejldekoration | operativsystem |
| stöd för mobilbilder | mobilinformationstjänster | referenstyp |
| mobilfärgdjup | mobilenhetstyp | sökmotor |
| stöd för mobilljud | webbläsartyp | läge |
| stöd för mobilvideo | webbläsare | land |
| mobil drm | anslutningstyp | geo region |
| mobilnätsprotokoll | mobiloperatör | storstad |
| mobiler | cookie | geo dma |
| mobile java vm | kundlojalitet | beständig cookie |
| längd för mobilbokmärke | java aktiverat | betalsökningar |
| mobil URL-längd | språk |  |

## Ändrar till heltalsbaserade dimensioner med kända värden {#integer-based-dims}

Heltalsbaserade dimensioner (till exempel webbläsarbredd) med en känd uppsättning värden delas upp i uppräknade intervall så att du snabbt kan definiera segment för ett visst intervall. Dessa uppräknade listor läggs till med &quot; - Bucketed&quot; efter dimensionsnamnet. På följande skärm visas hur de här dimensionerna segmenteras med hjälp av det föregående och nya segmentbyggargränssnittet:

![](assets/seg_browser_dimension.png)

Operatorerna för mindre än, större än och liknande är nu endast kompatibla med Data Warehouse-segment. Segment som är avsedda att vara kompatibla med alla rapporteringsgränssnitt ska använda måttets &quot;Bucketed&quot;-version med operatorn **[!UICONTROL equals]**.
