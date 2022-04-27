---
description: Där bearbetningsregler finns i den övergripande dataflödet för Analytics.
subtopic: Processing rules
title: Bearbetningsordning
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 790c3a02fbdf896cba0933dcd7a2b2efd5a19f15
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%

---

# Bearbetningsordning

För att bearbetningsreglerna ska kunna användas på ett effektivt sätt är det viktigt att förstå när de tillämpas under datainsamlingen.

![Bearbetningsordning](assets/analytics_processing_order.png)

I följande tabeller visas de data som vanligtvis är tillgängliga före och efter att bearbetningsregler har tillämpats.

## Före bearbetning av regler

| Dimension | Beskrivning |
|--- |--- |
| [Dynamiska variabler](/help/implement/vars/page-vars/dynamic-variables.md) | Variabler som fylls i dynamiskt genom att hämta information från HTTP-huvuden eller andra variabler. |
| [AppMeasurement](/help/implement/home.md) | Funktioner och plugin-program som används i AppMeasurement-bibliotek körs i webbläsaren eller klientprogrammet. |
| [Taggimplementering](/help/implement/launch/overview.md) | Regler definierade i användargränssnittet för datainsamling. |
| [Webb-SDK för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/analytics-overview.html) | Data som samlas in via Web SDK skickas till Adobe Experience Edge och vidarebefordras till önskat rapportpaket. |
| [Punktregler](/help/admin/admin/bot-removal/bot-rules.md) | Gör att du kan ta bort trafik som genereras av kända spindlar och botar. |

## Efter bearbetning av regler

| Dimension | Beskrivning |
|--- |--- |
| Data som lagts till av VISTA | Bearbetningsregler tillämpas före VISTA. |
| Besök sidnummer | Bearbetningsreglerna är bara medvetna om de data som finns i den aktuella träffen. Besökssidnumret kompileras när bearbetningsreglerna har tillämpats. |
| Ren URL läggs till som sidnamn om det inte anges | När reglerna har bearbetats och VISTA har tillämpats läggs den rena URL:en till som sidnamn om inget sidnamn har angetts. Eftersom den här logiken används efter att bearbetningsregler har tillämpats rekommenderar Adobe att du lägger till ett villkor som kontrollerar om sidnamnet är tomt.  Om du kör **[!UICONTROL Site Content]** > **[!UICONTROL Pages]** Rapportera och du ser URL-värden för sidnamn. Det är troligt att sidnamnsvariabeln är tom.  Du kan ställa in ett villkor för att testa om sidan är tom eller för att testa om sidnamnet eller sidans URL innehåller ett visst värde. Sidnamnet kan sedan anges efter behov. |
| Bearbetningsregler för marknadsföringskanal | Du kan använda bearbetningsregler för att förbereda data för bearbetning av [Bearbetningsregler för marknadsföringskanal](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html). |
| GEO-sökning | Innehåller värdena för besökarstatus och besökarens postnummer. |
| eVars persistence | Varor som fanns i en tidigare träff bevaras inte för varje träff under regelbearbetningen. Endast eVars som har angetts för den aktuella träffen som bearbetas är tillgängliga. |

## Hur bearbetningsregler tillämpas vid kopiering av träffar med VISTA

Om du har en VISTA-regel konfigurerad att kopiera träffar till en annan rapportsvit, skickas dessa träffar via eventuella bearbetningsregler som definieras i den andra rapportsviten.

Om du har definierat bearbetningsregler för den ursprungliga rapportsviten kan dessa regler tillämpas eller inte baserat på hur VISTA-regeln konfigurerades av Engineering Services. Om du vill veta mer kan du fråga din implementeringsspecialist om VISTA-regeln kopierar värdena för&quot;före&quot; eller&quot;efter&quot; till den extra rapportsviten. Om värdet &quot;pre&quot; kopieras, tillämpas inte bearbetningsregler som definierats i den ursprungliga rapportsviten. Om värdet &quot;post&quot; kopieras tillämpas bearbetningsreglerna innan träffen kopieras.
