---
description: Information om mallen Datakällor, som innehåller ett ramverk som är lämpligt för att skicka en viss uppsättning externa data till datakällor.
subtopic: Data sources
title: Översikt över mallen Datakällor
topic: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Översikt över mallen Datakällor

Information om mallen Datakällor, som innehåller ett ramverk som är lämpligt för att skicka en viss uppsättning externa data till datakällor.

Mallfilen som skapas med den här guiden är utformad för att hjälpa dig att komma igång med importen. Du är inte begränsad till kolumnerna som definieras i mallen. Du kan lägga till ytterligare kolumner efter behov, förutsatt att det finns stöd för mått och definitioner för den valda databehandlingstypen.

Du kan visa mått och dimensioner som stöds för varje typ i följande avsnitt:

* [Webblogg](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [Trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) (stöds inte längre)
* [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [Transaktions-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [Besökar-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [Fullständig bearbetning](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

För datatypen Visitor ID kan du till exempel lägga till en kolumn för alla mått och mått som anges i [Visitor ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

När du har skapat mallen kan du hämta den, ange dina data i mallen och sedan överföra data till FTP-webbplatsen för datakällor. När de har bearbetats av servern för datakällor är importerade data tillgängliga för användning i dina marknadsföringsrapporter.

Mallen Datakälla är en [!DNL .txt] fil som du kan öppna med valfri textredigerare. Det är dock enklast att arbeta med mallen i Microsoft Excel eller något annat kalkylprogram. Mallinnehållet varierar beroende på vad du väljer i [!UICONTROL Data Source Activation Wizard].

Mer information finns i [Importera filreferens](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) .
