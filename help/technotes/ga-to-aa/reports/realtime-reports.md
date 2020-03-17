---
title: Realtidsrapporter i Adobe Analytics
description: Lär dig hur du kan hämta realtidsrapporter i Adobe Analytics, som riktar sig till användare som är mer bekanta med Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Realtidsrapporter

Realtidsrapporter visar vad som händer på er webbplats just nu. Den här typen av rapporter är särskilt användbara om du vill se omedelbara resultat av uppdateringar som du gör på webbplatsen. Ett företag som kör en försäljning på Black Friday kan till exempel mäta trafiken till specifika sidor och avgöra vilken försäljning som ska prioriteras baserat på resultatet i det ögonblicket.

![Realtidsrapport](/help/technotes/ga-to-aa/assets/realtime.png)

Realtidsrapporter är en av de få funktioner som ännu inte finns i Analysis Workspace. Använd Rapporter och analyser för att hämta dessa data. De kräver en viss enkel konfiguration för att börja samla in data.

Så här når du rapportkonfigurationssidan i realtid (administratörsbehörighet krävs):

1. Klicka [!UICONTROL Reports] i rubriknavigeringen i Adobe Analytics.
2. Klicka på *[!UICONTROL Site Metrics]* > *[!UICONTROL Real-Time]* i den vänstra menyn.
3. Om rapportsviten ännu inte har aktiverats i realtid visas ett meddelande med en länk för att konfigurera rapportsviten. Om rapportsviten har aktiverats i realtid klickar du [!UICONTROL Configure] nära rapportens titel i realtid.

Adobe tillåter upp till tre realtidsrapporter att samla in data samtidigt. Alla måste konfigureras innan de börjar samla in data i realtid.

![Rapportkonfiguration i realtid](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Platser i realtid

Platser i realtid talar om var besökarna befinner sig när de besöker er webbplats just nu. Så här konfigurerar du en av dina tre realtidsrapporter så att platsdata visas:

1. Klicka [!UICONTROL Configure] nära rubriken för realtidsrapporten.
2. Under en av rapportplatserna i realtid:
   * Namnge din realtidsrapport; till exempel &quot;Platser&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * För primär dimension används vanligtvis GeoSegmentation Country. GeoSegmentation Region, GeoSegmentation US DMA och GeoSegmentation City finns också.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för platsen.
3. Klicka på [!UICONTROL Save and View Report].

## Trafikkällor i realtid

I realtid visar trafikkällor var besökarna kom från när de besökte er webbplats just nu. Så här konfigurerar du en av dina tre realtidsrapporter så att data från trafikkällor visas:

1. Klicka på &#39;Konfigurera&#39; bredvid rubriken för realtidsrapporten.
2. Under en av rapportplatserna i realtid:
   * Namnge din realtidsrapport; till exempel&quot;Trafikkällor&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * För primär dimension används vanligtvis referensdomän. Det finns även sökmotor och söknyckelord.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för trafikkällor.
3. Klicka på [!UICONTROL Save and View Report].

## Realtidsinnehåll

I realtid visas vilka sidor besökarna tittar på. Så här konfigurerar du en av dina tre realtidsrapporter så att innehållsdata visas:

1. Klicka [!UICONTROL Configure] nära rubriken för realtidsrapporten.
2. Under en av rapportplatserna i realtid:
   * Namnge din realtidsrapport; till exempel&quot;Innehåll&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * För Primär dimension används sidan vanligtvis. Site Section och Server är också tillgängliga om implementeringen definierar dessa variabler.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för innehållet.
3. Klicka på [!UICONTROL Save and View Report].

## Händelser i realtid

Händelser i realtid talar om vilka händelser som inträffar mest på er webbplats. I Google Analytics hämtar en händelse det antal gånger en specifik åtgärd (vanligtvis en åtgärd som inte har med sidvyn att göra) har utförts. GA-händelser skickas med en kategori, etikett och åtgärd. I Adobe Analytics är anpassade händelser mätvärden som får egna namn i Admin Console och kan analyseras tillsammans med alla dimensioner. Om du är ute efter en dimension i Adobe Analytics som liknar Google Analytics-händelser kan du överväga att använda dimensionen Custom Link, som ofta används som en catch-all för att samla in data som inte har med sidvisningar att göra (utöver Exit Links - for Exits - and Download Links - for Downloads).

> [!NOTE] När du använder anpassade händelser i realtidsrapporter måste dimensionsvärdet definieras i samma träff som den anpassade händelsen. Om du till exempel visar en anpassad registreringshändelse för dimensionen Referensdomän, returneras inga data utan ytterligare implementering. Eftersom referensdomänen bara visas vid den första träffen och en anpassad händelse normalt visas senare under besöket, kan data inte kopplas till realtidsrapporter. Dessa data är tillgängliga via Analysis Workspace med standardsvarstid, som vanligtvis är 30-90 minuter.

## Konverteringar i realtid

Realtidskonverteringar genererar data på olika plattformar. Google Analytics-målsättningarna liknar mätvärden och framgångsrika händelser i Adobe Analytics. Ni kan använda de flesta mätvärden i Adobe Analytics (både anpassade mätvärden som success events och standardmätvärden som revenue) i realtidsrapporter. På samma sätt som med Google Analytics kan ni också tillämpa dimensioner som produktnamn, spårningskod och kampanjresultat i realtidsrapporter.

1. Klicka [!UICONTROL Configure] nära rubriken för realtidsrapporten.
2. Under en av rapportplatserna i realtid:
   * Namnge din realtidsrapport; till exempel &quot;Konverteringar&quot;.
   * Förekomster används vanligtvis som mått. Användare/unika besökare är för närvarande inte tillgängliga i realtidsrapporter.
   * För primär dimension används spårningskod vanligtvis. Produktdimensionen är även tillgänglig om den används i implementeringen.
   * För de två sekundära dimensionerna använder du de önskade ytterligare data som du vill se för den här trafiken. Sekundära dimensioner behöver inte vara specifika för konverteringar.
3. Klicka på [!UICONTROL Save and View Report].

> [!NOTE] Om du använder händelser utanför instanser, t.ex. beställningar, måste implementeringen definiera dimensionen och händelsen för samma träff. Om dimensioner och händelser inte utlöses vid samma träff är dessa data tillgängliga i Analysis Workspace med standardfördröjning för bearbetning, som vanligtvis är 30-90 minuter.
