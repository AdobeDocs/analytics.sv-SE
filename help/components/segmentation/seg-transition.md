---
description: Frågor och svar om hur man hanterar äldre segment.
title: Frågor och svar om äldre segment
feature: Segmentation
exl-id: 316e2a2e-55d3-4c23-9985-9a6d90390e86
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 0%

---

# Frågor och svar om äldre segment

Svar på vanliga frågor om de bästa sätten att hantera äldre segment - segment som skapats före 2014.

## Hantera äldre segment {#legacy}

+++ **Vad hände med mina befintliga segment?**

Befintliga segment fortsätter att fungera som tidigare. Alla rapporter som använder dessa segment fortsätter att fungera korrekt. [Mer...](/help/components/segmentation/seg-transition.md)

De flesta tidigare fördefinierade och suite-segment migreras som segmentmallar till segmentbyggaren. Segmentmallar används för att snabbt skapa anpassade segment med gemensamma målgrupper. Segmentmallar kan inte användas direkt i en rapport, men de kan enkelt sparas i ett anpassat segment.

Segmentmallar är markerade med en speciell ikon i Segment Builder:

![](assets/seg_templates.png)

+++

+++ **Vad hände med schemalagda rapporter som har segment tillämpade?**

Schemalagda rapporter fortsätter att fungera korrekt med de segment som du har definierat.

När du tar bort ett segment fortsätter schemalagda rapporter och instrumentpaneler som använder det här segmentet att fungera som vanligt, dvs. segmentet eller instrumentpanelen fortsätter att använda det borttagna segmentet.

Schemalagda rapporter uppdateras inte när du redigerar ett segment med samma namn. Här är ett exempel: Låt oss anta att du har två segment med samma namn i olika rapportsviter:

![](assets/duplicate_seg_names.png)

Du har ett bokmärke som refererar till segmentet för huvudprogramrapporteringssviten. Sedan tar du bort segmentet eftersom det är en dubblett. Bokmärket fortsätter att köras och refererar till definitionen för det borttagna segmentet. Om du ändrar segmentdefinitionen för maindev-segmentet till att omfatta Catalinön och Tijuana Mexico, ändras inte det segment som används för bokmärket. Den gamla definitionen kommer att användas. Du åtgärdar detta genom att uppdatera bokmärket så att det refererar till den nya definitionen. Om du är osäker på om ett bokmärke, en kontrollpanel eller en schemalagd rapport använder ett borttaget segment, kan du ändra namnet på det återstående segmentet så att det blir tydligare om bokmärket använder det återstående segmentet.

+++

+++ **Vad hände med Data Warehouse?**

Alla befintliga Data Warehouse fungerar fortfarande i Data Warehouse. De flesta Data Warehouse fungerar även i andra komponenter som Analysis Workspace.

Du kan skapa eller redigera nya segment för Data Warehouse i segmentbyggaren/hanteraren. Produktkompatibilitetsmekanismen i segmentbyggaren avgör automatiskt om ett segment är kompatibelt med Data Warehouse.

+++

+++ **Vad hände med förkonfigurerade segment?**

* **Besök på en sida**
* **Besök från mobila enheter**
* **Besök från naturlig sökning**
* **Besök från betald sökning**
* **Besök med cookie-fil för besökar-ID**

Dessa segment migreras som segmentmallar till segmentbyggaren. Befintliga rapporter som använder dessa segment fortsätter att fungera korrekt.

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

Ägaren till dessa segment anges till den administratör som har det äldsta kontot i inloggningsföretagets lista över adminanvändare, men alla administratörer kan ta bort, redigera och dela dessa segment.

Segmenthanteringsgränssnittet i Admin Console där administratörer skapade och hanterade dessa globala segment är inte längre tillgängligt. Administratörer bör nu använda det nya segmentverktyget för att skapa segment och dela dem med lämpliga grupper eller individer eller med alla.

