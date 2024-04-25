---
title: Realtidsrapporter i Adobe Analytics
description: Lär dig hur du kan dra igång realtidsrapporter i Adobe Analytics som riktar sig till användare som är mer bekanta med Google Analytics.
feature: Third-party Integration
exl-id: 0ca27992-fff8-4bb4-8582-31fd401b23f6
source-git-commit: 8f08ff46d33d050d0bdb4e0555611ba37ccc8474
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---

# Realtidsrapporter

Realtidsrapporter visar vad som händer på er webbplats just nu. Den här typen av rapporter är särskilt användbara om du vill se omedelbara resultat av uppdateringar som du gör på webbplatsen. Ett företag som kör en försäljning på Black Friday kan till exempel mäta trafiken till specifika sidor och avgöra vilken försäljning som ska prioriteras baserat på resultatet i det ögonblicket.

![Realtidsrapport](/help/technotes/ga-to-aa/assets/realtime.png)

Realtidsrapporter är en av de få funktioner som ännu inte lagts in i Analysis Workspace. Använd rapporter för att hämta dessa data. De kräver en viss enkel konfiguration för att börja samla in data.

Så här når du rapportkonfigurationssidan i realtid (administratörsbehörighet krävs):

1. Klicka **[!UICONTROL Workspace]** i Adobe Analytics övre navigeringsfält.
1. Välj **[!UICONTROL Reports]** i det vänstra navigeringsfältet.
1. Välj **[!UICONTROL Enagement]** ![Chevron](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ChevronRight_18_N.svg) **[!UICONTROL Real-Time]**. Du kan också ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) sök i realtid.
1. Om rapportsviten ännu inte har aktiverats i realtid visas ett meddelande med en länk för att konfigurera rapportsviten.

Med Adobe kan upp till tre realtidsrapporter samla in data samtidigt. Alla måste konfigureras innan de kan börja samla in data i realtid.

![Rapportkonfiguration i realtid](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Platser i realtid

Platser i realtid talar om var besökarna befinner sig när de besöker er webbplats just nu. Så här konfigurerar du en av dina tre realtidsrapporter så att platsdata visas:

1. Klicka [!UICONTROL Configure] nära realtidsrapportens titel.
2. Under en av rapportplatserna i realtid:
   * Ge realtidsrapporten ett namn, till exempel&quot;Platser&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * För primär Dimension används vanligtvis GeoSegmentation Country. GeoSegmentation Region, GeoSegmentation US DMA och GeoSegmentation City finns också.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för platsen.
3. Klicka på [!UICONTROL Save and View Report].

## Trafikkällor i realtid

I realtid visar trafikkällor var besökarna kom från när de besökte er webbplats just nu. Så här konfigurerar du en av dina tre realtidsrapporter så att data från trafikkällor visas:

1. Klicka på &#39;Konfigurera&#39; bredvid rubriken för realtidsrapporten.
2. Under en av rapportplatserna i realtid:
   * Ge realtidsrapporten ett namn, till exempel&quot;Traffic Sources&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * Som primär Dimension används vanligen Referensdomän. Det finns även sökmotor och söknyckelord.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för trafikkällor.
3. Klicka på [!UICONTROL Save and View Report].

## Realtidsinnehåll

I realtid visas vilka sidor besökarna tittar på. Så här konfigurerar du en av dina tre realtidsrapporter så att innehållsdata visas:

1. Klicka [!UICONTROL Configure] nära realtidsrapportens titel.
2. Under en av rapportplatserna i realtid:
   * Ge realtidsrapporten ett namn, till exempel&quot;Innehåll&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * För Primär Dimension används vanligtvis Sida. Site Section och Server är också tillgängliga om implementeringen definierar dessa variabler.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för innehållet.
3. Klicka på [!UICONTROL Save and View Report].

## Händelser i realtid

Händelser i realtid talar om vilka händelser som inträffar mest på er webbplats. I Google Analytics hämtar en händelse det antal gånger en viss åtgärd (vanligtvis en åtgärd som inte har med sidvyn att göra) har utförts. GA-händelser skickas med en kategori, etikett och åtgärd. I Adobe Analytics är anpassade händelser mått som får egna namn i Admin Console och kan analyseras tillsammans med alla dimensioner. Om du letar efter en dimension i Adobe Analytics som liknar den i Google Analytics kan du överväga att använda dimensionen Custom Link, som ofta används som en catch-all för att samla in data som inte hör till sidvyerna (utöver Exit Links - for Exits - and Download Links - for Downloads).

>[!NOTE]
>
>När du använder anpassade händelser i realtidsrapporter måste dimensionsobjektet definieras i samma träff som den anpassade händelsen. Om du till exempel visar en anpassad registreringshändelse för dimensionen Referensdomän, returneras inga data utan ytterligare implementering. Eftersom referensdomänen bara visas vid den första träffen och en anpassad händelse normalt visas senare under besöket, kan data inte kopplas till realtidsrapporter. Dessa data är tillgängliga via Analysis Workspace med standardfördröjning, som vanligtvis är 30-90 minuter.

## Konverteringar i realtid

Realtidskonverteringar genererar data på olika plattformar. Målen i Google Analytics liknar mätvärden och framgångsrika händelser i Adobe Analytics. Du kan använda de flesta mätvärden i Adobe Analytics (både anpassade mätvärden som framgångshändelser och standardmätvärden som intäkter) i Real Time Reports. På samma sätt som för Google Analytics kan du även tillämpa dimensioner som produktnamn, spårningskod och kampanjresultat i realtidsrapporter.

1. Klicka [!UICONTROL Configure] nära realtidsrapportens titel.
2. Under en av rapportplatserna i realtid:
   * Ge realtidsrapporten ett namn, till exempel&quot;Konverteringar&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * Spårningskod används vanligtvis för primär Dimension. Produktdimensionen är även tillgänglig om den används i implementeringen.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för konverteringar.
3. Klicka på [!UICONTROL Save and View Report].

>[!NOTE]
>
>Om du använder händelser utanför instanser, t.ex. beställningar, måste implementeringen definiera dimensionen och händelsen för samma träff. Om dimensioner och händelser inte utlöses vid samma träff är dessa data tillgängliga i Analysis Workspace med standardfördröjning, som vanligtvis är 30-90 minuter.
