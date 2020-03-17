---
description: För att bearbetningsreglerna ska kunna användas på ett effektivt sätt är det viktigt att förstå när de tillämpas under datainsamlingen.
subtopic: Processing rules
title: Bearbetningsordning
topic: Admin tools
uuid: cea01d13-dfd5-40f7-8b2f-b6e2fe8354df
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Bearbetningsordning

För att bearbetningsreglerna ska kunna användas på ett effektivt sätt är det viktigt att förstå när de tillämpas under datainsamlingen.

![](assets/analytics_processing_order_test.png)

I följande tabeller visas de data som vanligtvis är tillgängliga före och efter att bearbetningsregler har tillämpats:

## Före bearbetning av regler

| Dimension | Beskrivning |
|--- |--- |
| Dynamisk variabelsökning | Variabler fylls i dynamiskt genom att information hämtas från HTTP-huvuden eller andra variabler. Till exempel `s.eVar5="D=c1"` placeras värdet för prop1 i eVar5. |
| AppMeasurement | Funktioner och plugin-program som används i AppMeasurement körs i webbläsaren eller klientprogrammet. |
| Dynamisk tagghantering | Regler som definieras i Dynamic Tag Management körs enligt definition. |
| Punktregler | [Med punktregler](/help/admin/admin/bot-removal/bot-rules.md) kan du ta bort trafik som genereras av kända spindlar och botar från rapportsviten. |

## Efter bearbetning av regler

| Dimension | Beskrivning |
|--- |--- |
| Data som lagts till av VISTA | Bearbetningsregler tillämpas före VISTA. |
| Besök sidnummer | Som en allmän regel är bearbetningsreglerna medvetna om de data som finns i den aktuella träffen. Besökssidnumret kompileras när bearbetningsreglerna har tillämpats. |
| Ren URL läggs till som sidnamn om det inte anges | När reglerna har bearbetats och VISTA har tillämpats läggs den rena URL:en till som sidnamn om inget sidnamn har angetts. Eftersom detta inträffar när bearbetningsregler har tillämpats rekommenderar vi att du lägger till ett villkor som kontrollerar om sidnamnet är tomt.  Om du kör rapporten Webbplatsinnehåll > Sidor och du ser https:// för sidnamn, är det troligtvis så att sidnamnet är tomt och URL:en används.  Du kan ställa in ett villkor för att testa om det finns ett tomt sidnamn eller för att testa om sidnamnet eller sidans URL innehåller ett visst värde. Sidnamnet kan sedan anges efter behov. |
| Bearbetningsregler för marknadsföringskanal | Du kan använda bearbetningsregler för att förbereda data för bearbetning enligt [reglerna](https://marketing.adobe.com/resources/help/en_US/mchannel/c_rules.html)för bearbetning av marknadsföringskanaler. |
| GEO-sökning | Detta inkluderar värdena för besökarstatus och postnummer för besökare. |
| eVars persistence | Varor som fanns i en tidigare träff bevaras inte för varje träff under regelbearbetningen. Endast eVars som har angetts för den aktuella träffen som bearbetas är tillgängliga. |

## Hur bearbetningsregler tillämpas vid kopiering av träffar med VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Om du har en VISTA-regel konfigurerad att kopiera träffar till en annan rapportsvit, skickas träffar via eventuella bearbetningsregler som har definierats i den andra rapportsviten.

Om du har definierat bearbetningsregler för den ursprungliga rapportsviten kan dessa tillämpas eller inte baserat på hur VISTA-regeln konfigurerades av Engineering Services. Om du vill veta mer kan du fråga din implementeringsspecialist om VISTA-regeln kopierar värdena för&quot;före&quot; eller&quot;efter&quot; till den extra rapportsviten. Om värdet &quot;pre&quot; kopieras, tillämpas inte bearbetningsregler som definierats i den ursprungliga rapportsviten. Om värdet &quot;post&quot; kopieras tillämpas bearbetningsreglerna innan träffen kopieras.
