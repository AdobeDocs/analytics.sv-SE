---
description: Med Bot Rules kan du ta bort trafik som genereras av kända spindlar och botar från rapportsviten. Genom att ta bort robottrafiken kan du få ett mer exakt mått på användaraktiviteten på din webbplats.
subtopic: Bot rules
title: Bot Rules - översikt
feature: Administratörsverktyg
uuid: 3cb9e29d-1c37-43de-b7ac-34441093a60e
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 0%

---

# Bot Rules - översikt

Med Bot Rules kan du ta bort trafik från rapportsviten som genereras av kända spindlar och botar. Genom att ta bort robottrafiken kan du få ett mer exakt mått på användaraktiviteten på din webbplats.

När båda reglerna har definierats jämförs all inkommande trafik med de definierade reglerna. Trafik som uppfyller någon av dessa regler samlas inte in i rapportsviten och ingår inte i trafikmätningarna.

Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** om du vill uppdatera eller överföra båda reglerna. Välj rätt Report Suite och gå sedan till **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.

Att ta bort robottrafik minskar vanligen mängden trafik och konverteringsmått. Många kunder tycker att om man tar bort både trafik ökar konverteringsgraden och ökar användbarheten. Innan du tar bort robottrafiken ska du kommunicera med intressenter för att se till att de kan göra de nödvändiga justeringarna av viktiga prestandaindikatorer som ett resultat av denna förändring. Om det är möjligt rekommenderar vi att man först tar bort både robottrafiken från ett litet rapporteringsprogram för att uppskatta den potentiella effekten.

Punkttrafikdata lagras i en separat databas för visning i rapporter om start- och startsidor. Det finns två alternativ för aktivering av robotfiltrering:

