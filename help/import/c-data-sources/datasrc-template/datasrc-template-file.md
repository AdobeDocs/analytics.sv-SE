---
description: Information om mallen Datakällor, som innehåller ett ramverk som är lämpligt för att skicka en viss uppsättning externa data till datakällor.
subtopic: Data sources
title: Översikt över Data Sources-mall
topic-fix: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
exl-id: d3122582-d392-4bd9-af2a-fb3d1292ba66
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 5%

---

# Översikt över Data Sources-mall

Information om mallen Datakällor, som innehåller ett ramverk som är lämpligt för att skicka en viss uppsättning externa data till datakällor.

Mallfilen som skapas med den här guiden är utformad för att hjälpa dig att komma igång med importen. Du är inte begränsad till kolumnerna som definieras i mallen. Du kan lägga till ytterligare kolumner efter behov, förutsatt att det finns stöd för mått och definitioner för den valda databehandlingstypen.

Du kan visa mått och dimensioner som stöds för varje typ i följande avsnitt:

* [Webblogg](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [Trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)  (stöds inte längre)
* [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [Transaktions-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [Besökar-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [Fullständig bearbetning](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

För datatypen Visitor ID kan du till exempel lägga till en kolumn för alla mått och mått som listas i [Visitor ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

När du har skapat mallen kan du hämta den, ange dina data i mallen och sedan överföra data till FTP-webbplatsen för datakällor. När de har bearbetats av servern för datakällor är importerade data tillgängliga för användning i dina marknadsföringsrapporter.

Datakällmallen är en [!DNL .txt]-fil som du kan öppna med valfri textredigerare. Det är dock enklast att arbeta med mallen i Microsoft Excel eller något annat kalkylprogram. Mallinnehållet varierar beroende på dina val i [!UICONTROL Data Source Activation Wizard].

Mer information finns i [Importera filreferens](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md).
