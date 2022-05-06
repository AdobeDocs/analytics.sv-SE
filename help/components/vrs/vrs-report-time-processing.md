---
description: Bearbetning av rapporttid är en virtuell rapportsvitsinställning som gör att data kan behandlas på ett icke-förstörande, retroaktivt sätt.
title: Bearbetning av rapporttid
role: Admin
solution: Analytics
feature: VRS
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: ec4edb257490d326ab8f8de51a4ab9412a2b4a28
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 1%

---

# Bearbetning av rapporttid

[!UICONTROL Report time processing] är en inställning för ett virtuellt rapportpaket som tillåter att data i Analysis Workspace behandlas på ett icke-förstörande, retroaktivt sätt.

[!UICONTROL Report Time Processing] påverkar bara data i den virtuella rapportsviten och påverkar inte data eller datainsamling i basrapportsviten. Skillnaden mellan [!UICONTROL Report Time Processing] och traditionell Analytics-bearbetning förstås bäst med följande diagram:

![Traditionell bearbetningsprocess](assets/google1.jpg)

Under databearbetningen i Analytics flödar data genom datainsamlingsflödet och in i ett förbearbetningssteg, som förbereder data för rapportering. I det här förbearbetningssteget används bl.a. logik för förfallodatum och beständighetslogik för eVar på data som samlas in. Den främsta nackdelen med den här förbehandlingsmodellen är att den kräver att all konfiguration görs i förväg innan data samlas in. Det innebär att ändringar i förbehandlingsinställningarna bara gäller för nya data från den tidpunkten och framåt. Det här är problematiskt om data kommer i fel ordning eller om inställningarna är felkonfigurerade.

[!UICONTROL Report Time Processing] är ett helt annat sätt att behandla Analytics-data för rapportering. I stället för att förbestämma bearbetningslogiken innan data samlas in, ignorerar Analytics datauppsättningen under förbearbetningssteget och använder den här logiken varje gång en rapport körs:

![Rörledning för bearbetning av rapporttid](assets/google2.jpg)

Denna bearbetningsarkitektur möjliggör mycket mer flexibla rapporteringsalternativ. Du kan t.ex. ändra besökets tidsgräns till hur länge du vill på ett icke-förstörande sätt och dessa ändringar återspeglas i eVar beständighets- och segmentbehållare under hela rapporteringsperioden. Dessutom kan du skapa ett valfritt antal virtuella rapportsviter, där vart och ett har olika alternativ för bearbetning av rapporttid som baseras på samma basrapportserie, utan att ändra några data i basrapportsviten.

[!UICONTROL Report Time Processing] gör det även möjligt för Analytics att förhindra bakgrundstötar från att starta nya besök och [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html) om du vill starta ett nytt besök när en appstartshändelse utlöses.

## Konfigurationsalternativ

Följande konfigurationsalternativ är tillgängliga för virtuella rapportsviter med rapporttidsbearbetning aktiverat:

