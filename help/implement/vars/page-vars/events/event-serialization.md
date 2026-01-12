---
title: Händelseserialisering
description: Ta bort dubbletter av mätvärden på webbplatsen.
feature: Appmeasurement Implementation
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
source-git-commit: 7cd930ac63e0c02dbc7df2b6114d523f5ac91064
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# Händelse-ID-serialisering

Händelseserialisering är processen att implementera åtgärder för att förhindra att dubbletthändelser anges i analysrapporter. Det är viktigt att deduplicera händelser i fall där du inte vill att besökarna ska uppdatera sidan ska få statistik som ökar.

>[!NOTE]
>
>Datakällor stöder inte händelseserialisering eller borttagning av dubbletter.

## Konfigurera händelseserialisering

Du måste först ange en händelses [!UICONTROL Unique Event Recording] till [!UICONTROL Use Event ID] i inställningarna för rapportsviten. Se [Slutförda händelser](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) i användarhandboken för Admin.

När du använder händelse-ID:n utförs borttagning av dubbletter på följande nivåer:

* Varje variabel använder sin egen tabell för borttagning av dubbletter. Till exempel räknas både `event1:ABC` och `event2:ABC` i rapporteringen.
* Deduplicering sker globalt för alla besökare. Om besökare A skickar `event1:ABC` och besökare B också skickar `event1:ABC`, ignorerar Adobe den andra instansen från besökare B.
* Avdupliceringen upphör inte att gälla. Om en besökare skickar `event1:ABC` och sedan kommer tillbaka två år senare och skickar `event1:ABC` igen, ignorerar Adobe den andra instansen.

>[!TIP]
>
>Om du vill deduplicera [`purchase`](event-purchase.md)-händelsen använder du variabeln [`purchaseID`](../purchaseid.md) i stället.

## Använda händelse-ID:n via SDK på webben

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) använder händelseserialiseringen händelsens XDM-fält `id`. Den fullständiga XDM-sökvägen beror på vilken händelse du vill serialisera.

Om du till exempel vill serialisera måttet för kundvagnstillägg anger du `xdm.commerce.productListAdds.id` till det önskade serialiseringsvärdet. Om du vill serialisera anpassad händelse 20 anger du `xdm._experience.analytics.event1to100.event20.id` till önskat serialiseringsvärde.

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) används `data.__adobe.analytics.events` för händelseserialisering, följande AppMeasurement-strängsyntax.

## Använd händelse-ID:n med Adobe Analytics-tillägget

Du kan ange fältet för händelse-ID när du konfigurerar Analytics-tillägget (globala variabler) eller som en åtgärd i en regel.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Actions]-åtgärd under [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta upp avsnittet [!UICONTROL Events] där varje händelse innehåller ett [!UICONTROL Event ID]-fält.

Giltiga värden är alfanumeriska tecken som är upp till 20 byte långa. Om du anger ett värde som är längre än 20 byte trunkeras det till de första 20 byten.

## Använd händelse-ID:n i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Händelseserialisering är en del av variabeln `s.events`. Tilldela ett ID till varje händelse med ett kolon i strängen.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Om en händelse har serialisering aktiverat men inte innehåller något serialiserings-ID räknas alltid händelsen.
