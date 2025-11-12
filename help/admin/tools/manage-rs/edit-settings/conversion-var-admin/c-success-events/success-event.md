---
description: Success-händelser är åtgärder som kan spåras. Du avgör vilken händelse som lyckas. Om en besökare till exempel köper ett objekt kan köphändelsen betraktas som en lyckad händelse.
keywords: event
title: Success events overview
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 1%

---

# Slutförda händelser

Slutförda händelser (kallas även konverteringshändelser eller anpassade händelser) är åtgärder som kan spåras. Du avgör vilken händelse som lyckas. Om en besökare till exempel köper ett objekt kan köphändelsen betraktas som en lyckad händelse.

En videoöversikt över lyckade händelser finns i [Introduktion till konverteringshändelser](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events) i självstudiekurserna för Analytics.

## Exempel på lyckade händelser

Det finns många typer av framgångsrika händelser, beroende på webbplatstypen. Flera exempel:

* **Detaljhandel**: Produktvy, utcheckning, köp
* **Media**: Prenumeration, tävlingsregistrering, sidvy, videovy
* **Ekonomi**: Användning av program, inloggning och självbetjäningsverktyg
* **Resa**: Bokning (inköp), intern kampanj (klickning), sökning (tidsaxel för prissättning)
* **Telekommunikation**: Inköp, leads och självbetjäningsverktyg
* **Högteknologi**: Hämta rapport, offert, ifyllnad av formulär, supportförfrågningar
* **Automatisering**: Leadsändning, anbudsförfrågan, broschyrenedladdning

Variabeln [s.events](/help/implement/vars/page-vars/events/event-serialization.md) definierar en success-händelse.

## Konfigurera lyckade händelser

Du kan konfigurera de händelsevariabler som används på platsen. Du kan lägga till upp till 1 000 lyckade händelser. Händelser 81-1 000 fungerar bara om du använder H22-kod eller högre.

Så här konfigurerar du lyckade händelser:

