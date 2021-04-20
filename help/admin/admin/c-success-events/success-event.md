---
description: Success-händelser är åtgärder som kan spåras. Du avgör vilken händelse som lyckas. Om en besökare till exempel köper ett objekt kan köphändelsen betraktas som lyckad händelse.
keywords: event
title: Översikt över slutförda händelser
feature: Admin Tools
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 4%

---

# Översikt över slutförda händelser

Success-händelser är åtgärder som kan spåras. Du avgör vilken händelse som lyckas. Om en besökare till exempel köper ett objekt kan köphändelsen betraktas som lyckad händelse.

Gå till sidan Success Events i inställningarna för rapportsviten:

1. Logga in på [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) med dina inloggningsuppgifter för AdobeID.
2. Klicka på knappen med nio rutnät längst upp och klicka sedan på [!UICONTROL Analytics].
3. Navigera till [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. Välj önskad rapportsvit och navigera sedan till [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Success Events].
5. Leta reda på önskad händelse och ändra listrutan [!UICONTROL Unique Event Recording] till [!UICONTROL Record Once Per Visit] eller [!UICONTROL Use Event ID].

Det finns många typer av framgångsrika händelser, beroende på webbplatstypen. Flera exempel:

* **Detaljhandel**: Produktvy, utcheckning, inköp
* **Media**: Prenumeration, tävlingsregistrering, sidvy, videovy
* **Ekonomi**: Inlämning av ansökningar, inloggning, användning av självbetjäningsverktyg
* **Resa**: Bokning (inköp), intern kampanj (klickning), sökning (tidsaxel för prissättning)
* **Telekommunikation**: Inköp, leads, användning av självbetjäningsverktyg
* **Högteknologi**: Nedladdning av rapporter, offertförfrågan, ifyllnad av formulär, supportförfrågningar
* **Bilar**: Leadinlämning, anbudsförfrågan, nedladdning av broschyrer

Variabeln [s.events](https://docs.adobe.com/content/help/sv-SE/analytics/implementation/vars/page-vars/events/event-serialization.html) definierar en success-händelse.

## Sidan Slutförda händelser - beskrivningar {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** >  **[!UICONTROL Admin]** >  **[!UICONTROL Report Suites]** >  **[!UICONTROL Edit Settings]** >  **[!UICONTROL Conversion]** >  **[!UICONTROL Success Events]**

På sidan Success Events kan du konfigurera de händelsevariabler som används på din plats. Du kan lägga till upp till 1 000 lyckade händelser. Händelser 81-1 000 fungerar bara om H22-koden eller senare används.

| Element | Beskrivning |
|--- |--- |
| Händelse | Händelsens ursprungliga namn. |
| Namn | Ge meningsfulla namn till de framgångshändelser som används på er webbplats. Om till exempel event1 används för att spåra registreringar, ändrar du namnet här så att event1 representeras som mätvärdet för &quot;Registreringar&quot; i alla konverteringsrapporter. |
| Typ | Den valda typen avgör om händelsen är en räknarhändelse (standard), numerisk händelse eller valutakurs. Numeriska händelser och valutakurshändelser gör att du kan öka måtten med mer än en.  Räknarhändelser används för att spela in en händelse i tid, medan valutahändelser spelar in ett decimaltal, som moms eller frakt. Det värde som skickas till valutakurshändelser konverteras från sidvalutan till rapportsvitens basvaluta vid inleverans. Mer information om hur du använder valutakurser får du om du kontaktar en Adobe-representant. Numeriska händelser används för att rapportera icke-valutanummer, t.ex. antalet kuponger som används i en order. Valutahändelser används för att spåra moms och fraktkostnader. Händelser som används i standardtypen för datakällor måste vara numeriska händelser eller valutakurshändelser. |
| Polaritet | Med hjälp av metrisk polaritet kan du ange om Adobe Analytics ska se det som bra eller dåligt om en viss anpassad händelse (metrisk) inträffar. Det gör att Adobe Analytics kan visa riktningsvisare (pilar) för olika mätvärden för att lägga till kontext (t.ex. vecka för vecka-jämförelser).  Exempel: Om&quot;Buggar som skickats&quot; går upp vecka för vecka, ska Adobe Analytics se det bra eller dåligt? En ökning av antalet e-postregistreringar är förmodligen bra. Men en ökning av antalet inskickningsfel i formulär är antagligen felaktig.  I Analysis Workspace tillämpas polaritet på Villkorsstyrd formatering av friformstabell, visualiseringar av sammanfattningsändringar och färgschemat Positive/Negative för mappningsvisualisering. |
| Beskrivning | En kort beskrivning av evenemangets syfte och användning. |
| Unik händelseinspelning | **Registrera en gång per besök**: Kopplar den angivna händelsen till besökarens session. Efterföljande antal till en viss händelse i samma besök ignoreras. Den här typen av händelseserialisering kräver inga implementeringsändringar.<br>**Använd händelse-ID**: Kopplar den angivna händelsen till ett anpassat ID. Efterföljande antal till en viss händelse med samma händelse-ID ignoreras. Den här typen av händelseserialisering kräver ett anpassat ID i träffar för att dubblettvärden ska kunna tas bort. Se [Serialisering av händelse-ID](../../../implement/vars/page-vars/events/event-serialization.md) i Användarhandboken för implementering. |
| Deltagande | Ger fullständig attribueringskreditering till alla dimensionsobjekt i besöket. |
| Varning (valutakändelse) | När händelsetyper ändras till eller från en valutakurs visas ett meddelande om att historiska data inte är tillgängliga i rapporter.  Olika händelsetyper använder separata datatabeller och kan inte användas samtidigt. Vissa historiska data kan återställas om användaren återställer händelsetypen. Data som samlats in efter den första ändringen är dock inte tillgängliga. Var försiktig när du ändrar en händelsetyp. |