Befintliga segment som använder logik som har ändrats enligt beskrivningen i det här dokumentet fortsätter att fungera korrekt, men de måste uppdateras innan de kan sparas igen. Om du till exempel har ett befintligt segment där USA innehåller &quot;New York&quot;, fortsätter det att fungera korrekt, även om du nästa gång du redigerar segmentet måste uppdatera det så att det använder den uppräknade typen med ett lika stort villkor.

+++

+++ **Vad ska jag göra med duplicerade segment som har samma namn men som kan ha olika definitioner?**
Nu när segment fungerar i flera rapportsviter kan det finnas flera segment med samma namn. Vi rekommenderar att du antingen

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
* Webbläsare - använd dimensionen Webbläsartyper för att få alla webbläsare i en typ, t.ex. Google Chrome
* Operativsystem - Använd dimensionerna för OS-typer för att få alla operativsystem i en typ, t.ex. Microsoft Windows.
* Se&quot;Nya och namnändrade Dimensioner&quot; (se nedan)

## Nya och namnändrade Dimensioner {#renamed}

Tabellen nedan innehåller en lista med dimensioner som har bytt namn i Segment Builder.

| Namn på ny Dimension | Tidigare namn | Anteckningar |
|--- |--- |--- |
| Operativsystemstyper | Nytt | Lades till våren 2015. |
| Webbläsarbredd - paketerad | Bredd på webbläsare | Den här dimensionen är kompatibel med alla gränssnitt och delas upp i en numrerad lista med intervall i stället för specifika heltalsvärden. Om du behöver segmentera specifika värden använder du den detaljerade versionen av dimensionen i ett datalagersegment. |
| Webbläsarhöjd - paketerad | Webbläsarhöjd | Den här dimensionen är kompatibel med alla gränssnitt och delas upp i en numrerad lista med intervall i stället för specifika heltalsvärden. Om du behöver segmentera specifika värden använder du den detaljerade versionen av dimensionen i ett datalagersegment. |
| Webbläsarbredd - Detaljerad | Bredd på webbläsare | Namnet har ändrats och är nu endast kompatibelt med datalagret. När du definierar segment som är kompatibla med alla gränssnitt använder du den uppräknade typen Webbläsarbredd - Bucketed. |
| Webbläsarhöjd - granulerad | Webbläsarhöjd | Namnet har ändrats och är nu endast kompatibelt med datalagret. När du definierar segment som är kompatibla med alla gränssnitt ska du använda den uppräknade typen Webbläsarhöjd - Bucketed. |
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

## Ändrar till strängbaserade Dimensioner som har kända värden {#string-based-dims}

Strängbaserade dimensioner med en känd uppsättning värden ändrades till uppräknade typer. När du skapar ett segment med dessa mått fylls listan i med alla kända värden och den enda operatorn som stöds är lika med. På så sätt kan du snabbt segmentera de exakta värden som du sökte efter utan att välja oönskade värden när du använder mindre begränsande matchning.

Följande dimensioner ändrades till uppräknade listor:

| Dimensionens namn | Dimensionens namn | Dimensionens namn |
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

## Ändrar till heltalsbaserade Dimensioner med kända värden {#integer-based-dims}

Heltalsbaserade dimensioner (till exempel webbläsarbredd) med en känd uppsättning värden delades upp i uppräknade intervall så att du snabbt kan definiera segment för ett visst intervall. Dessa uppräknade listor läggs till med &quot; - Bucketed&quot; efter dimensionsnamnet. På följande skärm visas hur de här dimensionerna segmenteras med hjälp av det föregående och nya segmentbyggargränssnittet:

![](assets/seg_browser_dimension.png)

Operatorerna för mindre än, större än och liknande är nu kompatibla med enbart Data Warehouse. Segment som är avsedda att vara kompatibla med alla rapporteringsgränssnitt bör använda måttets &quot;Bucketed&quot;-version med likhetsoperatorn.
