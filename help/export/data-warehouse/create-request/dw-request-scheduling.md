---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera ett rapportmål för en Data Warehouse-begäran
feature: Data Warehouse
source-git-commit: 3b116cb8d0d3f3eb86b512d712f37b29876f2b22
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# Konfigurera schemaläggningsalternativ för en Data Warehouse-förfrågan

>[!AVAILABILITY]
>
>Vissa av de Data Warehouse som beskrivs i den här artikeln (och andra artiklar i den här Datan Warehouse) är endast tillgängliga i den begränsade testfasen av releasen och är kanske inte tillgängliga i din miljö ännu.
>
>Information om vilka funktioner som ännu inte är tillgängliga för alla kunder, samt information om tidslinjen för releasen av dessa funktioner, finns i [versionsinformation](/help/release-notes/latest.md).
>
>Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar schemaläggningsalternativ för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Så här konfigurerar du schemaläggningsalternativ för en Data Warehouse:

1. Börja skapa en begäran i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. På sidan Ny Data Warehouse väljer du [!UICONTROL **Schemaläggningsalternativ**] -fliken.

   ![Målflik för rapport](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Ange följande fält:

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Skicka rapporten nu**] | Skickar rapporten som en engångsrapport. När det här alternativet är markerat döljs alla schemaläggningsalternativ. |
   | [!UICONTROL **Schemalägg senare**] | Anger alternativ för schemaläggning av rapportleverans. Alla alternativ beskrivs nedan. |
   | [!UICONTROL **Rapportfrekvens**] | Hur ofta rapporter levereras. <p>Följande alternativ är tillgängliga:</p><ul><li>Varje timme</li><p>[!UICONTROL **Varje timme**] är bara tillgängligt när [!UICONTROL **Datumintervall**] på [!UICONTROL **Allmänna inställningar**] tabben är inställd på [!UICONTROL **Senaste timmen**].</p><li>Dagligen</li><li>Veckovis</li><li>Månadsvis</li><li>Årlig</li></ul><p>Ytterligare alternativ visas beroende på vilken frekvens du väljer.</p> |
   | [!UICONTROL **Startar**] | Det datum då det nya schemat ska börja. |
   | [!UICONTROL **Tid på dagen**] | Tiden på dagen som rapporten ska skickas. |
   | [!UICONTROL **Alternativ för slutleverans**] | Välj när de schemalagda leveranserna ska avslutas. Du kan välja att aldrig sluta, att sluta efter ett visst antal förekomster eller att avsluta ett visst datum. |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-förfrågan på [!UICONTROL **E-postmeddelande**] -fliken. Mer information finns i [Konfigurera ett e-postmeddelande för en Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

