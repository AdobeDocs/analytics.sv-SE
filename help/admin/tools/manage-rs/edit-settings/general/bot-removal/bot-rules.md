---
description: Med Bot Rules kan du ta bort trafik som genereras av kända spindlar och botar från rapportsviten. Genom att ta bort robottrafiken kan du få ett mer exakt mått på användaraktiviteten på din webbplats.
title: Förstå och konfigurera robotregler
feature: Bot Removal
role: Admin
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 0%

---

# Förstå och konfigurera robotregler

Med Bot Rules kan du ta bort trafik från rapportsviten som genereras av kända spindlar och botar. Genom att ta bort robottrafiken kan du få ett mer exakt mått på användaraktiviteten på din webbplats.

När båda reglerna har definierats jämförs all inkommande trafik med de definierade reglerna. Trafik som uppfyller någon av dessa regler samlas inte in i rapportsviten och ingår inte i trafikmätningarna.

Att ta bort robottrafik minskar vanligen mängden trafik och konverteringsmått. Många kunder tycker att om man tar bort både trafik ökar konverteringsgraden och ökar användbarheten.

Punkttrafikdata lagras i en separat databas för visning i rapporter om start- och startsidor.

>[!NOTE]
>
>Adobe Experience Platform Edge Network tillhandahåller en [robotavkänningstjänst](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) som märker att träffar identifieras som om de kommer från bottnar. Processen för att identifiera robotar som används i Adobe Analytics är separat och refererar inte till robotpoängen som ingår i data som hämtas via Edge Network. De två systemen använder dock samma IAB-robotlista.

## Uppdatera eller överföra robotregler

