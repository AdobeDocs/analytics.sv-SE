---
description: 'null'
title: Använda integreringen
uuid: c902a868-20a7-42df-8a79-8e154608f299
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Använda integreringen{#using-the-integration}

När den har distribuerats kan du börja använda de ytterligare funktioner som den här integreringen ger.

**Obs**: Det kan ta 24-48 timmar att börja se några av de dynamiska signaldata som ingår i Adobe Analytics-rapporterna.

Följande åtgärder ger mervärde genom den här integreringen i Adobe Analytics.

## Visa trafik- och konverteringsmått efter dynamiska signaldimensioner{#viewing-traffic-and-conversion-metrics-by-dynamic-signal-dimensions}

Exempel på en rapport i Adobe Analytics.

Integreringen ger nya dimensioner som blir tillgängliga som Adobe Analytics-rapporter. Rapporten nedan är ett exempel på hur både besök och konverteringsmått (registreringar) som har delats upp efter artikeltitel analyseras.

![](assets/examplereport.png)

## Segmentering efter dynamiska signaldimensioner{#segmenting-by-dynamic-signal-dimensions}

Exempel på segment baserade på dynamiska signaldimensioner.

En viktig egenskap i den här integreringen är möjligheten att skapa Adobe Analytics-segment baserat på de integrerade rapporteringsdimensionerna. Du kan t.ex. skapa ett segment som endast innehåller besök från en viss VoiceStorm-community. Du kan kalla det&quot;Besök som drivs av SuperFans&quot;. Den här segmentdefinitionen kan se ut så här.

![](assets/segment1.png)

![](assets/segment2.png)

## Integrerade rapporteringsdimensioner{#integrated-reporting-dimensions}

Visar de dimensioner för dynamisk signalrapportering som ingår i den här integreringen.

| Dimension | Beskrivning |
|---|---|
| Kanaltyp | Det sociala nätverket (eller bloggplattformen) där användaren delade ett inlägg i communityn. Användare kan dela ett inlägg i flera kanaler. Klickningar och annan aktivitet segmenteras per kanal. I det här fältet visas Facebook, Twitter osv. så att du kan se vilken kanaltyp som driver aktiviteten. |
| Artikel-ID | Artikel-ID:t identifierar unikt varje del av innehållet i forumet för dynamiska signaler. |
| Källtyp | I det här fältet anges om inlägget har skapats av en&quot;Medlem&quot; eller&quot;Varumärke&quot;. Observera att innehåll i båda fallen kan skapas manuellt i programmet eller importeras från en extern feed. |
| Användarnamn | Den användare som delade ett inlägg på sitt sociala nätverk och skapade klickningar på din webbplats. |
| Käll-ID | Det unika käll-ID:t identifierar skaparen (eller författaren) av det delade inlägget. Detta är oftast antingen en viss medlem eller ett externt foder. |
| Användar-ID | Användar-ID:t identifierar en användare (dvs. en medlem) i gruppen för dynamiska signaler. I det här fallet är användaren den delare som delade posten i sitt/sina sociala nätverk. |
| Källnamn | Källan är skaparen (eller författaren) av det delade inlägget. I de flesta fall är detta medlem i communityn eller ett externt flöde. |
| Artikelrubrik | Titeln på det delade inlägget som genererade klickningar tillbaka till webbplatsen. |
| Community-namn | Namnet på din community för dynamiska signaler. |

