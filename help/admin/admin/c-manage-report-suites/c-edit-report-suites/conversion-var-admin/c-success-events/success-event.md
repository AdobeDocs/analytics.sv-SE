---
description: Success-händelser är åtgärder som kan spåras. Du avgör vilken händelse som lyckas. Om en besökare till exempel köper ett objekt kan köphändelsen betraktas som en lyckad händelse.
keywords: event
title: Success events overview
feature: Event
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# Success events overview

Slutförda händelser (kallas även konverteringshändelser eller anpassade händelser) är åtgärder som kan spåras. Du avgör vilken händelse som lyckas. Om en besökare till exempel köper ett objekt kan köphändelsen betraktas som en lyckad händelse.

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/28764/?quality=12)

Gå till sidan Success Events i inställningarna för rapportsviten:

1. Logga in på [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) med dina inloggningsuppgifter för AdobeID.
2. Klicka på knappen med nio stödraster längst upp och klicka sedan på [!UICONTROL Analytics].
3. Navigera till [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. Välj önskad rapportsvit och navigera sedan till [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Success Events].

Det finns många typer av framgångsrika händelser, beroende på webbplatstypen. Flera exempel:

* **Detaljhandel**: Produktvy, utcheckning, köp
* **Media**: Prenumeration, tävlingsregistrering, sidvy, videovy
* **Ekonomi**: Användning av program, inloggning och självbetjäningsverktyg
* **Resa**: Bokning (inköp), intern kampanj (klickning), sökning (tidsaxel för prissättning)
* **Telekommunikation**: Inköp, leads och självbetjäningsverktyg
* **Högteknologi**: Hämta rapport, offert, ifyllnad av formulär, supportförfrågningar
* **Automatisering**: Leadsändning, anbudsförfrågan, broschyrenedladdning

Variabeln [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html) definierar en success-händelse.

## Händelsesida - beskrivningar {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**

På sidan Success Events kan du konfigurera de händelsevariabler som används på din plats. Du kan lägga till upp till 1 000 lyckade händelser. Händelser 81-1 000 fungerar bara om H22-koden eller senare används.

| Element | Beskrivning |
|--- |--- |
| Händelse | Händelsens ursprungliga namn. |
| Namn | Ge meningsfulla namn till de framgångshändelser som används på er webbplats. Om till exempel event1 används för att spåra registreringar, ändrar du namnet här så att event1 representeras som mätvärdet för &quot;Registreringar&quot; i alla konverteringsrapporter. |
| Typ | Den valda typen avgör om händelsen är en räknarhändelse (standard), numerisk händelse eller valutakurs. Numeriska händelser och valutakurshändelser gör att du kan öka måtten med mer än en.  Räknarhändelser används för att spela in en händelse i tid, medan valutahändelser spelar in ett decimaltal, som moms eller frakt. Det värde som skickas till valutakurshändelser konverteras från sidvalutan till rapportsvitens basvaluta vid inleverans. Mer information om hur du använder valutakurser får du om du kontaktar en Adobe-representant. Numeriska händelser används för att rapportera icke-valutanummer, t.ex. antalet kuponger som används i en order. Valutahändelser används för att spåra moms och fraktkostnader. Händelser som används i standardtypen för datakällor måste vara numeriska händelser eller valutakurshändelser. |
| Polaritet | Med hjälp av metrisk polaritet kan du ange om Adobe Analytics ska se det som bra eller dåligt om en viss anpassad händelse (metrisk) inträffar. Det gör att Adobe Analytics kan visa riktningsvisare (pilar) för olika mätvärden för att lägga till kontext (t.ex. vecka för vecka-jämförelser).  Exempel: Om &quot;Buggar som skickas&quot; går upp vecka för vecka, ska Adobe Analytics se det bra eller dåligt ut? En ökning av antalet e-postregistreringar är förmodligen bra. Men en ökning av antalet inskickningsfel i formulär är antagligen felaktig.  I Analysis Workspace tillämpas polaritet på: Villkorlig formatering av friformstabell, visualisering av sammanfattningsändring och det positiva/negativa färgschemat för mappningsvisualisering. |
| Beskrivning | En kort beskrivning av evenemangets syfte och användning. |
| Unik händelsinspelning | **Spela in en gång per besök**: Kopplar den angivna händelsen till besökarens session. Efterföljande antal till en viss händelse i samma besök ignoreras. Den här typen av händelseserialisering kräver inga implementeringsändringar.<br>**Använd händelse-ID**: Kopplar den angivna händelsen till ett anpassat ID. Efterföljande antal till en viss händelse med samma händelse-ID ignoreras. Den här typen av händelseserialisering kräver ett anpassat ID i träffar för att dubblettvärden ska kunna tas bort. Se [Serialisering av händelse-ID](/help/implement/vars/page-vars/events/event-serialization.md) i användarhandboken för Implementering. |
| deltagande | Ger fullständig attribueringskreditering till alla dimensionsobjekt i besöket. |
| Varning (valutakändelse) | När händelsetyper ändras till eller från en valutakurs visas ett meddelande om att historiska data inte är tillgängliga i rapporter.  Olika händelsetyper använder separata datatabeller och kan inte användas samtidigt. Vissa historiska data kan återställas om användaren återställer händelsetypen. Data som samlats in efter den första ändringen är dock inte tillgängliga. Var försiktig när du ändrar en händelsetyp. |
