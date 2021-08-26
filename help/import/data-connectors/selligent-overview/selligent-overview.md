---
description: Använd Selligent-dataanslutningen med Adobe Analytics.
title: Selligent Data Connector för Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
exl-id: baeabd9c-10bc-4733-8779-abfa81807c54
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 2%

---

# Selligent Data Connector för Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Adobe Data Connector-tekniken upphör den 1 augusti 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

Integreringen innehåller följande viktiga fördelar:

* Samla marknadsförings- och analysdata via e-post i ett enda rapporteringsgränssnitt.
* Optimera e-postkampanjer genom konvertering och bidrag till intäkter och webbplatsens framgång.
* Återmarknadsför till viktiga besökare och marknadssegment baserat på dynamiska marknadsföringssegment.

## Dynamiska marknadsföringssegment {#section-a2216f3339304636bd5417249bd635a4}

Den här e-postintegreringen stöder dynamiska marknadsföringssegment som hjälper er att utveckla verksamheten. Den här integreringen innehåller följande marknadsföringssegment:

| Segment | Beskrivning |
|---|---|
| **Cart Abandonation Profile** | Hjälp besökarna att konvertera till kunder med finjusterade kampanjer som är särskilt utformade för dem som tvekar att slutföra kundvagnen. |
| **Inköpsprofil** | Öka antalet upprepade order och det genomsnittliga ordervärdet genom kampanjer riktade mot besökares inköpsmönster. |
| **Beteendeprofil för produkt-/innehållsvy** | Nå potentiella kunder genom marknadsföringssegment baserat på produktvisningar och profiler för innehållsåtkomst. |
| **Anpassade segment för återmarknadsföring** | Kunderna kan också skapa och schemalägga anpassade segment för ny marknadsföring som är specifika för användarnas behov. |

## Innan du aktiverar den här integreringen{#before-you-activate-this-integration}

Innan du aktiverar integreringen bör du granska följande objekt mot dina distributioner av Adobe Analytics och ditt e-postprogram.

På så sätt säkerställs att bästa praxis och krav finns innan aktiveringen. Detta resulterar i en optimal och lyckad integrering.

## Krav för Adobe Analytics{#prerequisites-for-adobe-analytics}

Här listas de åtgärder som krävs för att genomföra Adobe Analytics innan du kan distribuera integreringen.

| Förutsättning | Anteckningar |
|---|---|
| Välj Report Suite | Observera att den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen. |
| Konfigurera analysvariabler | Den här integreringen kräver anpassade händelser och anpassade eVars-variabler, samt eventuellt ytterligare händelser och ytterligare eVars-variabler. Se Konfigurera analysvariabler för Selligent. |
| Auktoriserad representant | Observera att aktiveringen av den här integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobe tillförlitliga partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan. |
| Aktivera Adobe Data warehouse™ | Denna integrering kräver att Data warehouse är aktiverat för att generera segment för återmarknadsföring. Om du inte har aktiverat Adobe Data warehouse kontaktar du Adobe för mer information. |
| Mottagar-ID | Integreringen kräver att vi hämtar och lagrar ett besökar-ID i en Analytics-variabel (eVar). Besökar-ID:t (kallas ofta för mottagar-ID) är en kodad eller numerisk representation av en e-postadress från Selligent-systemet. Detta&quot;Mottagar-ID&quot; är kopplat till besökarbeteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som återförs till Selligent-systemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden. |
| Extern spårning | Om du för närvarande inte följer den bästa metoden att aktivera extern spårning för varje e-postkampanj som du skickar måste du göra det för att integreringen ska lyckas. Mer information finns i avsnittet Selligent nedan. |
| Integritetsefterlevnad | Genom att aktivera spårning av mottagare eller besökar-ID kan den här funktionen spåra personligt identifierbar information om webbplatsens besökare. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke. |

## Konfigurera analysvariabler för Selligent{#configure-analytics-variables-for-selligent}

Den här integreringen kräver att 2 eVars reserveras för varje implementering av rapportsviten.

Förutom dessa eVars kan ett antal händelser reserveras beroende på data från Selligent, som du vill se i Analytics. Dessa eVars och händelser beskrivs nedan:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabeltyp </th> 
   <th colname="col2" class="entry"> Variabelnamn </th> 
   <th colname="col3" class="entry"> Hur det används </th> 
   <th colname="col4" class="entry"> Inställningar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Meddelande-ID </td> 
   <td colname="col3"> Om du vill fånga upp den enskilda e-postmeddelandekampanjens identifiering. </td> 
   <td colname="col4"> <p><b>Status</b>: Aktiverad </p> <p><b>Allokering</b>: Senaste </p> <p><b>Förfaller efter</b>: "Affärsbeslut" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Mottagar-ID </td> 
   <td colname="col3"> Om du vill samla in den anonyma identifieringen för den kund som klickade på e-postkampanjen. </td> 
   <td colname="col4"> <p><b>Status</b>: Aktiverad </p> <p><b>Allokering</b>: Senaste </p> <p><b>Förfaller efter</b>: "Affärsbeslut" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Skickat </td> 
   <td colname="col3"> Om du vill lagra antalet e-postmeddelanden som skickas från Selligent. </td> 
   <td colname="col4"> <p><b>Typ</b>: Numeriskt </p> <p><b>Deltagande</b>: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Levererat </td> 
   <td colname="col3"> För att lagra antalet e-postmeddelanden som levererats. </td> 
   <td colname="col4"> <p><b>Typ</b>: Numeriskt </p> <p><b>Deltagande</b>: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Vyer </td> 
   <td colname="col3"> För att lagra antalet unika e-postmeddelanden som visats. </td> 
   <td colname="col4"> <p><b>Typ</b>: Numeriskt </p> <p><b>Deltagande</b>: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Klickningar </td> 
   <td colname="col3"> Om du vill lagra antalet gånger som någon klickar på ett e-postmeddelande. </td> 
   <td colname="col4"> <p><b>Typ</b>: Numeriskt </p> <p><b>Deltagande</b>: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Studsade </td> 
   <td colname="col3"> Om du vill lagra antalet e-postmeddelanden som studsade. </td> 
   <td colname="col4"> <p><b>Typ</b>: Numeriskt </p> <p><b>Deltagande</b>: Aktiverad </p> </td> 
  </tr> 
 </tbody> 
</table>

## Krav för Selligent{#prerequisites-for-selligent}

Visar den information som krävs för att tillhandahålla från ditt Selligent-konto innan du kan distribuera integreringen.

**Giltigt marginalkonto**

För att kunna använda den här integreringen av Data Connectors måste du ha ett giltigt Selligent-konto.

**Kontoinformation**

Du behöver följande information om ditt Selligent-konto under den här integrationsinställningen:

* **Adobe-tjänst-URL**:

   URL:en kan härledas från den URL som används för att logga in på Selligent Marketing-lösningen. Ersätt&quot;/simweb/login.aspx&quot; del av URL:en med&quot;/automation/omniture.asmx&quot;

   Exempel: `https://<client-specific install url>/automation/omniture.asmx`

* **Frågesträngsparametrar:** Dessa läggs till i startsidans URL för meddelande-ID och mottagar-ID (Visitor-ID). Dessa är alltid MID och RID för meddelande-ID respektive mottagar-ID.

* **Integrationstoken** Starta hanterarverktyget inifrån Simweb och gå till  **[!UICONTROL Configuration]** >  **[!UICONTROL System Settings]** >  **[!UICONTROL General]** tab >  **[!UICONTROL System]**. Under **[!UICONTROL Security]** hittar du integreringstoken.

   ![](assets/selligent-integration_token.png)
