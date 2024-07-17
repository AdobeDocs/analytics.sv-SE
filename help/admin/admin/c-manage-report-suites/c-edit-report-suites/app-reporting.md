---
description: Aktivera mått och mätvärden för användning i spårning av mobilapplikationer.
title: Apprapportering
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---

# Apprapportering

Med gränssnittet App Reporting kan du aktivera livscykeldimensioner och mätvärden som är dedikerade för användning i spårning av mobilapplikationer.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**

>[!IMPORTANT]
>
>När någon av dessa funktioner har aktiverats kan de inte inaktiveras. Om du aktiverar en viss funktion blir dess respektive mått och mått permanent tillgängliga i Analysis Workspace.

## [!UICONTROL App Reports]

[!UICONTROL App Reports] dimensioner och mått används för följande syften:

* **Anskaffning**: Spåra refererande URL:er för nedladdningskampanjer för appar.
* **Livscykel**: Grundnivån för rapportering som tillhandahålls genom mätning som skickas vid varje programstart.
* **Programåtgärder**: Rapporter och sökvägar baserade på åtgärder i appen.
* **Livstidsvärde**: Förstå hur användare får upp värde över tiden med hjälp av nyckeltal för appar (t.ex. köp, annonsvyer, videoslutföranden, sociala resurser, fotoöverföringar).
* **Timed Events**: Mät hur lång tid som förflyter (i appen och total tid) mellan viktiga programåtgärder (till exempel tid före första köp).

När du aktiverar [!UICONTROL App Reports] är följande dimensioner tillgängliga:

* [!UICONTROL Action Name] (med dimensionerna [Entry](/help/components/dimensions/entry-dimensions.md) och [Exit](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL App Id]
* [!UICONTROL Acquisition Content]
* [!UICONTROL Acquisition Medium]
* [!UICONTROL Acquisition Name]
* [!UICONTROL Acquisition Source]
* [!UICONTROL Acquisition Term]
* [!UICONTROL Day of Week (SDK)]
* [!UICONTROL Days Since First Use]
* [!UICONTROL Days Since Last Use]
* [!UICONTROL Device Name (SDK)]
* [!UICONTROL Hour of Day (SDK)]
* [!UICONTROL First Launch Date]
* [!UICONTROL Launch Number]
* [!UICONTROL Lifetime Value (evar)]
* [!UICONTROL Operating System Version (SDK)]
* [!UICONTROL Resolution (SDK)]

Följande mått är tillgängliga:

* [!UICONTROL Action Time In App]
* [!UICONTROL Action Time Total]
* [!UICONTROL Crashes]
* [!UICONTROL First Launches]
* [!UICONTROL Launches]
* [!UICONTROL Lifetime Value (event)]
* [!UICONTROL Total Session Length]
* [!UICONTROL Upgrades]

## [!UICONTROL Location Tracking]

[!UICONTROL Location Tracking] dimensioner används för följande syften:

* Spåra latitud- och longituddata
* Identifiera, skapa och visualisera specifika intressepunkter. Intressepunkter måste definieras i den mobila SDK-konfigurationsfilen.
* Spåra bluetooth-fyrar (UUID, major, minor och närhet).

När du aktiverar [!UICONTROL Location Tracking] är följande dimensioner tillgängliga:

* [!UICONTROL Beacon Major] (med dimensionerna [Entry](/help/components/dimensions/entry-dimensions.md) och [Exit](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Beacon Minor] (med dimensionerna [Entry](/help/components/dimensions/entry-dimensions.md) och [Exit](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Beacon Proximity] (med dimensionerna [Entry](/help/components/dimensions/entry-dimensions.md) och [Exit](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Beacon UUID] (med dimensionerna [Entry](/help/components/dimensions/entry-dimensions.md) och [Exit](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Location (down to 10 km)]
* [!UICONTROL Location (down to 100 m)]
* [!UICONTROL Location (down to 1 m)]
* [!UICONTROL Point of Interest Name]
* [!UICONTROL Distance to Point of Interest Center]
* [!UICONTROL Point of Interest ID]

## [!UICONTROL Voice and Chatbots]

Med [!UICONTROL Voice and Chatbots] dimensioner och mätvärden kan du mäta röstassistenter som Alexa eller Google Home. Det gör det också möjligt att mäta chattbottar som vuxits hemma. Mätningsegenskaperna är:

* **Livscykel**: Grundnivå för rapportering för alla program, t.ex. antal starter och plattformstyp.
* **Konversationer**: Mäter återgivningar, svar och andra mått och mått som hör till konversationen.

När du aktiverar [!UICONTROL Voice and Chatbots] är följande dimensioner tillgängliga:

* [!UICONTROL Voice Device Capabilities] (med dimensionerna [Entry](/help/components/dimensions/entry-dimensions.md) och [Exit](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Voice Authentication]
* [!UICONTROL Voice Error Type]
* [!UICONTROL Voice Intent]
* [!UICONTROL Voice App Response]
* [!UICONTROL Voice Language]

Följande mått är tillgängliga:

* [!UICONTROL Voice End Session]
* [!UICONTROL Voice Error]
* [!UICONTROL Voice Utterances]

## Äldre rapportering och attribuering för bakgrundstödraster

Äldre rapportering innebär att träffar som genereras när en app finns i bakgrunden behandlas som vanliga förgrundsträffar. De visas i rapporter och påverkar attribueringen. Denna äldre konfiguration är vanligtvis önskvärd för att vara konsekvent med tidigare implementeringar.

Adobe rekommenderar att äldre rapportering inaktiveras så att bakgrundstötarna inte syns. Om du vill ta med bakgrundsträffar i din analys kan du aktivera inställningen [Virtual Report Suite](/help/components/vrs/vrs-about.md) **[!UICONTROL Include background hits]**.
