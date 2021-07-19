---
description: Bearbetning av rapporttid är en virtuell rapportsvitsinställning som gör att data kan behandlas på ett icke-förstörande, retroaktivt sätt.
title: Bearbetning av rapporttid
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: 3867573780a791ec4cf2b2ceda33707d972f3f5c
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 0%

---

# Bearbetning av rapporttid

Bearbetning av rapporttid är en virtuell rapportsvitsinställning som gör att data kan behandlas på ett icke-förstörande, retroaktivt sätt.

>[!NOTE]
>
>Tidsbearbetning för rapport är bara tillgängligt för Analysis Workspace.

Tidsbearbetning för rapportering påverkar bara data i den virtuella rapportsviten och påverkar inte data eller datainsamling i basrapportsviten. Skillnaden mellan Report Time Processing och traditionell Analytics-bearbetning är bäst att förstå med följande diagram:

![Google1](assets/google1.jpg)

Under databearbetningen i Analytics flödar data genom datainsamlingsflödet och in i ett förbearbetningssteg, som förbereder data för rapportering. I det här förbearbetningssteget används bl.a. logik för förfallodatum och beständighetslogik för eVar på data som samlas in. Den främsta nackdelen med den här förbehandlingsmodellen är att den kräver att all konfiguration görs i förväg innan data samlas in. Det innebär att ändringar i förbehandlingsinställningarna bara gäller för nya data från den tidpunkten och framåt. Det här är problematiskt om data kommer i fel ordning eller om inställningarna är felkonfigurerade.

Tidsbearbetning för rapportering är ett helt annat sätt att behandla analysdata för rapportering. I stället för att förbestämma bearbetningslogiken innan data samlas in, ignorerar Analytics datauppsättningen under förbearbetningssteget och använder den här logiken varje gång en rapport körs:

![Google2](assets/google2.jpg)

Denna bearbetningsarkitektur möjliggör mycket mer flexibla rapporteringsalternativ. Du kan t.ex. ändra besökets tidsgräns till hur länge du vill på ett icke-förstörande sätt och dessa ändringar återspeglas i eVar beständighet och segmentbehållare retroaktivt som om du hade använt dessa inställningar innan data samlades in. Dessutom kan du skapa ett valfritt antal virtuella rapportsviter, där vart och ett har olika alternativ för bearbetning av rapporttid som baseras på samma basrapportserie, utan att ändra några data i basrapportsviten.