>[!IMPORTANT]
>
>Innan du tar bort robottrafiken ska du kommunicera med intressenter för att se till att de kan göra de nödvändiga justeringarna av viktiga prestandaindikatorer som ett resultat av denna förändring. Om det är möjligt rekommenderar vi att man först tar bort både robottrafiken från ett litet rapporteringsprogram för att uppskatta den potentiella effekten.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Konfigurera robotregler](https://video.tv.adobe.com/v/335738/?quality=12){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


Så här uppdaterar eller överför du robotregler:

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Markera rapportsviten där du vill uppdatera båda reglerna och välj sedan **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.

1. Använd något av följande alternativ för att uppdatera eller överföra robotregler för rapportsviten:

   * Välj [!UICONTROL **Aktivera reglerna för IAB-filtrering**] om du vill ta bort robotar i IAB:s (International Advertising Bureau&#39;s) internationella spindlar och bottentrafik.

     Vi rekommenderar att du väljer det här alternativet till ett minimum.

     Mer information finns i avsnittet nedan, [Standard IAB-robotregler](#standard-iab-bot-rules).

   * Välj [!UICONTROL **Lägg till regel**] om du vill definiera och lägga till anpassade robotregler baserade på användaragenter, IP-adresser eller IP-intervall.

     Mer information finns i avsnittet nedan, [Anpassade robotregler](#custom-bot-rules).

   * Bredvid [!UICONTROL **Välj CSV-startfilen som ska importeras**] väljer du [!UICONTROL **Välj fil**] och sedan den CSV-fil som definierar robotreglerna.

     Mer information finns i avsnittet nedan, [Överför robotregler](#upload-bot-rules).

1. Välj [!UICONTROL **Spara**].

## Standard IAB-robotregler

Du kan aktivera standardregler för IAB-robotar genom att markera kryssrutan [!UICONTROL Enable IAB Bot Filtering Rules]. Det här urvalet tar bort botar i IAB:s (International Advertising Bureau&#39;s) International Spiders &amp; Bots List för att ta bort robottrafiken. Adobe uppdaterar den här listan från IAB varje månad.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-iab-checkbox.png)

Adobe kan inte tillhandahålla den detaljerade IAB-robotlistan till kunder, men du kan använda Bots Report för att visa en lista med bots som har kommit åt din webbplats. Om du vill skicka en robot till IAB-listan går du till [IAB](https://www.iab.com).

Mer information om hur du aktiverar standard-IAB-robotregler i en rapportsvit finns i [Uppdatera eller överföra robotregler](#update-or-upload-bot-rules).

## Anpassade robotregler

>[!NOTE]
>
>Användargränssnittet tillåter att 500 regler definieras manuellt. När den här gränsen har nåtts måste reglerna hanteras i grupp med alternativen Importera fil och Exportera batchregler.

Med anpassade robotregler kan du filtrera trafikbaserade villkor som du definierar. Information om hur du börjar aktivera anpassade robotregler i en rapportserie finns i [Uppdatera eller överföra robotregler](#update-or-upload-bot-rules).

Anpassade robotregler definieras med följande villkorstyper:

* Användaragent
* IP-adress
* IP-intervall

Flera villkor kan definieras för en enskild regel. Flera villkor matchas med &quot;eller&quot;. Om du till exempel anger ett värde för användaragenten och IP-adressen räknas trafiken som starttrafik om något av villkoren uppfylls.

### Användaragent

Ett villkor för användaragenten kontrollerar om användaragentvärdet är **[!UICONTROL starts with]** eller **[!UICONTROL contains]** den angivna strängen. Om **[!UICONTROL contains]** väljs matchas delsträngen om den finns någonstans i användaragenten.

Valfria värden kan inkluderas i listan **[!UICONTROL does not contain]** för att definiera värden som användaragenten inte får innehålla för en lyckad matchning. Du kan ange flera värden genom att inkludera ett värde per rad. Om användaragenten uppfyller villkoren som anges i matchningssträngen, men även innehåller en sträng i listan som inte innehåller någon, betraktas den inte som en matchning.

Fältet **[!UICONTROL contains]** får innehålla högst 100 tecken. Listan innehåller inte mer än 255 tecken minus ett avgränsningstecken för varje ny rad. (Detta motsvarar antalet strängar - 1. Om du anger 4 *som inte innehåller* strängar krävs 3 avgränsningstecken.) Alla strängmatchningar är inte skiftlägeskänsliga.

### IP-adress (inklusive matchningar med jokertecken)

Matchar en IP-adress eller flera adresser i samma block med jokertecken (&#42;). Ange de numeriska värdena för den IP-adress som du vill matcha. Ersätt &#42; för alla värden som du vill matcha med ett jokertecken. Följande lista innehåller exempel på IP-adressmatchningssträng:

```
10.10.10.1
10.10.10.*
```

### IP-adressintervall

Ange de start- och slutintervall för IP-adresserna som ska matcha. Ersätt &#42; för alla värden som du vill matcha med ett jokertecken.

### Definiera en anpassad robotregel

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, markera en eller flera rapportsviter och klicka på **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.
1. Klicka på **[!UICONTROL Add Rule]** och definiera ett eller flera matchningsvillkor.
1. Klicka på **[!UICONTROL Save]**. Ändringen bör träda i kraft inom 30 minuter.

## Överför robotregler

Om du vill importera robotregler gruppvis kan du överföra en CSV-fil som definierar reglerna.

1. Information om hur du börjar överföra båda reglerna till en rapportserie finns i [Uppdatera eller överföra båda reglerna](#update-or-upload-bot-rules).

1. Skapa en CSV-fil med följande kolumner, på rad 1 i kalkylbladet och i den ordning som anges:

   | Kolumn 1, rad 1 | Kolumn 2, rad 1 | Kolumn 3, rad 1 | Kolumn 4, rad 1 | Kolumn 5, rad 1 | Kolumn 6, rad 1 |
   |--- |--- |---|---|---|---|
   | Punktnamn | IP-start | IP-slut | Regel <br>(innehåller eller börjar med)</br> | Inkludera användaragent | Användaragenten uteslut<br>(högst 255 tecken)</br> |

   Du kan definiera tre typer av Båda-regler:

   * Användaragenten innehåller eller börjar med
   * En IP-adress eller jokerteckenmatchning
   * IP-intervallmatchning

   Varje rad i importfilen kan bara innehålla en av följande båda definitioner:

   >[!NOTE]
   >
   >   Om du vill matcha en robot med en kombination av regler som är kopplade till en OR (till exempel användaragent eller IP-adress), anger du ett identiskt namn för alla regler som du vill kombinera i fältet för båda namnen. AND-matchningar stöds inte.


   * **Användaragenten innehåller eller börjar med**: Ange en enda användaragentsträng som ska matcha i kolumnen Agentinkludering. Ange den typ av matchning som du vill ska utföras genom att placera *innehåller* eller *börjar med* i fältet Agentmatchningsregel. Ett valfritt värde kan inkluderas i kolumnen Agent Exclude som definierar en eller flera pipe-avgränsade ( `|` ) strängar som inte finns i agenten. Strängmatchningar är inte skiftlägeskänsliga. Både IP-startkolumnen och IP-slutkolumnen måste vara tomma.

   * **En IP-adress eller jokertecken matchar**: Om du vill matcha en enda IP-adress ( `10.10.10.1`) eller IP-adress med jokertecken ( `10.10.*.*`) placerar du samma värde i både IP-startkolumnen och IP-slutkolumnen. Matchningsregel, Inkludera agent och Exkludera agent måste vara tomma.

   * **IP-intervallmatchning**: Definiera ett intervall med IP-adresser med kolumnerna IP Start och IP End. Jokertecken kan användas för att matcha IP-intervall, till exempel `10.10.10.*` till `10.10.20.*`. Matchningsregel, Inkludera agent och Exkludera agent måste vara tomma.

1. På sidan Punktregler i Report Suite Manager väljer du [!UICONTROL **Välj fil**] bredvid [!UICONTROL **Välj CSV-fil för import**] och sedan den CSV-fil som definierar de båda regler som du vill importera.

1. (Valfritt) Markera kryssrutan **[!UICONTROL Overwrite existing rules]** om du vill ta bort alla befintliga regler och ersätta dem med de regler som är definierade i överföringsfilen.

1. Välj [!UICONTROL **Importera fil**].

1. Granska de importerade reglerna i området [!UICONTROL **Regeluppsättningar**].

1. Välj [!UICONTROL **Spara**].

## Exportera robotregler

Så här exporterar du alla regler som definieras i användargränssnittet i ett CSV-format:

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Markera rapportsviten som innehåller robotreglerna som du vill exportera och välj sedan **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.

1. Välj **[!UICONTROL Export Bot Rules]** och spara sedan CSV-filen i filsystemet.

## Robotreglernas inverkan på datainsamling {#section_F01A3130E7A04A9993371CF26F6586F2}

Punktregler tillämpas på alla analysdata. Data som tas bort av punktregler visas bara i rapporter för start- och punktsidor.

VISTA-regler tillämpas efter PUNKTREGLER. Se [Bearbetningsordning](/help/technotes/processing-order.md) i användarhandboken för Technotes.

**Bearbetning av besök med hög hastighet:** Om fler än 100 träffar inträffar under ett besök avgör rapporten om besökstiden i sekunder är mindre än eller lika med antalet träffar under besöket. I denna situation, på grund av kostnaderna för att behandla långa, intensiva besök, börjar rapporteringen om med ett nytt besök. Besök med många träffar orsakas normalt av robotattacker och betraktas inte som normala besökare.

>[!NOTE]
>
>Träffar markerade som *`bots`* faktureras som [serversamtal.](/help/admin/tools/server-call-usage/overage-overview.md)

## Inverkan av IP-förfalskning på robotfiltrering {#section_92E60B95BE8940D983F28C79E0CD6B12}

IAB-robotlistan baseras enbart på användaragent, så filtrering som baseras på den listan påverkas inte av inställningarna för IP-förfalskning. För icke-IAB-robotfiltrering (anpassade regler) kan IP ingå i filtreringsvillkoren. Om filtreringen börjar med IP sker robotfiltreringen efter att den sista oktetten har tagits bort om den inställningen är aktiverad, men före de andra alternativen för IP-begränsning, som att ta bort hela IP-adressen eller ersätta den med ett unikt ID.

Om IP-förfalskning är aktiverat inträffar IP-uteslutning innan IP-adressen döljs, så kunderna behöver inte ändra någonting när de aktiverar IP-förfalskning.

Om den sista oktetten tas bort, görs det före IP-filtrering. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande &#42; ska matcha 0.
