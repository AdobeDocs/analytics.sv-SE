---
description: Med hjälp av data i etikettrapportsviten kan du tilldela etiketter för identiteter, känslighet och datastyrning till varje variabel i en viss rapportsvit.
title: Data i etikettrapportsvit
feature: Data Governance
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
source-git-commit: c774d05ca3b1f9f45ec118b0e7b8a839a03b87e3
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 28%

---

# Data i etikettrapportsvit

Med hjälp av data i etikettrapportsviten kan du tilldela etiketter för identiteter, känslighet och datastyrning till varje variabel i en viss rapportsvit. Försäkra dig om att du först bekanta dig med [etiketter och definitioner](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

>[!NOTE]
>
>Kom ihåg att etikettering måste granskas varje gång en ny rapportsvit skapas eller när en ny variabel aktiveras i en befintlig rapportsvit. Du kan också behöva granska etiketteringen när nya lösningar är aktiverade, eftersom de kan visa nya variabler som kan kräva etiketter. En återimplementering av dina mobilappar eller webbplatser kan ändra hur befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketter.

## Tilldela eller redigera sekretessetiketter för rapportsviten {#assign-edit}

**Exempel**: Som Data Controller planerar du att samla in e-postadresser och cookie-ID:n från registrerade för att bearbeta deras förfrågningar om dataintegritet. Dessa cookie-ID:n lagras i en rapportsvit i Adobe Analytics.

1. I Adobe Analytics navigerar du till **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Data governance]**.

   ![Sekretessmärkning](assets/privacy_rs_settings.png)

1. Välj en rapportsvit på **[!UICONTROL Report Suites]** överst.

1. I filteravsnittet till vänster väljer du vilka variabelgrupper du vill etikettera. Du kan bara märka en grupp med variabler åt gången.

   * **Standardkomponenter** - Standardkomponenter är färdiga analysmått och analysvärden som samlas in som standard i en Analytics-implementering.
   * **Konverteringsvariabler** - Custom Insight Conversion Variable (eller eVar) placeras i Adobe-koden på vissa webbsidor på webbplatsen. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. En eVar kan besöksbaserat och fungera på liknande sätt som cookies. Värden som skickas till eVar följer användaren under en förbestämd tidsperiod.
   * **Listvariabler** - Listvariabler är anpassade variabler som du kan använda hur du vill. De fungerar på liknande sätt som eVars, förutom att de kan innehålla flera värden i samma träff. Listvariabler har ingen teckengräns.
   * **Trafikvariabler** - Med Custom Insight Traffic Variables (eller props) kan du korrelera anpassade data med specifika trafikrelaterade händelser. Propvariablerna är inbäddade i implementeringskoden på varje sida på webbplatsen.
   * **Success Events** - Framgångshändelser (kallas även konverteringshändelser eller anpassade händelser) är åtgärder som kan spåras. Du avgör vilken händelse som lyckas. Om en besökare till exempel köper ett objekt kan köphändelsen betraktas som lyckad händelse.
   * **Klassificeringar** - Klassificeringsindelningar används för att mappa analysrapporteringsdata till relaterade egenskaper. Klassificeringar kan användas för en mängd olika syften, men används oftast för att klassificera kampanjspårningskoder (både interna och externa) och produkt-ID:n.

1. Markera en variabel genom att markera dess kryssruta och sedan klicka på **[!UICONTROL Edit Privacy Labels]** på det blå fält som visas längst ned på skärmen.

   ![Redigera](assets/edit-label.png)

   På den här skärmen visas de etiketter som används och du kan använda ytterligare etiketter. Du kanske inte kan använda eller ändra alla etiketter, beroende på vilken komponent det är.

   ![Använda etiketter](assets/edit-labels2.png)

1. Klicka på **[!UICONTROL Apply]** när du är klar med alla etiketter.