Med Report Time Processing kan Analytics även förhindra bakgrundstötningar från att starta nya besök och gör att [mobil-SDK](https://www.adobe.io/apis/cloudplatform/mobile.html) kan ange att rapportering ska starta ett nytt besök när en appstartshändelse utlöses.

Följande konfigurationsalternativ är tillgängliga för virtuella rapportsviter med rapporttidsbearbetning aktiverat:

* **Besök Timeout:** Inställningen för tidsgräns för besök anger hur mycket inaktivitet en unik besökare måste ha innan ett nytt besök startas automatiskt. Standardvärdet är 30 minuter. Om du till exempel anger tidsgränsen för besök till 15 minuter skapas en ny besöksgruppering för varje sekvens av träffar som samlats in, åtskilda med 15 minuters inaktivitet. Den här inställningen påverkar inte bara antalet besök, utan även hur besökssegmentens behållare utvärderas och besökets förfallologik för eVars som förfaller vid besök. Om du minskar tidsgränsen för besöket ökar troligen det totala antalet besök i din rapportering, medan tidsgränsen för besöket minskar det totala antalet besök i din rapportering.
* **Besöksinställningar för mobilappar:** För rapportsviter som innehåller data som genererats av mobilappar via SDK:n för  [Adobe Mobile finns ytterligare](https://www.adobe.io/apis/cloudplatform/mobile.html) besöksinställningar tillgängliga. De här inställningarna är icke-förstörande och påverkar bara träffar som samlats in via Mobile SDK:er. De här inställningarna påverkar inte data som samlats in utanför Mobile SDK.
* **Förhindra att bakgrundstötningar startar ett nytt besök:** Bakgrundstötlar samlas in av SDK:n för mobiler när appen är i bakgrundsläge.
* **Starta ett nytt besök vid varje appstart:** Förutom tidsgränsen för besöket kan du tvinga ett besök att börja när en appstartshändelse har spelats in från Mobile SDK:er oavsett inaktivitetsfönstret. Den här inställningen påverkar besöksmåtten och besökssegmentbehållaren, liksom logiken för besökets förfallodatum på eVars.
* **Starta nytt besök med händelse:** En ny session startar när en händelse utlöses, oavsett om en session har uppnått tidsgränsen eller inte. Den nyligen skapade sessionen innehåller händelsen som startade den. Dessutom kan du använda flera händelser för att starta en session och en ny session utlöses om någon av dessa händelser observeras i data. Den här inställningen påverkar antalet besök, besökssegmenteringsbehållaren och besökets förfallologik på eVars.

Rapporttidsbearbetningen stöder inte alla mått och mått som är tillgängliga i traditionella analysrapporter. Virtuella rapportsviter som använder Report Time Processing är bara tillgängliga i Analysis Workspace och är inte tillgängliga i [!UICONTROL Reports & Analytics], Data warehouse, Report Builder, Data Feeds eller API:t för rapportering.

Dessutom bearbetas endast data som kommer från rapportens datumintervall (kallas datumfönster nedan). Detta innebär att eVar som är inställda på&quot;aldrig förfaller&quot; för en besökare före rapportdatumintervallet inte finns kvar i rapporteringsfönstren och inte visas i rapporter. Detta innebär också att kundlojalitetsmätningarna enbart baseras på data som finns i rapporteringsdatumintervallet och inte på hela historiken före rapportens datumintervall.

Nedan finns en lista med mått och mått som för närvarande inte stöds vid bearbetning av rapporttid:

* **Analyser för mål:** stöds för närvarande inte. Framtida stöd planeras.
* **Analyser för Advertising Cloud reserverade värden/dimensioner:** Stöds för närvarande inte. Framtida stöd planeras.
* **Mått för enkel åtkomst:** stöds inte permanent.
* **List-variabler:** stöds inte för närvarande. Framtida stöd planeras.
* **Counter eVars:** Stöds inte permanent.
* **marknadsföringskanalvariabler:stöds** inte för närvarande. Framtida stöd planeras.
* **Dagar sedan Dimensionen för det senaste köpet:** På grund av karaktären hos fönstret för rapporttidsbearbetning stöds inte den här dimensionen.
* **Dimensionen Dagar före första köpet:** På grund av typen för fönstret för rapporttidsbearbetning stöds inte den här dimensionen.
* **Dimension för returfrekvens:** På grund av karaktären hos fönstret för rapporttidsbearbetning stöds inte den här dimensionen. Ett alternativt sätt att använda ett besöksräkningsmått i ett segment är möjligt, eller att använda besöksmåttet i en histogramrapport.
* **Dagar sedan senaste besök-Dimensionen:** På grund av karaktären hos fönstret för rapporttidsbearbetning stöds inte den här dimensionen.
* **Ursprunglig Dimension för startsida:** På grund av karaktären hos fönstret för rapporttidsbearbetning stöds inte den här dimensionen.
* **Linear Allocation eVars:** Stöds för närvarande inte. Framtida stöd planeras.
* **Ursprunglig Dimension för referensdomän:** stöds inte för tillfället. Framtida stöd planeras.
* **Besök Nummer:** På grund av karaktären hos fönstret för rapporttidsbearbetning stöds inte det här måttet. Som ett alternativ i mobilappar kan du använda ett beräknat mått, inklusive besökare/besök med mätvärdet för appinstallation, för att identifiera nya besökare eller besök.
* **Datakällor för transaktions-ID:** stöds för närvarande inte. Framtida stöd planeras.

Nedan visas en lista över mått och mått som påverkas beroende på vilka inställningar för Tidsbearbetning för rapport som har valts:

* Om alternativet Förhindra att bakgrundstötningar startar ett nytt besök är aktiverat inträffar följande ändringar. Mer information finns i [Sammanhangsberoende sessioner](vrs-mobile-visit-processing.md).
   * **Studsfrekvens/studsfrekvens:** Bakgrundsträffar som inte följs av en förgrundsträff betraktas inte som studsande och bidrar inte till studsfrekvensen.
   * **Antal sekunder per besök:** Endast besök som innehåller förgrundsträffar bidrar till detta mätresultat.
   * **Tid per besök:** Endast besök som innehåller förgrundsträffar bidrar till detta mätresultat.
   * **Dimensioner och mått för in-/utträde:** Endast inmatningar och utmatningar från besök med förgrundsträffar visas i den här dimensionen.
   * **Unika besökarmått:** Unika besökare inkluderar inte besökare som bara hade bakgrundsträffar i rapportens datumintervall.
* **Besök:** Besök återspeglar de inställningar som den virtuella rapportsviten har konfigurerat, vilka kan skilja sig från basrapportsviten.
* **Serialiserade händelser med händelse-ID:** n:Händelser som använder händelseserialisering med ett händelse-ID dedupliceras bara för händelser som inträffar inom rapportdatumintervallet för en besökare. Dessa händelser dedupliceras inte för alla datum eller besökare globalt på grund av fönstret för rapporttidsbearbetning.
* **Inköp/Intäkter/Beställningar/Enheter:** När inköps-ID används dedupliceras dessa värden endast för dubbletter av inköps-ID:n som inträffar inom rapportdatumintervallet för en besökare i stället för för för alla datum eller för besökare globalt på grund av fönstret för rapporttidsbearbetning.
* **Icke-marknadsförande eVars/reserverade eVars:** Värden som anges i en eVar finns bara kvar om värdet angavs inom rapportdatumintervallet på grund av fönstret för rapporttidsbearbetning. Dessutom kan tidsbaserade förfallodatum förfalla en timme tidigt eller en timme sent om det kvarstående förloppet sträcker sig över en sommartid.
* **Merchandising eVars/reserved eVars:** See above. För konverteringssyntax, där bindningen är inställd på &quot;any event&quot;, används &quot;any hit&quot; i stället.
* **Träfftyp:** Den här dimensionen anger om en träff är för- eller bakgrundsbild.
