---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera ett rapportmål för en Data Warehouse-begäran
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '527'
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
   | Skicka rapporten nu | Skickar rapporten som en engångsrapport. När det här alternativet är markerat döljs alla schemaläggningsalternativ. |
   | Schemalägg senare | Anger alternativ för schemaläggning av rapportleverans. Alla alternativ beskrivs nedan. |
   | Rapportfrekvens | Hur ofta rapporter levereras. <p>Följande alternativ är tillgängliga:</p><ul><li>Varje timme</li><p>[!UICONTROL **Varje timme**] är bara tillgängligt när [!UICONTROL **Datumintervall**] på [!UICONTROL **Allmänna inställningar**] tabben är inställd på [!UICONTROL **Senaste timmen**].</p><li>Dagligen</li><li>Veckovis</li><li>Månadsvis</li><li>Årlig</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" --> |
   | Återkommande månad | Intervallet mellan månaderna då rapporten skickas. |
   | Dag i månaden | Det datum varje månad som rapporten skickas.<p>När det här alternativet är tillgängligt [!UICONTROL **Vecka i månaden**] och [!UICONTROL **Veckodag**] är inte det. Välj [!UICONTROL **Alternativt format**] för att växla fram och tillbaka. </p> |
   | Vecka i månaden | Den vecka i varje månad som rapporten ska skickas. <p>Följande alternativ är tillgängliga:</p><ul><li>Första</li><li>Andra</li><li>Tredje</li><li>Fjärde</li><p>Skicka rapporten den 4:e veckan, även på månader med fem veckor. Välj [!UICONTROL **Senaste**] om du vill att rapporten ska skickas den sista veckan i varje månad.</p><li>Senaste</li></ul><p>När det här alternativet är tillgängligt [!UICONTROL **Dag i månaden**] är inte det. Välj [!UICONTROL **Alternativt format**] för att växla fram och tillbaka. </p> |
   | Veckodag | Veckodagen som rapporten ska skickas till. <p>När det här alternativet är tillgängligt [!UICONTROL **Dag i månaden**] är inte det. Välj [!UICONTROL **Alternativt format**] för att växla fram och tillbaka. </p> |
   | Startar | Det datum då det nya schemat ska börja. |
   | Tid på dagen | Tiden på dagen som rapporten ska skickas. |
   | Alternativ för slutleverans | Välj när de schemalagda leveranserna ska avslutas. Du kan välja att aldrig sluta, att sluta efter ett visst antal förekomster eller att avsluta ett visst datum. |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-förfrågan på [!UICONTROL **E-postmeddelande**] -fliken. Mer information finns i [Konfigurera ett e-postmeddelande för en Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

