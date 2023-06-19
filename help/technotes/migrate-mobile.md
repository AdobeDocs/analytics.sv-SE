---
description: Lär dig hur du migrerar bearbetningsregler för mobila tjänster till Adobe Analytics
title: Migrera bearbetningsregler för mobila tjänster till Adobe Analytics
feature: Processing Rules
exl-id: ea183c1a-a85e-4f4e-a7f6-f947b939e9d9
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Migrera bearbetningsregler för mobila tjänster till Adobe Analytics

Det här dokumentet innehåller instruktioner om hur du migrerar eventuella ytterligare bearbetningsregler - utöver Lifecycle Metrics - som du har skapat i gränssnittet för mobila tjänster till Adobe Analytics.

Bearbetningsregler används för att flytta värden från kontextdatavariabler till props och eVars. Du kan till exempel placera värdet för en&quot;sökterm&quot;-kontextdatavariabel i värdet för en Commerce Variable-eVar och skriva över det värdet för varje träff. Utan bearbetningsregler är kontextdatavariabler meningslösa och fyller inte i några rapporter i Analytics.

Det här dokumentet visar även hur du rapporterar om mobilanvändning i Analysis Workspace.

## Migrera bearbetningsregler

Om ni använder mobiltjänster för kostnadsfria funktioner som bearbetningsregler och användningsrapporteringsfunktioner kan ni smidigt gå över till analysgränssnittet (bearbetningsregelgränssnitt eller Analysis Workspace) för att utföra dessa funktioner. För livscykelmått, eller regler som har konfigurerats i användargränssnittet för bearbetningsregler för AA, behöver du inte utföra någon migrering. Livscykelstatistik är körklara mått som samlas in automatiskt när Mobile SDK implementeras i din app för första gången.

Men om du skapar ytterligare bearbetningsregler i gränssnittet för mobila tjänster (utöver Lifecycle Metrics) bör du migrera dem så att du kan redigera/ta bort dem i Analytics när du har förlorat åtkomsten till Mobile Services.

1. Logga in på `experience.adobe.com` och går till Mobiltjänster.
1. Klicka på kugghjulsikonen för en mobilapp vars kontextvariabelmappningar du vill migrera till Adobe Analytics.
1. Klicka på **[!UICONTROL Manage Variables and Metrics]** menyalternativet och klicka sedan på **[!UICONTROL Custom Variables]** -fliken. Här ser du vilka kontextvariabelmappningar (kontextdata) som har lagts till i konfigurationen. Anteckna dessa konfigurationer (eller ta en skärmbild). Exempel:

   ![Kontextvariabel](assets/context-var.png)

1. Gå till Experience Cloud, byt till Adobe Analytics och se till att du är med i samma paket för mobilrapporter som du tittade på i Mobiltjänster.
1. Gå till **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]**.
1. Klicka på **[!UICONTROL Add Rule]**.
1. Ignorera villkoren och fortsätt att lägga till samma sammanhangsvariabler som finns i Mobiltjänster.

   ![Bearbetar regel](assets/proc-rule.png)

1. Klicka på **[!UICONTROL Save]**.

## Rapportering om mobilanvändning i Analysis Workspace

Förutom mobilstatistik och mått (om rapportsviten är aktiverad för Mobile Services) innehåller Analysis Workspace flera mallar för Mobile-projekt som kan underlätta analys:

* **[!UICONTROL Messaging]**: Fokuserar på prestanda i appen och push-meddelanden.
* **[!UICONTROL Location]**: Innehåller en karta som visar platsdata.
* **[!UICONTROL Key Metrics]**: Håll koll på nyckelmätningarna i appen.
* **[!UICONTROL App Usage]**: Hur många appanvändare, starter och första starter hade appen och hur lång var den genomsnittliga sessionslängden?
* **[!UICONTROL Acquisition]**: Hur fungerar mobilförvärv?
* **[!UICONTROL Performance]**: Hur fungerar appen och var har användarna problem?
* **[!UICONTROL Retention]**: Vilka är mina lojala användare och vad gör de?
* **[!UICONTROL Journeys]**: Vilka är de framträdande användningsmönstren för min app?

Här är ett utdrag från mallen Mobile App Usage:

![Användning av mobilappar](assets/mobile-app-usage.png)

Så här kommer du åt mallarna:

1. Logga in på `experience.adobe.com` och väljer Analytics.
1. Se till att du har en rapportsserie som är aktiverad för mobiltjänster.
1. Klicka på **[!UICONTROL Workspace]** -fliken.
1. Klicka på **[!UICONTROL Create New Project]**.
1. Välj någon av mobilmallarna och klicka på **[!UICONTROL Create]**.

## Migrera andra mobiltjänster

Följande Mobile Services-funktionalitet är kopplad till Adobe Analytics, men kräver en köpt Adobe Analytics SKU:

* Förvärvningslänkar
* Push-meddelanden
* Meddelanden i appen
* Platspunkter för intressehantering

Om du använder mobiltjänster för betalfunktionalitet har du inte någon genomförbar migreringsväg till andra interna/externa verktyg:

* För värvningslänkar kan vi hänvisa dig till Adobe Partners för att tillgodose dina behov.
* Push Messaging och In-app Messaging är tillgängliga i Adobe Campaign Standard och Adobe Campaign Classic (endast push). Den underliggande datauppsättning som används för målinriktning är dock annorlunda. Vi föreslår att du samarbetar med ditt Adobe-kontoteam för att fastställa migreringsalternativ för meddelandedata.
* För platsfunktioner rekommenderar vi att du använder den nya [Adobe Experience Platform Location Service](https://www.adobe.com/experience-platform/location-service.html), vilket är kostnadsfritt för alla Adobe Experience Platform-kunder.
