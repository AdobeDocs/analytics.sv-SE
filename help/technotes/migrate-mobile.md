---
description: Lär dig hur du migrerar bearbetningsregler för mobila tjänster till Adobe Analytics
title: Migrera bearbetningsregler för mobila tjänster till Adobe Analytics
translation-type: tm+mt
source-git-commit: bdb6f9ba435513cd1dc3febf35eae0e821c756ca
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 0%

---


# Migrera bearbetningsregler för mobila tjänster till Adobe Analytics

I och med den kommande (hittills oanmälda) uppgången av Adobe Mobile Services-funktionen ger det här dokumentet dig anvisningar om hur du migrerar eventuella ytterligare bearbetningsregler - utöver Lifecycle Metrics - som du har skapat i användargränssnittet för mobila tjänster till Adobe Analytics.

Bearbetningsregler används för att flytta värden från kontextdatavariabler till props och eVars. Du kan till exempel placera värdet för en&quot;sökterm&quot;-kontextdatavariabel i värdet för en Commerce Variable-eVar och skriva över det värdet för varje träff. Utan bearbetningsregler är kontextdatavariabler meningslösa och fyller inte i några rapporter i Analytics.

## Migrera bearbetningsregler

Om ni använder mobiltjänster för kostnadsfria funktioner som bearbetningsregler och användningsrapporteringsfunktioner kan ni smidigt gå över till analysgränssnittet (bearbetningsregelgränssnitt eller Analysis Workspace) för att utföra dessa funktioner. För livscykelmått, eller regler som har konfigurerats i användargränssnittet för bearbetningsregler för AA, behöver du inte utföra någon migrering. Livscykelstatistik är körklara mått som samlas in automatiskt när Mobile SDK implementeras i din app för första gången.

Men om du skapar ytterligare bearbetningsregler i gränssnittet för mobila tjänster (utöver Lifecycle Metrics) bör du migrera dem så att du kan redigera/ta bort dem i Analytics när du har förlorat åtkomsten till Mobile Services.

1. Logga in på experience.adobe.com och gå till Mobile Services.
1. Klicka på kugghjulsikonen för en mobilapp vars kontextvariabelmappningar du vill migrera till Adobe Analytics.
1. Klicka på **[!UICONTROL Manage Variables and Metrics]** menyalternativet och sedan på **[!UICONTROL Custom Variables]** fliken. Här ser du vilka kontextvariabelmappningar (kontextdata) som har lagts till i konfigurationen. Anteckna dessa konfigurationer (eller ta en skärmbild). Exempel:

   ![Kontextvariabel](assets/context-var.png)

1. Gå till Experience Cloud, byt till Adobe Analytics och se till att du är med i samma mobila rapportsserie som du tittade på i Mobiltjänster.
1. Gå till Admin > Report Suites > Edit Settings > General > Processing Rules.
1. Klicka på Lägg till regel.
1. Ignorera villkoren och fortsätt att lägga till samma sammanhangsvariabler som finns i Mobiltjänster.

   ![Bearbetar regel](assets/proc-rule.png)

## Rapportering om mobilanvändning i Analysis Workspace

Förutom mobilstatistik och mått (om rapportsviten är aktiverad för Mobile Services) innehåller Analysis Workspace flera mallar för Mobile-projekt som kan underlätta analys:

* Meddelanden: Fokuserar på prestanda i appen och push-meddelanden.
* Plats: Innehåller en karta som visar platsdata.
* Nyckeltal: Håll koll på nyckelmätningarna i appen.
* Appanvändning: Hur många appanvändare, starter och första starter hade appen och hur lång var den genomsnittliga sessionslängden?
* Förvärv: Hur fungerar mobilförvärv?
* Prestanda: Hur fungerar appen och var har användarna problem?
* Kvarhållning: Vilka är mina lojala användare och vad gör de?
* Resor: Vilka är de framträdande användningsmönstren för min app?

Här är ett utdrag från mallen Mobile App Usage:

![Användning av mobilappar](assets/mobile-app-usage.png)

Så här kommer du åt mallarna:

1. Logga in på experience.adobe.com och välj Analytics.
1. Se till att du har en rapportsserie som är aktiverad för mobiltjänster.
1. Klicka på fliken Arbetsyta.
1. Klicka på Skapa nytt projekt.
1. Välj någon av mobilmallarna och klicka på Skapa.

## Migrera andra mobiltjänster

Följande Mobile Services-funktionalitet är kopplad till Adobe Analytics, men kräver en köpt Adobe Analytics SKU:

* Förvärvningslänkar
* Push-meddelanden
* Meddelanden i appen
* Platspunkter för intressehantering

Om du använder mobiltjänster för betalfunktionalitet har du inte någon genomförbar migreringsväg till andra interna/externa verktyg:

* För värvningslänkar kan vi hänvisa dig till Adobe Partners för att tillgodose dina behov.
* Även om det finns varianter av Push Messaging och In-app Messaging i Adobe Campaign Standard och Adobe Campaign Classic (endast push) är den underliggande datauppsättning som används för målanpassning annorlunda och det går inte att migrera data eller meddelandeaktiviteter.
* För platsfunktioner rekommenderar vi att du använder den nya [Adobe Experience Platform Location Service](https://www.adobe.com/experience-platform/location-service.html), som är kostnadsfri för alla AEP-kunder.
