---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera ett rapportmål för en Data Warehouse-begäran
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: 1bd46f104c5ebcca78d624b49c56b2992c3d62cb
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 2%

---

# Konfigurera schemaläggningsalternativ för en Data Warehouse-förfrågan

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar schemaläggningsalternativ för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Så här konfigurerar du schemaläggningsalternativ för en Data Warehouse:

1. Börja skapa en begäran i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. På sidan Ny Data Warehouse väljer du [!UICONTROL **Schemaläggningsalternativ**] -fliken.

   ![Målflik för rapport](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Ange följande fält:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Skicka rapporten nu**] | Skickar rapporten som en engångsrapport. När det här alternativet är markerat döljs alla schemaläggningsalternativ. |
   | [!UICONTROL **Schemalägg senare**] | Anger alternativ för schemaläggning av rapportleverans. Alla alternativ beskrivs nedan. |
   | [!UICONTROL **Rapportfrekvens**] | Hur ofta rapporter levereras. <p>Följande alternativ är tillgängliga:</p><ul><li>Varje timme</li><p>[!UICONTROL **Varje timme**] är bara tillgängligt när [!UICONTROL **Datumintervall**] på [!UICONTROL **Allmänna inställningar**] tabben är inställd på [!UICONTROL **Senaste timmen**].</p><li>Dagligen</li><li>Veckovis</li><li>Månadsvis</li><li>Årlig</li></ul><p>Ytterligare alternativ visas beroende på vilken frekvens du väljer.</p> |
   | [!UICONTROL **Startar**] | Det datum då det nya schemat ska börja. |
   | [!UICONTROL **Tid på dagen**] | Tiden på dagen som rapporten ska skickas. |
   | [!UICONTROL **Alternativ för slutleverans**] | Välj när de schemalagda leveranserna ska avslutas. Du kan välja att aldrig sluta, att sluta efter ett visst antal förekomster eller att avsluta ett visst datum. |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-förfrågan på [!UICONTROL **E-postmeddelande**] -fliken. Mer information finns i [Konfigurera ett e-postmeddelande för en Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).
