---
title: Översikt över plugin-program
description: Klistra in kod på webbplatsen för att få nya funktioner.
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Översikt över plugin-program

Plugin-program är kodfragment som utför flera avancerade funktioner som hjälper er att implementera Analytics. Dessa plugin-program utökar JavaScript-filens funktioner så att du får fler funktioner som inte är tillgängliga med en grundläggande implementering. Adobe erbjuder ett antal andra plugins som en del i avancerade lösningar.

>[!IMPORTANT]
>
>Plugin-program tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger ingen support för dessa plugin-program, inklusive installation och felsökning. Om du behöver hjälp med ett plugin-program kontaktar du din organisations Account Manager. De kan ordna ett möte med en konsult för att få hjälp.

Adobe erbjuder flera sätt att installera ett visst plugin-program:

1. Använd tillägget&quot;Common Analytics Plugins&quot; med taggar i Adobe Experience Platform
2. Klistra in plugin-kod med den anpassade kodredigeraren
3. Klistra in plugin-programkoden i din `AppMeasurement.js`-fil

Varje organisation har olika implementeringsbehov, så du kan bestämma hur du vill inkludera dem i implementeringen. Se till att du uppfyller följande kriterier när du inkluderar koden på din plats:

1. Instansiera Analytics-spårningsobjektet (med [`s_gi`](../functions/s-gi.md)) först.
   * Den tagghanterade webbplatsen instansierar automatiskt spårningsobjektet när Adobe Analytics läses in.
   * Implementeringar som använder `AppMeasurement.js` initierar vanligtvis spårningsobjektet högst upp i JavaScript-filen.
2. Inkludera plugin-kod sekund.
   * Tillägget Common Analytics Plugins har en åtgärdskonfiguration där du kan initiera plugin-program.
   * Om du inte vill använda tillägget kan du klistra in plugin-kod i den anpassade kodredigeraren när du konfigurerar Analytics-tillägget.
   * Om implementeringen inte använder taggar i Adobe Experience Platform kan du klistra in plugin-kod i `AppMeasurement.js` var som helst efter att du har initierat spårningsobjektet.
3. Ring plugin-programmet tredje.
   * Alla implementeringar, både innanför och utanför en tagghanterad webbplats, använder JavaScript för att anropa plugin-program. Anropa plugin-programmet med det format som finns på sidan för plugin-programmet.
4. Validera implementeringen och publiceringen.

Många organisationer anropar plugin-program med funktionen [`doPlugins`](../functions/doplugins.md). Även om den här funktionen inte är nödvändig anser Adobe att det är en god vana att använda den. AppMeasurement anropar den här funktionen precis innan en bildförfrågan kompileras och skickas, vilket är idealiskt eftersom flera plugin-program är beroende av andra Analytics-variabler.
