---
title: Översikt över plugin-program
description: Klistra in kod på webbplatsen för att få nya funktioner.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# Översikt över plugin-program

Plugin-program är kodfragment som utför flera avancerade funktioner som hjälper er att implementera Analytics. Dessa plugin-program utökar funktionerna i din JavaScript-fil för att ge dig fler funktioner som inte är tillgängliga med en grundläggande implementering. Adobe erbjuder ett antal andra plugins som en del i avancerade lösningar.

{{plug-in}}

Adobe erbjuder flera sätt att installera ett visst plugin-program:

* Använd tillägget&quot;Common Analytics Plugins&quot; med Adobe Analytics-tillägget
* Klistra in plugin-kod med den anpassade kodredigeraren
* Klistra in plugin-programkoden i filen `AppMeasurement.js`

Varje organisation har olika implementeringsbehov, så du kan bestämma hur du vill inkludera dem i implementeringen. Se till att du uppfyller följande kriterier när du inkluderar koden på din plats:

1. Instansiera analysspårningsobjektet (med [`s_gi`](../functions/s-gi.md)) först.
   * Den tagghanterade webbplatsen instansierar automatiskt spårningsobjektet när Adobe Analytics läses in.
   * Implementeringar som använder `AppMeasurement.js` initierar vanligtvis spårningsobjektet högst upp i JavaScript-filen.
2. Inkludera plugin-kod sekund.
   * Tillägget Common Analytics Plugins har en åtgärdskonfiguration där du kan initiera plugin-program.
   * Om du inte vill använda tillägget kan du klistra in plugin-kod i den anpassade kodredigeraren när du konfigurerar Analytics-tillägget.
   * Om implementeringen inte använder taggar i Adobe Experience Platform kan du klistra in plugin-kod i `AppMeasurement.js` var som helst när du har initierat spårningsobjektet.
3. Ring plugin-programmet tredje.
   * Alla implementeringar, både innanför och utanför en tagghanterad webbplats, använder JavaScript för att anropa plugin-program. Anropa plugin-programmet med det format som finns på sidan för plugin-programmet.
4. Validera implementeringen och publiceringen.

Många organisationer anropar plugin-program med funktionen [`doPlugins`](../functions/doplugins.md). Även om den här funktionen inte är nödvändig anser Adobe att det är en god vana att använda den. AppMeasurement anropar den här funktionen precis innan man kompilerar och skickar en bildförfrågan, vilket är idealiskt eftersom flera plugin-program är beroende av andra Analytics-variabler.
