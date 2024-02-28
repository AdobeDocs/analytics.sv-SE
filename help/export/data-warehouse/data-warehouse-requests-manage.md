---
description: Med Hanteraren för begäran kan du visa, duplicera och prioritera om begäranden.
title: Hantera förfrågningar från Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: 4c9451c1df31ec22bf3f7b0198f294d8e57d79d5
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 0%

---

# Hantera förfrågningar från Data Warehouse

Du kan visa och hantera förfrågningar från Data Warehouse som du har gjort. Endast administratörer kan visa och hantera förfrågningar som gjorts av andra användare i organisationen.

I följande avsnitt beskrivs aktiviteter som du kan utföra när du hanterar begäranden.

## Visa förfrågningar

Som standard kan du bara visa de förfrågningar du skapar, såvida inte användarna har valt att göra deras förfrågningar synliga för andra i organisationen (enligt beskrivningen i [Allmänna inställningar för begäran om Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md)). Systemadministratörer kan visa alla begäranden.

Så här visar du förfrågningar från Data Warehouse:

1. I Adobe Analytics: [!UICONTROL **verktyg**] > [!UICONTROL **Data Warehouse**].

   På sidan Data Warehouse visas alla förfrågningar som du har gjort. Data visas i varje kolumn. Du kan [konfigurera vilka kolumner](#configure-columns) är synliga.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Valfritt) Klicka på namnet på begäran för att visa en dialogruta med följande information: <!-- Check this -->

   * När en begäran började bearbetas

   * Begränsad hastighet: För många begäranden om Data Warehouse körs i organisationen. Begäran pausas tills andra dataförfrågningar har slutförts.

## Redigera begäranden

Tänk på följande när du redigerar begäranden:

* Endast begäranden som har konfigurerats för att köras enligt ett schema kan redigeras.

* Alla fält som är associerade med begäran kan inte redigeras. Fält som inte kan redigeras är nedtonade.

* Administratörer som redigerar en annan användares begäran måste välja ett nytt konto och en plats som de har åtkomst till.

Så här redigerar du en schemalagd begäran:

1. I Adobe Analytics: [!UICONTROL **verktyg**] > [!UICONTROL **Data Warehouse**].

1. Markera den begäran som du vill redigera på sidan Data Warehouse.

   ![Hantera en begäran](assets/dw-manage-request.png)

1. Välj [!UICONTROL **Redigera**].

1. Redigera begäran efter behov. Det går inte att redigera nedtonade konfigurationsalternativ.

   Information om varje konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Välj [!UICONTROL **Spara ändringar**].

## Visa historiken för en begäran

Du kan visa historiken för alla förfrågningar om Data Warehouse som du har gjort.

1. I Adobe Analytics: [!UICONTROL **verktyg**] > [!UICONTROL **Data Warehouse**].

1. På sidan Data Warehouse markerar du den begäran vars historik du vill visa.

   ![Hantera en begäran](assets/dw-manage-request.png)

1. Välj [!UICONTROL **Visa historik**].

   The [!UICONTROL **Visa begäran om Data Warehouse**] sidan visar en lista över enskilda rapportleveranser som är associerade med begäran.

   Välj **Konfigurera kolumn** icon ![Ikon för att konfigurera kolumner](assets/configure-column-icon.png) om du vill dölja kolumner eller visa kolumner som inte visas som standard.

   ![Historiksida för begäran](assets/dw-request-history.png)

   Följande kolumner är tillgängliga:

   | Kolumn | Beskrivning |
   |---------|----------|
   | [!UICONTROL **Skapad den**] | Datum och tid då rapporten skapades.<p>Detta visas i tidszonen för den användare som initierade begäran.</p> |
   | [!UICONTROL **Startdatum**] | Datum och tid då rapporten startades.<p>Detta visas i tidszonen för den användare som initierade begäran.</p> |
   | [!UICONTROL **Slutförd den**] | Datum och tid då rapporten slutfördes.<p>Detta visas i tidszonen för den användare som initierade begäran.</p> |
   | [!UICONTROL **Uppdaterat**] | Datum och tid då rapporten senast uppdaterades.<p>Detta visas i tidszonen för den användare som initierade begäran.</p> |
   | [!UICONTROL **Status**] | Status för rapportleveransen. Möjliga statusar är:<ul><li>[!UICONTROL **Skapad**]: Rapporten skapades men har ännu inte bearbetats.</li><li>[!UICONTROL **Väntande**]: Rapporten väntar på att bearbetas.</li><li>[!UICONTROL **Bearbetar**]: Rapporten bearbetas för närvarande.</li><li>[!UICONTROL **Slutförd**]: Rapporten har slutförts och är nu tillgänglig.</li><li>[!UICONTROL **Schemalagd**]: Rapporten är schemalagd men har inte startats ännu.</li><li>[!UICONTROL **Avbruten**]: Rapporten avbröts av användaren.</li><li>[!UICONTROL **Fel - Bearbetning**:] Rapporten påträffade ett fel och kunde inte bearbetas.</li><li>[!UICONTROL **Fel - det gick inte att skicka**]: Rapporten genererades men kunde inte levereras. Kontrollera [destinationskonfiguration](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)och skicka sedan rapporten igen.</li></ul>. |
   | [!UICONTROL **Från**] | Startdatumet för den övergripande tidsramen som ingår i rapporten.<p>Detta visas i rapportsvitens tidszon.</p> |
   | [!UICONTROL **Till**] | Slutdatumet för den övergripande tidsramen som ingår i rapporten. <p>Detta visas i rapportsvitens tidszon.</p> |
   | [!UICONTROL **ID för äldre begäran**] | Det ID som används för att identifiera en rapport i det äldre Datan Warehouse. Detta ID kan behövas när du kontaktar Adobe kundtjänst. |
   | [!UICONTROL **Rapport-ID**] | Det ID som används för att identifiera en rapport i det aktuella Datan Warehouse. Detta ID kan behövas när du kontaktar Adobe kundtjänst. |


1. Välj en rapportleverans och välj sedan något av följande alternativ:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Destinationsinformation**] | Visar konto- och platsinformation som är associerad med begäran. Det här är kontot och platsen som konfigurerades tidigare, enligt beskrivningen i [Konfigurera ett rapportmål för en Data Warehouse-begäran](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Avbryt rapport**] | Avbryter rapporten. Du kan inte avbryta rapporter som har statusen [!UICONTROL **Slutförd**] eller [!UICONTROL **Avbruten**]. |
   | [!UICONTROL **Kör rapporten igen**] | Kör rapporten igen med data som de var när den ursprungligen skickades. Du kan köra en rapport som har någon av följande statusar igen: [!UICONTROL **Avbruten**], [!UICONTROL **Slutförd**], [!UICONTROL **Fel - Bearbetning**], eller [!UICONTROL **Fel - det gick inte att skicka**]. |
   | [!UICONTROL **Skicka om rapport**] | Skickar rapportfilen som tidigare har skapats igen. Du kan skicka om en rapport som har någon av följande statusar: [!UICONTROL **Slutförd**] eller [!UICONTROL **Fel - det gick inte att skicka**]. |

