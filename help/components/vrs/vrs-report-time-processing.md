---
description: Bearbetning av rapporttid är en virtuell rapportsvitsinställning som gör att data kan behandlas på ett icke-förstörande, retroaktivt sätt.
title: Bearbetning av rapporttid
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Bearbetning av rapporttid

Bearbetning av rapporttid är en virtuell rapportsvitsinställning som gör att data kan behandlas på ett icke-förstörande, retroaktivt sätt.

> [!NOTE] Rapporttidsbearbetning är bara tillgängligt för Analysis Workspace.

Tidsbearbetning för rapportering påverkar bara data i den virtuella rapportsviten och påverkar inte data eller datainsamling i basrapportsviten. Skillnaden mellan Report Time Processing och traditionell Analytics-bearbetning är bäst att förstå med följande diagram:

![Google1](assets/google1.jpg)

Under databearbetningen i Analytics flödar data genom datainsamlingsflödet och in i ett förbearbetningssteg, som förbereder data för rapportering. I det här förbearbetningssteget används bl.a. förfallologik och eVar-beständighetslogik för data när de samlas in. Den främsta nackdelen med den här förbehandlingsmodellen är att den kräver att all konfiguration görs i förväg innan data samlas in. Det innebär att ändringar i förbehandlingsinställningarna bara gäller för nya data från den tidpunkten och framåt. Det här är problematiskt om data kommer i fel ordning eller om inställningarna är felkonfigurerade.

Tidsbearbetning för rapportering är ett helt annat sätt att behandla analysdata för rapportering. I stället för att förbestämma bearbetningslogiken innan data samlas in, ignorerar Analytics datauppsättningen under förbearbetningssteget och använder den här logiken varje gång en rapport körs:

![Google2](assets/google2.jpg)

Denna bearbetningsarkitektur möjliggör mycket mer flexibla rapporteringsalternativ. Du kan till exempel ändra besökets timeout-period till hur lång tid du vill på ett icke-förstörande sätt, och dessa ändringar återspeglas i din eVar-beständighet och segmentbehållare retroaktivt som om du hade använt dessa inställningar innan data samlades in. Dessutom kan du skapa ett valfritt antal virtuella rapportsviter, där vart och ett har olika alternativ för bearbetning av rapporttid som baseras på samma basrapportserie, utan att ändra några data i basrapportsviten.

Med Report Time Processing kan Analytics även förhindra bakgrundstötningar från att starta nya besök och [mobil-SDK](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) kan tala om för rapportanvändare att starta ett nytt besök när en Appstart-händelse utlöses.

Följande konfigurationsalternativ är tillgängliga för virtuella rapportsviter med rapporttidsbearbetning aktiverat:

