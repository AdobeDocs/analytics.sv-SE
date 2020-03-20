---
title: Detaljerad marknadsföringskanal - första och sista beröring
description: Tilldela framgångsstatistik och intäkter till olika kanaldetaljer utan hänsyn till den övergripande kanalen de är i.
translation-type: tm+mt
source-git-commit: 5bb107f22490bb9e092292367c51df4eafd43ba4

---


# Detaljerad marknadsföringskanal - första och sista beröring

Dessa rapporter ger insikt om de specifika kampanjer eller nyckelord som är mest effektiva på er webbplats. Ni kan använda den här rapporten för att allokera framgångsmått och intäkter till olika kanaldetaljer, utan hänsyn till den övergripande kanalen de är i. Du kan till exempel se hur ett visst betalt söknyckelord jämförs med en e-postkampanj. I motsats till rapporten Marketing Channel Overview liknar den här rapporten en standardrapport.

## Rapportegenskaper

* Den här rapporten körs på regler som definierats i marknadsföringskanaler. Se [Kanaler och regler](/help/components/c-marketing-channels/c-channels.md).

   I rapporten används i synnerhet den **[!UICONTROL Set the channel's value to]** del av varje regel som används. Om du ändrar dessa regler eller hur kanalens värde ställs in ändras hur data i den här rapporten beräknas. Mer information finns i [Vanliga frågor och svar](/help/components/c-marketing-channels/c-faq.md) om regler för bearbetning av marknadsföringskanaler.

* Skillnaderna mellan *First* och *Last Touch* finns i [Om marknadsföringskanalrapporter](/help/components/c-marketing-channels/analyze-mc.md).

* Behandlingsordningen är avgörande för hur marknadsföringskanaler fungerar. Varje träff kontrollerar först villkoren högst upp i bearbetningsreglerna och filtrerar sedan därifrån.
* Den här rapporten kan visas i trendformat och rankningsformat.
* Den här rapporten kan använda ett sökfilter för att hitta specifika radobjekt.
* Förutom olika kanaler som samlas in med standardmetoder kan [offlinedatakällor](/help/components/c-marketing-channels/c-getting-started-mchannel.md) användas.
* Du kan använda [klassificeringar](/help/components/c-classifications2/c-classifications.md) i den här rapporten, så att du kan byta namn på och konsolidera radobjekt. Information om marknadsföringskanaler finns [här](/help/components/c-marketing-channels/classifictions-mchannel.md).

* Den här rapporten kan delas upp i alla andra Marketing Channel-rapporter.
* Följande mått kan användas i den här rapporten (beroende på inställningar för organisation och rapportsviten):
   * Klickfunktioner: det antal gånger som variabeln *`s.campaign`* definieras.
   * Nya åtaganden: antalet besökare som har fått en ny First Touch Channel.
   * Alla standardvärden för e-handel: Intäkter, beställningar, enheter, kundvagnar, kundvagnsvyer, utcheckningar, kundvagnstillägg, kundvagnsborttagningar.
   * Alla anpassade händelser: Händelser 1-80 och Händelser 81-100 om H22-koden eller senare används.
   * Besök och besökare: tillgängligheten är beroende av organisation och rapportserie. Kontakta kontohanteraren om du vill ha mer information.
   Se [Mätvärden](https://marketing.adobe.com/resources/help/en_US/mchannel/c_overview_metrics.html) i [!UICONTROL Marketing Channel] hjälpen.