* **[!UICONTROL Visit Timeout]:** Inställningen för tidsgräns för besök anger hur mycket inaktivitet en unik besökare måste ha innan ett nytt besök startas automatiskt. Standardvärdet är 30 minuter. Om du till exempel anger tidsgränsen för besök till 15 minuter skapas en ny besöksgruppering för varje sekvens av träffar som samlats in, åtskilda med 15 minuters inaktivitet. Den här inställningen påverkar inte bara antalet besök, utan även hur besökssegmentens behållare utvärderas och besökets förfallologik för eVars som förfaller vid besök. Om du minskar tidsgränsen för besöket ökar troligen det totala antalet besök i din rapportering, medan tidsgränsen för besöket minskar det totala antalet besök i din rapportering.
* **[!UICONTROL Mobile App Visit Settings]:** För rapportsviter som innehåller data som genererats av mobilappar via [Adobe Mobile SDKs](https://experienceleague.adobe.com/docs/mobile.html)finns ytterligare inställningar för besök. De här inställningarna är icke-förstörande och påverkar bara träffar som samlats in via Mobile SDK:er. De här inställningarna påverkar inte data som samlats in utanför Mobile SDK.
* **[!UICONTROL Prevent Background Hits from starting a new Visit]:** Bakgrundsträffar samlas in av Mobile SDK:er när appen är i bakgrundsläge.
* **[!UICONTROL Start a New Visit upon each App Launch]:** Förutom tidsgränsen för besök kan du tvinga ett besök att börja när en Appstart-händelse har spelats in från Mobile SDK:er oavsett inaktivitetsfönstret. Den här inställningen påverkar besöksmåtten och besökssegmentbehållaren, liksom logiken för besökets förfallodatum på eVars.
* **[!UICONTROL Start New Visit with Event]:** En ny session startar när en händelse utlöses, oavsett om en session har uppnått tidsgränsen eller inte. Den nyligen skapade sessionen innehåller händelsen som startade den. Dessutom kan du använda flera händelser för att starta en session och en ny session utlöses om någon av dessa händelser observeras i data. Den här inställningen påverkar antalet besök, besökssegmenteringsbehållaren och besökets förfallologik på eVars.

Här är en video om hur du startar ett nytt besök med eventet:

>[!VIDEO](https://video.tv.adobe.com/v/23129/?quality=12)

## Bearbetningsbegränsningar för rapporttid

Rapporttidsbearbetningen stöder inte alla mått och mått som är tillgängliga i traditionella analysrapporter. Virtuella rapportsviter som använder Report Time Processing är bara tillgängliga i Analysis Workspace och är inte tillgängliga i [!UICONTROL Reports & Analytics], Data warehouse, Report Builder, datafeeds eller API:t för rapportering.

Dessutom bearbetas endast data som kommer från rapportens datumintervall (kallas datumfönster nedan). Detta innebär att eVar som är inställda på&quot;aldrig förfaller&quot; för en besökare före rapportdatumintervallet inte finns kvar i rapporteringsfönstren och inte visas i rapporter. Detta innebär också att kundlojalitetsmätningarna enbart baseras på data som finns i rapporteringsdatumintervallet och inte på hela historiken före rapportens datumintervall.

Följande dimensioner och mått stöds inte för bearbetning av rapporttid:

* **Analyser för Target**
* **Analyser för Advertising Cloud mått/mätvärden**
* **Counter eVars**
* **Dagar före första köp**
* **Dagar sedan senaste köp**
* **Dagar sedan senaste besök**
* **Inmatningssidans originalformat**
* **Linjär allokeringsvariabler**
* **Listvariabler**
* **Dimensioner för marknadsföringskanaler**
* **Ursprunglig referensdomän**
* **Återbesöksfrekvens**
* **Enkelt besök**
* **Datakällor för transaktions-ID**
* **Besöksnummer**

## Påverkade mått och mätvärden

Nedan visas en lista över mått och mått som påverkas beroende på vilka inställningar för Tidsbearbetning för rapport som har valts:

* Om alternativet Förhindra att bakgrundstötningar startar ett nytt besök är aktiverat inträffar följande ändringar. Se [Sammanhangsberoende sessioner](vrs-mobile-visit-processing.md) för mer information.
   * **Studsfrekvens:** Bakgrundstötningar som inte följs av en förgrundsträff betraktas inte som ett studs och bidrar inte till studsfrekvensen.
   * **Antal sekunder per besök:** Endast besök som innehåller förgrundsträffar bidrar till detta mätresultat.
   * **Tid per besök:** Endast besök som innehåller förgrundsträffar bidrar till detta mätresultat.
   * **Dimensioner och mått för in-/utträde:** Endast inmatningar och utträden från besök med förgrundstreck visas i den här dimensionen.
   * **Unika besökarmått:** Unika besökare inkluderar inte besökare som bara hade bakgrundsträffar i rapportens datumintervall.
* **Besök:** Besökarna återspeglar de inställningar som har konfigurerats i den virtuella rapportsviten, som kan skilja sig från basrapportsviten.
* **Serialiserade händelser med händelse-ID:** Händelser som använder händelseserialisering med ett händelse-ID dedupliceras bara för händelser som inträffar inom rapportdatumintervallet för en besökare. Dessa händelser dedupliceras inte för alla datum eller besökare globalt på grund av fönstret för rapporttidsbearbetning.
* **Inköp/Inkomster/Beställningar/Enheter:** När inköps-ID används dedupliceras dessa värden endast för dubbletter av inköps-ID:n som finns inom rapportdatumintervallet för en besökare i stället för för på alla datum eller för besökare globalt på grund av fönstret för rapporttidsbearbetning.
* **Icke-marknadsförande eVars/reserverade eVars:** Värden som angetts i en eVar behålls bara om värdet angavs inom rapportdatumintervallet på grund av fönstret för rapporttidsbearbetning. Dessutom kan tidsbaserade förfallodatum förfalla en timme tidigt eller en timme sent om beständigheten sträcker sig över en sommartid.
* **Merchandising eVars/reserved eVars:** Se ovan. För konverteringssyntax, där bindningen är inställd på &quot;any event&quot;, används &quot;any hit&quot; i stället.
* **Träfftyp:** Den här dimensionen anger om en träff är för- eller bakgrundsbild.
* **Dimensioner med (lågtrafik) eller &quot;Uniques Exceeded&quot;:** Radobjektet (Lågtrafik) bestäms något annorlunda när du använder Rapporttidsbearbetning och är inte garanterat matchande vad som observeras vid rapportering på basrapportsviten. Det är inte säkert att radobjekt som inte ingår i lågtrafik motsvarar 100 % av Dimensionen för det radobjektet. Dessa skillnader kan bli mer uttalade ju högre antal unika värden som finns i en dimension.