1. I Adobe Analytics väljer du **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj den rapportsvit där du vill konfigurera lyckade händelser.
1. Välj **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Stegresultat](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Identifiera namnet på händelsen som du vill använda som en lyckad händelse i kolumnen [!UICONTROL **Händelse**].

1. Markera kryssrutan bredvid objektet i kolumnen **[!UICONTROL Name]** om du vill aktivera redigering och ange sedan önskat namn.

   Ge meningsfulla namn till de framgångshändelser som används på er webbplats. Om till exempel event1 används för att spåra registreringar, ändrar du namnet här så att event1 representeras som mätvärdet för &quot;Registreringar&quot; i alla konverteringsrapporter.

1. Markera kryssrutan bredvid objektet i kolumnen **[!UICONTROL Type]** för att aktivera listrutan och välj sedan önskad typ.

   >[!IMPORTANT]
   >
   >Tänk på följande när du ändrar händelsetypen:<ul><li>Du kan ändra händelsetypen mellan räknare och numerisk utan att förlora åtkomsten till tidigare hämtade data.</li><li>När händelsetyper ändras till eller från en valutakurs visas ett meddelande om att historiska data inte är tillgängliga i rapporter. Olika händelsetyper använder separata datatabeller och kan inte användas samtidigt. Vissa historiska data kan återställas om användaren återställer händelsetypen. Data som samlats in efter den första ändringen är dock inte tillgängliga.</li></ul>

   Den typ du väljer avgör om händelsen är en räknarhändelse (standard), numerisk händelse eller valutakurs. <p>Räknarhändelser används för att spela in en händelse i tid.</p><p>Numeriska händelser används för att rapportera icke-valutanummer, t.ex. antalet kuponger som används i en order.</p> <p>Valutahändelser registrerar ett decimaltal, som moms eller frakt. Det värde som skickas till valutakurshändelser konverteras från sidvalutan till rapportsvitens basvaluta vid inleverans. Valutahändelser används för att spåra moms och fraktkostnader. Kontakta en Adobe-representant om du vill ha mer information om hur du använder valutasändningar.<p>Numeriska händelser och valutakurshändelser gör att du kan öka måtten med mer än en.</p><p>Händelser som används i standardtypen för datakällor måste vara numeriska händelser eller valutakurshändelser.</p>

1. Markera kryssrutan i kolumnen **[!UICONTROL Polarity]** och välj sedan i listrutan om en uppåtgående trend för det här måttet är bra eller dåligt.

   detta gör att du kan ange om Adobe Analytics ska anse det vara bra eller dåligt om en viss anpassad händelse (mått) inträffar. Det aktiverar riktningsvisare (pilar) för olika mätvärden för att lägga till kontext (till exempel vecka över vecka-jämförelser).  Exempel: Om &quot;Buggar som skickas&quot; går upp vecka för vecka, ska Adobe Analytics se det bra eller dåligt ut? En ökning av antalet e-postregistreringar är förmodligen bra. Men en ökning av antalet inskickningsfel i formulär är antagligen felaktig.  I Analysis Workspace tillämpas polaritet på: Villkorlig formatering av friformstabell, visualisering av sammanfattningsändring och det positiva/negativa färgschemat för mappningsvisualisering.

1. Markera kryssrutan i kolumnen **[!UICONTROL Visibility]** och välj sedan i listrutan om du vill dölja standardmått (inbyggda), anpassade händelser och inbyggda händelser i menyn, metrisk väljare, beräkningsmetrisk byggare och segmentbyggare.

   Den här inställningen påverkar inte datainsamlingen för det måttet eller händelsen. Den påverkar bara dess synlighet i användargränssnittet enligt följande:

   Följande inställningar är tillgängliga:

   | Inställning | Synlig i | Inte synlig i |
   |---------|----------|---------|
   | [!UICONTROL **Visas överallt**] | <ul><li>Analysis Workspace</li><li>Segment Builder</li><li>Beräknad metrisk Builder</li></ul> | Ej tillämpligt |
   | [!UICONTROL **Builders**] | <ul><li>Segment Builder</li><li>Beräknad metrisk Builder</li><li>Analysis Workspace</li></ul> |  |
   | [!UICONTROL **Dold överallt**] | Ej tillämpligt | <ul><li>Analysis Workspace</li><li>Segment Builder</li><li>Beräknad metrisk Builder</li></ul> |

1. Markera kryssrutan i kolumnen [!UICONTROL **Beskrivning**] och ange sedan en beskrivning.
1. I kolumnen [!UICONTROL **Unik händelseinspelning**] markerar du kryssrutan och väljer sedan i listrutan om händelsen alltid ska spelas in.

   Följande alternativ är tillgängliga:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Spela in en gång per besök**] | Kopplar den angivna händelsen till besökarens session. Efterföljande antal till en viss händelse i samma besök ignoreras. Den här typen av händelseserialisering kräver inga implementeringsändringar. |
   | [!UICONTROL **Använd händelse-ID**] | Kopplar den angivna händelsen till ett anpassat ID. Efterföljande antal till en viss händelse med samma händelse-ID ignoreras. Den här typen av händelseserialisering kräver ett anpassat ID i träffar för att dubblettvärden ska kunna tas bort. Se [Serialisering av händelse-ID](/help/implement/vars/page-vars/events/event-serialization.md) i användarhandboken för Implementering. |

1. Markera kryssrutan i kolumnen [!UICONTROL **Deltagande**] och välj sedan om du vill aktivera eller inaktivera deltagande. När det är aktiverat ger det fullständig attribueringskreditering till alla dimensionsobjekt i besöket.

   >[!NOTE]
   >
   >Du kan aktivera deltagande för upp till 100 anpassade händelser. Utöver detta kan du skapa deltagandemått i [Calculated Metrics](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)-byggaren.

1. Välj **[!UICONTROL Save]**.
