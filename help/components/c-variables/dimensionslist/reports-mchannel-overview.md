---
description: Översiktsrapporten om marknadsföringskanalen är utformad för att ge en högnivåinsikt om vilka metoder kunderna får ut till er webbplats är mest effektiva. Använd den här rapporten för att tilldela framgångsmått och intäkter till olika kanaler. Ni kan också se de specifika kampanjer eller nyckelord i varje kanal som är mest framgångsrika. Det innehåller ett eget unikt och intuitivt gränssnitt, som gör att du kan visa både första och sista beröringsstatistik samtidigt.
title: Marknadskanal - översikt
topic: Reports
uuid: e4542014-2098-4f4a-ac0d-97587182d6cc
translation-type: tm+mt
source-git-commit: ad991b8fcc309d1f3aae01d472683927a447ab4d
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---


# Marknadskanal - översikt

Översiktsrapporten om marknadsföringskanalen är utformad för att ge en högnivåinsikt om vilka metoder kunderna får ut till er webbplats är mest effektiva. Använd den här rapporten för att tilldela framgångsmått och intäkter till olika kanaler. Ni kan också se de specifika kampanjer eller nyckelord i varje kanal som är mest framgångsrika. Det innehåller ett eget unikt och intuitivt gränssnitt, som gör att du kan visa både första och sista beröringsstatistik samtidigt.

## Allmänna egenskaper {#section_87F54048CE5445F7A6C795C7787C530A}

* Den här rapporten är enbart beroende av [bearbetningsreglerna](/help/components/c-marketing-channels/c-rules.md)för marknadsföringskanaler. Om du ändrar dessa regler ändras hur data i den här rapporten beräknas.
* Behandlingsordningen är avgörande för hur marknadsföringskanaler fungerar. Varje träff kontrollerar först villkoren högst upp i bearbetningsreglerna och filtrerar sedan därifrån.
* Rapporten består av två uppdelningar: själva kanalerna och deras kanalinformation. Om du klickar på plusknappen (+) bredvid varje kanal visas dess detaljer.
* Endast fyra mätvärden kan läggas till i varje kolumn. Du är dock inte begränsad till antalet kolumner som du kan använda.
* En liten trendlinje visas i slutet av den sista kolumnen. Den här trendlinjen kan växla mellan aktiva mätvärden.
* Förutom olika kanaler som samlas in med standardmetoder kan du använda offlinedatakällor.
* [Du kan använda klassificeringar](/help/components/c-classifications2/c-classifications.md) för att byta namn på och konsolidera radobjekt.
* Följande mått kan användas i den här rapporten (beroende på inställningar för organisation och rapportsviten):

   * **Klickfunktioner**: det antal gånger som variabeln *`s.campaign`* definieras.
   * [Nya åtaganden](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-new-engagements.html): antalet besökare som har fått en ny First Touch Channel.
   * Alla standardvärden för e-handel: Intäkter, beställningar, enheter, kundvagnar, kundvagnsvyer, utcheckningar, kundvagnstillägg, kundvagnsborttagningar.
   * Alla anpassade händelser: Händelser 1-80 och Händelser 81-100 om H22-koden eller senare används.
   * **Besök** och **besökare**: kräver Commerce Visits och Visitors, som är beroende av organisation och rapportsvit. Kontakta kontohanteraren om du vill ha mer information.
   * **Budget** och **kostnad**: mätvärden som är specifika för marknadsföringskanaler. Se [Kostnader och budgetar](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/analyze-mc.html).

## Produktspecifika egenskaper {#section_0C78D294D00942FD9A26D37CB5D645AE}

**Version 14 och 15**

Du kan komma åt den här rapporten genom att gå till **[!UICONTROL Marketing Channels]** > **[!UICONTROL Channel Overview Report]** (förutsatt att menyn inte är anpassad).

Segmentering är inte tillgängligt i den här rapporten. Använd [!UICONTROL First- or Last-Touch Channel] eller [!UICONTROL First- or Last-Touch Details] rapporter i stället.

**Ad Hoc Analysis**

Även om rapporten [!UICONTROL Marketing Channel Overview Report] inte är tillgänglig kan du få åtkomst till den med hjälp av olika allokeringar. På så sätt kan ni effektivt återskapa en mycket liknande rapport.

Den här rapporten kan utnyttja flera avancerade segment.
