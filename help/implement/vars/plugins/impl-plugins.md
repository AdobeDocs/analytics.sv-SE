---
title: Översikt över plugin-program
description: Klistra in kod på webbplatsen för att få nya funktioner.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Översikt över plugin-program

Plugin-program är kodfragment som utför flera avancerade funktioner som hjälper er att implementera Analytics. Dessa plugin-program utökar JavaScript-filens funktioner så att du får fler funktioner som inte är tillgängliga med en grundläggande implementering. Adobe erbjuder ett antal andra plugins som en del i avancerade lösningar.

> [!IMPORTANT] Plugin-program tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för dessa plugin-program, inklusive installation och felsökning. Om du behöver hjälp med ett plugin-program kontaktar du din organisations Account Manager. De kan ordna ett möte med en konsult för att få hjälp.

Adobe erbjuder flera sätt att installera ett visst plugin-program:

1. Använd tillägget&quot;Common Analytics Plugins&quot; med Adobe Experience Platform Launch
2. Klistra in plugin-kod med den anpassade kodredigeraren för Launch
3. Klistra in plugin-programkoden i `AppMeasurement.js` filen

Varje organisation har olika implementeringsbehov, så du kan bestämma hur du vill inkludera dem i implementeringen. Se till att du uppfyller följande kriterier när du inkluderar koden på din plats:

1. Instansiera Analytics-spårningsobjektet (med `s_gi`) först.
   * Launch instansierar automatiskt spårningsobjektet när Adobe Analytics läses in.
   * Implementeringar som använder `AppMeasurement.js` initierar vanligtvis spårningsobjektet längst upp i JavaScript-filen.
2. Inkludera plugin-kod sekund.
   * Tillägget Common Analytics Plugins har en åtgärdskonfiguration där du kan initiera plugin-program.
   * Om du inte vill använda plugin-programmet kan du klistra in plugin-programkod i den anpassade kodredigeraren när du konfigurerar Analytics-tillägget.
   * Om implementeringen inte använder Launch kan du klistra in plugin-kod i `AppMeasurement.js` var som helst när du har initierat spårningsobjektet.
3. Ring plugin-programmet tredje.
   * Alla implementeringar, både i och utanför Launch, använder JavaScript för att anropa plugin-program. Anropa plugin-programmet med det format som finns på sidan för plugin-programmet.
4. Validera implementeringen och publiceringen.

Många organisationer anropar plugin-program med [`doPlugins`](../functions/doplugins.md) funktionen. Även om den här funktionen inte är obligatorisk anser Adobe att den är den bästa metoden att använda. AppMeasurement anropar den här funktionen precis innan en bildförfrågan kompileras och skickas, vilket är idealiskt eftersom flera plugin-program är beroende av andra Analytics-variabler.
