---
description: För att bearbetningsreglerna ska kunna användas på ett effektivt sätt är det viktigt att förstå när de tillämpas under datainsamlingen.
subtopic: Processing rules
title: Bearbetningsordning
feature: Administratörsverktyg
uuid: cea01d13-dfd5-40f7-8b2f-b6e2fe8354df
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%

---

# Bearbetningsordning

För att bearbetningsreglerna ska kunna användas på ett effektivt sätt är det viktigt att förstå när de tillämpas under datainsamlingen.

![](assets/analytics_processing_order_test.png)

I följande tabeller visas de data som vanligtvis är tillgängliga före och efter att bearbetningsregler har tillämpats:

## Före bearbetning av regler

| Dimension | Beskrivning |
|--- |--- |
| Dynamisk variabelsökning | Variabler fylls i dynamiskt genom att information hämtas från HTTP-huvuden eller andra variabler. `s.eVar5="D=c1"` placerar till exempel värdet för prop1 i eVar5. |
| AppMeasurement | Funktioner och plugin-program som används i AppMeasurement körs i webbläsaren eller klientprogrammet. |
| Tagghantering | Regler som definieras i Adobe Launch eller Dynamic Tag Management körs enligt definition. |
| Punktregler | [Med ](/help/admin/admin/bot-removal/bot-rules.md) punktregler kan du ta bort trafik som genereras av kända spindlar och botar från rapportsviten. |

## Efter bearbetning av regler

| Dimension | Beskrivning |
|--- |--- |
| Data som lagts till av VISTA | Bearbetningsregler tillämpas före VISTA. |
| Besök sidnummer | Som en allmän regel är bearbetningsreglerna medvetna om de data som finns i den aktuella träffen. Besökssidnumret kompileras när bearbetningsreglerna har tillämpats. |
| Ren URL läggs till som sidnamn om det inte anges | När reglerna har bearbetats och VISTA har tillämpats läggs den rena URL:en till som sidnamn om inget sidnamn har angetts. Eftersom detta inträffar när bearbetningsregler har tillämpats rekommenderar vi att du lägger till ett villkor som kontrollerar om sidnamnet är tomt.  Om du kör rapporten Webbplatsinnehåll > Sidor och du ser https:// för sidnamn, är det troligtvis så att sidnamnet är tomt och URL:en används.  Du kan ställa in ett villkor för att testa om det finns ett tomt sidnamn eller för att testa om sidnamnet eller sidans URL innehåller ett visst värde. Sidnamnet kan sedan anges efter behov. |
| Bearbetningsregler för marknadsföringskanal | Du kan använda bearbetningsregler för att förbereda data för bearbetning med [Bearbetningsregler för marknadsföringskanaler](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-rules.html). |
| GEO-sökning | Detta inkluderar värdena för besökarstatus och postnummer för besökare. |
| eVars persistence | Varor som fanns i en tidigare träff bevaras inte för varje träff under regelbearbetningen. Endast eVars som har angetts för den aktuella träffen som bearbetas är tillgängliga. |

## Hur bearbetningsregler tillämpas när uppsatser kopieras med VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Om du har en VISTA-regel konfigurerad att kopiera träffar till en annan rapportsvit, skickas dessa träffar via eventuella bearbetningsregler som definieras i den andra rapportsviten.

Om du har definierat bearbetningsregler för den ursprungliga rapportsviten kan dessa tillämpas eller inte baserat på hur VISTA-regeln konfigurerades av Engineering Services. Om du vill veta mer kan du fråga din implementeringsspecialist om VISTA-regeln kopierar värdena för&quot;före&quot; eller&quot;efter&quot; till den extra rapportsviten. Om värdet &quot;pre&quot; kopieras, tillämpas inte bearbetningsregler som definierats i den ursprungliga rapportsviten. Om värdet &quot;post&quot; kopieras tillämpas bearbetningsreglerna innan träffen kopieras.