* **Besök timeout:** Inställningen för tidsgräns för besök anger hur mycket inaktivitet en unik besökare måste ha innan ett nytt besök startas automatiskt. Standardvärdet är 30 minuter. Om du till exempel anger tidsgränsen för besök till 15 minuter skapas en ny besöksgruppering för varje sekvens av träffar som samlats in, åtskilda med 15 minuters inaktivitet. Den här inställningen påverkar inte bara antalet besök, utan även hur besökssegmentens behållare utvärderas och besökets förfallologik för eVars som förfaller vid besök. Om du minskar tidsgränsen för besöket ökar troligen det totala antalet besök i din rapportering, medan tidsgränsen för besöket minskar det totala antalet besök i din rapportering.
* **Besöksinställningar för mobilappar:** Ytterligare besöksinställningar finns tillgängliga för rapportsviter som innehåller data som genererats av mobilappar via [Adobe Mobile SDK](https://www.adobe.io/apis/cloudplatform/mobile.html). De här inställningarna är icke-förstörande och påverkar bara träffar som samlats in via Mobile SDK:er. De här inställningarna påverkar inte data som samlats in utanför Mobile SDK.
* **Förhindra att bakgrundstötningar startar ett nytt besök:** Bakgrundsträffar samlas in av Mobile SDK:er när appen är i bakgrundsläge.
* **Starta ett nytt besök vid varje appstart:** Förutom tidsgränsen för besök kan du tvinga ett besök att börja när en Appstart-händelse har spelats in från Mobile SDK:er oavsett inaktivitetsfönstret. Den här inställningen påverkar besöksmåtten och besökssegmentbehållaren, liksom logiken för besökets förfallodatum på eVars.
* **Starta nytt besök med evenemang:** En ny session startar när en händelse utlöses, oavsett om en session har uppnått tidsgränsen eller inte. Den nyligen skapade sessionen innehåller händelsen som startade den. Dessutom kan du använda flera händelser för att starta en session och en ny session utlöses om någon av dessa händelser observeras i data. Den här inställningen påverkar antalet besök, besökssegmenteringsbehållaren och besökets förfallologik på eVars.

Rapporttidsbearbetningen stöder inte alla mått och mått som är tillgängliga i traditionella analysrapporter. Virtuella rapportsviter som använder Report Time Processing är bara tillgängliga på Analysis Workspace och kommer inte att vara tillgängliga i [!UICONTROL Reports & Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds eller API:t för rapportering.

Dessutom bearbetas endast data som kommer från rapportens datumintervall (kallas datumfönster nedan). Det innebär att eVar-värden som är inställda på&quot;aldrig förfaller&quot; för en besökare före rapportens datumintervall inte finns kvar i rapporteringsfönstren och inte visas i rapporter. Detta innebär också att kundlojalitetsmätningarna enbart baseras på data som finns i rapporteringsdatumintervallet och inte på hela historiken före rapportens datumintervall.

Nedan finns en lista med mått och mått som för närvarande inte stöds vid bearbetning av rapporttid:

* **Analyser för Target:** Stöds inte för närvarande. Framtida stöd planeras.
* **Analyser för Advertising Cloud-reserverade mått:** Stöds inte för närvarande. Framtida stöd planeras.
* **Mått för enkel åtkomst:** Stöds inte permanent.
* **Listvariabler:** Stöds inte för närvarande. Framtida stöd planeras.
* **Counter eVars:** Stöds inte permanent.
* **Variabler för marknadsföringskanaler:** Stöds inte för närvarande. Framtida stöd planeras.
* **Dagar sedan senaste inköpsdimension:** Den här dimensionen stöds inte på grund av karaktären hos fönstret för rapporttidsbearbetning.
* **Dagar före första inköpsdimension:** Den här dimensionen stöds inte på grund av karaktären hos fönstret för rapporttidsbearbetning.
* **Returfrekvensdimension:** Den här dimensionen stöds inte på grund av karaktären hos fönstret för rapporttidsbearbetning. Ett alternativt sätt att använda ett besöksräkningsmått i ett segment är möjligt, eller att använda besöksmåttet i en histogramrapport.
* **Dagar sedan senaste besök Dimension:** Den här dimensionen stöds inte på grund av karaktären hos fönstret för rapporttidsbearbetning.
* **Ursprunglig dimension för startsida:** Den här dimensionen stöds inte på grund av karaktären hos fönstret för rapporttidsbearbetning.
* **Linjär allokeringsvariabler:** Stöds inte för närvarande. Framtida stöd planeras.
* **Ursprunglig referensdomändimension:** Stöds inte för närvarande. Framtida stöd planeras.
* **Besök nummer:** Detta mått stöds inte på grund av karaktären hos fönstret för rapporttidsbearbetning. Som ett alternativ i mobilappar kan du använda ett beräknat mått, inklusive besökare/besök med mätvärdet för appinstallation, för att identifiera nya besökare eller besök.
* **Datakällor för transaktions-ID:** Stöds inte för närvarande. Framtida stöd planeras.

Nedan visas en lista över mått och mått som påverkas beroende på vilka inställningar för Tidsbearbetning för rapport som har valts:

* Om alternativet Förhindra att bakgrundstötningar startar ett nytt besök är aktiverat inträffar följande ändringar. Mer information finns i [Sammanhangsberoende sessioner](vrs-mobile-visit-processing.md) .
   * **Studsfrekvens:** Bakgrundstötningar som inte följs av en förgrundsträff betraktas inte som ett studs och bidrar inte till studsfrekvensen.
   * **Antal sekunder per besök:** Endast besök som innehåller förgrundsträffar bidrar till detta mätresultat.
   * **Tid per besök:** Endast besök som innehåller förgrundsträffar bidrar till detta mätresultat.
   * **Ingångs-/avslutningsmått och mätvärden:** Endast inmatningar och utträden från besök med förgrundstreck visas i den här dimensionen.
   * **Unika besökarmått:** Unika besökare inkluderar inte besökare som bara hade bakgrundsträffar i rapportens datumintervall.
* **Besök:** Besökarna återspeglar de inställningar som har konfigurerats i den virtuella rapportsviten, som kan skilja sig från basrapportsviten.
* **Serialiserade händelser med händelse-ID:** Händelser som använder händelseserialisering med ett händelse-ID dedupliceras bara för händelser som inträffar inom rapportdatumintervallet för en besökare. Dessa händelser dedupliceras inte för alla datum eller besökare globalt på grund av fönstret för rapporttidsbearbetning.
* **Inköp/Inkomster/Beställningar/Enheter:** När inköps-ID används dedupliceras dessa värden endast för dubbletter av inköps-ID:n som finns inom rapportdatumintervallet för en besökare i stället för för på alla datum eller för besökare globalt på grund av fönstret för rapporttidsbearbetning.
* **Icke-marknadsförande eVars/reserverade eVars:** Värden som angetts i en eVar finns bara kvar om värdet angavs inom rapportdatumintervallet på grund av fönstret för rapporttidsbearbetning. Dessutom kan tidsbaserade förfallodatum förfalla en timme tidigt eller en timme sent om beständigheten sträcker sig över en sommartid.
* **Merchandising eVars/reserved eVars:** Se ovan. För konverteringssyntax, där bindningen är inställd på &quot;any event&quot;, används &quot;any hit&quot; i stället.
* **Träfftyp:** Den här dimensionen anger om en träff är för- eller bakgrundsbild.