| Regeltyp | Beskrivning |
|--- |--- |
| Standard IAB-robotregler | Om du väljer [!UICONTROL Enable IAB Bot Filtering Rules] används [IAB:s](https://www.iab.com) (International Advertising Bureau&#39;s) International Spiders &amp; Bots List för att ta bort robottrafiken. De flesta kunder väljer det här alternativet till ett minimum. |
| Anpassade robotregler | Du kan definiera och lägga till anpassade robotregler baserat på användaragenter, IP-adresser eller IP-intervall. |

## Standard IAB-robotregler

Du kan aktivera standardregler för IAB-robotar genom att markera kryssrutan [!UICONTROL Enable IAB Bot Filtering Rules]. Det här urvalet tar bort botar i IAB:s lista International Advertising Bureau&#39;s (International Advertising Bureau&#39;s) International Spiders &amp; Bots för att ta bort robottrafiken. Adobe uppdaterar denna lista från IAB varje månad.

![](assets/bot-iab-checkbox.png)

Adobe kan inte tillhandahålla den detaljerade IAB-robotlistan till kunder, men du kan använda Bots Report för att visa en lista med bots som har använt din webbplats. Om du vill skicka en robot till IAB-listan går du till [IAB](https://www.iab.com).

## Anpassade robotregler

>[!NOTE]
>
>Användargränssnittet tillåter att 500 regler definieras manuellt. När den här gränsen har nåtts måste reglerna hanteras i grupp med alternativen Importera fil och Exportera batchregler.

Med anpassade robotregler kan du filtrera trafikbaserade villkor som du definierar.

Anpassade robotregler definieras med följande villkorstyper:

* Användaragent
* IP-adress
* IP-intervall

Flera villkor kan definieras för en enskild regel. Flera villkor matchas med &quot;eller&quot;. Om du till exempel anger ett värde för användaragenten och IP-adressen räknas trafiken som starttrafik om något av villkoren uppfylls.

### Användaragent

Ett villkor för användaragenten kontrollerar om användaragentvärdet är **[!UICONTROL starts with]** eller **[!UICONTROL contains]** den angivna strängen. Om **[!UICONTROL contains]** är markerat matchas delsträngen om den förekommer någonstans i användaragenten.

Valfria värden kan inkluderas i **[!UICONTROL does not contain]**-listan för att definiera värden som användaragenten inte får innehålla för att matchningen ska lyckas. Du kan ange flera värden genom att inkludera ett värde per rad. Om användaragenten uppfyller villkoren som anges i matchningssträngen, men även innehåller en sträng i listan som inte innehåller någon, betraktas den inte som en matchning.

Fältet **[!UICONTROL contains]** är begränsat till 100 tecken. Listan innehåller inte mer än 255 tecken minus ett avgränsningstecken för varje ny rad. (Detta är lika med antalet strängar - 1. Om du anger 4 *innehåller inte* strängar krävs 3 avgränsningstecken.) Alla strängmatchningar är inte skiftlägeskänsliga.

### IP-adress (inklusive matchningar med jokertecken)

Matchar en IP-adress eller flera adresser i samma block med jokertecken (*). Ange de numeriska värdena för den IP-adress som du vill matcha. Ersätt * för alla värden som du vill matcha med ett jokertecken. Följande lista innehåller exempel på IP-adressmatchningssträng:

```
10.10.10.1
10.10.10.*
```

### IP-adressintervall

Ange de start- och slutintervall för IP-adresserna som ska matcha. Ersätt * för alla värden som du vill matcha med ett jokertecken.

### Definiera en anpassad robotregel

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, markera en eller flera rapportsviter och klicka på **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.
1. Klicka på **[!UICONTROL Add Rule]** och definiera ett eller flera matchningsvillkor.
1. Klicka på **[!UICONTROL Save]**. Ändringen bör träda i kraft inom 30 minuter.

## Överför robotregler

Om du vill importera robotregler gruppvis kan du överföra en CSV-fil som definierar reglerna.

Skapa en CSV-fil med följande kolumner i den ordning som de visas:

| Kolumn 1 | Kolumn 2 | Kolumn 3 | Kolumn 4 | Kolumn 5 |
|--- |--- |---|---|---|
| Punktnamn | IP-start | IP-slut | Agentmatchningsregel<br>(innehåller eller börjar med)</br> | Agenten exkluderar<br>(255 tecken)</br> |

Du kan definiera tre typer av båda reglerna:

* Användaragenten innehåller eller börjar med
* En IP-adress eller jokerteckenmatchning
* IP-intervallmatchning

Varje rad i importfilen kan bara innehålla en av följande båda definitioner:

* **Användaragenten innehåller eller börjar med**: Ange en enda användaragentsträng som ska matchas i kolumnen Agentinkludering. Ange den typ av matchning som du vill ska utföras genom att placera *innehåller* eller *startar med* i fältet Agentmatchningsregel. Ett valfritt värde kan inkluderas i kolumnen Agent Exclude som definierar en eller flera röravgränsade ( `|`) strängar som inte finns i agenten. Strängmatchningar är inte skiftlägeskänsliga. Både IP-startkolumnen och IP-slutkolumnen måste vara tomma.

* **En IP-adress eller jokerteckenmatchning**: Om du vill matcha en enda IP-adress (  `10.10.10.1`) eller IP-adress med jokertecken (  `10.10.*.*`) placerar du samma värde i kolumnerna IP Start och IP End. Matchningsregel, Inkludera agent och Exkludera agent måste vara tomma.

* **IP-intervallmatchning**: Definiera ett intervall med IP-adresser med kolumnerna IP Start och IP End. Jokertecken kan användas för att matcha IP-intervall, till exempel `10.10.10.*` till `10.10.20.*`. Matchningsregel, Inkludera agent och Exkludera agent måste vara tomma.

### Flera regler i kombination med OR

Om du vill matcha en robot med en kombination av regler som är kopplade till en OR (till exempel användaragent eller IP-adress), anger du ett identiskt namn för alla regler som du vill kombinera i fältet för båda namnen. AND-matchningar stöds inte.

### Skriv över alla regler med en överföringsfil

Markera kryssrutan **[!UICONTROL Overwrite existing rules]** om du vill ta bort alla befintliga regler och ersätta dem med reglerna som är definierade i överföringsfilen.

### Exportregler

Knappen **[!UICONTROL Export Uploaded Bot File]** exporterar alla regler som definierats i användargränssnittet i ett CSV-format.


## Robotregelns inverkan på datainsamling {#section_F01A3130E7A04A9993371CF26F6586F2}

Punktregler tillämpas på alla analysdata. Data som tas bort av punktregler visas bara i rapporter för start- och punktsidor.

VISTA-regler används efter punktregler (se [Bearbetningsordning).](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md)

**Bearbetning av besök med hög hastighet:** Om fler än 100 träffar inträffar under ett besök avgör rapporten om besökstiden i sekunder är mindre än eller lika med antalet träffar under besöket. I denna situation, på grund av kostnaderna för att behandla långa, intensiva besök, börjar rapporteringen om med ett nytt besök. Besök med många träffar orsakas normalt av robotattacker och betraktas inte som normala besökare.

>[!NOTE]
>
>Träffar som markerats som *`bots`* faktureras som [serversamtal.](/help/admin/c-server-call-usage/overage-overview.md)

## Inverkan av IP-förfalskning på robotfiltrering {#section_92E60B95BE8940D983F28C79E0CD6B12}

IAB-robotlistan baseras enbart på användaragent, så filtrering som baseras på den listan påverkas inte av inställningarna för IP-förfalskning. För icke-IAB-robotfiltrering (anpassade regler) kan IP ingå i filtreringsvillkoren. Om filtreringen börjar med IP sker robotfiltreringen efter att den sista oktetten har tagits bort om den inställningen är aktiverad, men före de andra alternativen för IP-begränsning, som att ta bort hela IP-adressen eller ersätta den med ett unikt ID.

Om IP-förfalskning är aktiverat inträffar IP-uteslutning innan IP-adressen döljs, så kunderna behöver inte ändra någonting när de aktiverar IP-förfalskning.

Om den sista oktetten tas bort, görs det före IP-filtrering. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande * ska matcha 0.