## Kopiera begäranden

När du kopierar en begäran kopieras alla konfigurationsalternativ från den ursprungliga begäran.

1. I Adobe Analytics: [!UICONTROL **verktyg**] > [!UICONTROL **Data Warehouse**].

1. Markera den begäran du vill kopiera på sidan Data Warehouse.

   ![Hantera en begäran](assets/dw-manage-request.png)

1. Välj [!UICONTROL **Kopiera**].

   Sidan med begäran om att kopiera Data Warehouse visas. Alla konfigurationsalternativ kopieras från den ursprungliga begäran.

1. Uppdatera alla konfigurationsalternativ som är associerade med begäran.

   Information om varje konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Välj [!UICONTROL **Spara ändringar**].

## Avbryt begäranden

Endast begäranden som har konfigurerats för att köras enligt ett schema kan avbrytas.

Så här avbryter du en schemalagd begäran:

1. I Adobe Analytics: [!UICONTROL **verktyg**] > [!UICONTROL **Data Warehouse**].

1. Markera den begäran som du vill redigera på sidan Data Warehouse.

   ![Hantera en begäran](assets/dw-manage-request.png)

1. Välj [!UICONTROL **Avbryt**].

   Begäran kommer inte längre att köras vid den schemalagda tidpunkten.

## Konfigurera kolumner

Du kan konfigurera vilken information som ska visas för varje begäran genom att lägga till eller ta bort kolumner.

1. Välj **Konfigurera kolumner** i det övre högra hörnet på Datan Warehouse.

   ![Konfigurera kolumner](assets/dw-configure-columns.png)

   Följande kolumner är tillgängliga:

   | Tillgänglig kolumn | Beskrivning |
   |---------|----------|
   | Namn på begäran | Namnet på den person som skapade begäran. |
   | Rapportsvit | Rapportsviten som är associerad med begäran. |
   | Begärd av | Användaren som skapade begäran. |
   | Datum för förfrågan | Datumet då begäran gjordes. |
   | Status | Följande statusar är tillgängliga:<ul><li><p>**Slutförd**: Begäran har körts.</p></li><li><p>**Avbruten**: Begäran avbröts av användaren.</p></li><li><p>**Schemalagd**: Begäran är konfigurerad att köras enligt ett schema.</p></li><li><p>**Misslyckades**: Begäran kunde inte slutföras. Kontakta kundsupport om din begäran fortsätter att misslyckas.</p></li></ul> |

   {style="table-layout:auto"}

1. Kontrollera att alla kolumner som du vill visa är markerade. Markerade kolumner visas på Datan Warehouse och visar relevant information.

## Filtrera och sortera förfrågningar

1. Välj **Filter** ikonen till vänster på Datan Warehouse.

   ![Filterförfrågningar](assets/dw-filter.png)

1. Expandera [!UICONTROL **Rapportsviter**], [!UICONTROL **Ägare**], eller [!UICONTROL **Status**] väljer du sedan hur du vill filtrera förfrågningarna.

## Sök efter förfrågningar

1. I sökfältet högst upp på sidan Data Warehouse anger du det begärandenamn som du vill visa.

   Förfrågningar filtreras när du skriver.