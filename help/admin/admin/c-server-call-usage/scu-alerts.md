---
description: Lägg till eller hantera alla användningsvarningar för servern. När du skapar en avisering gäller den alla rapportsviter i alla inloggningsföretag för ett faktureringsföretag.
title: Varningar om användning av serversamtal
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
source-git-commit: 373a1ecffafdcefe3c7b60954f14c2f3a5ca386d
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 1%

---

# Användningsvarningar för serversamtal

När du skapar en avisering gäller den alla rapportsviter i alla inloggningsföretag för ett faktureringsföretag.

Användningsaviseringar om serveranrop ingår i användargränssnittet för [Varningar](/help/components/c-alerts/alert-manager.md).

Den är förifylld med **1 standardvarning** som visas i alla inloggningsföretag som har åtkomst till funktionen Serversamtalsanvändning. Den här varningen utlöser ett meddelande adresserat till alla inloggningsföretagets administratörer om något av följande villkor uppfylls:

* &quot;Valfri&quot; användning av serveranrop som &quot;är över eller lika med&quot; 100 % för alla typer av serveranrop som du är berättigad till, ELLER
* &quot;Valfri&quot; användning av serveranrop som &quot;är över eller lika med&quot; 90 % för alla typer av serveranrop som du är berättigad till, ELLER
* &quot;Valfri&quot; användning av serveranrop som &quot;är över eller lika med&quot; 75 % för alla typer av serveranrop som du är berättigad till, OCH &quot;Förbrukad tidsperiod&quot; &quot;är under eller lika med&quot; 75 % av användningsperioden.

![](/help/admin/admin/c-server-call-usage/assets/alerts.png)

Du kan få åtkomst till varningar om användning av serversamtal på två sätt:

* Klicka på **[!UICONTROL Manage Alerts]** i det övre högra hörnet på fliken Aktuell användning eller på fliken Användning i Report Suite, eller
* Navigera till **[!UICONTROL Components]** > **[!UICONTROL Alerts]** i Adobe Analytics.

## Skapa varningsmeddelanden om användning av serversamtal {#create}

Om du vill skapa ytterligare aviseringar

1. Klicka på **[!UICONTROL + Add]** och välj **[!UICONTROL Server Call Usage Alert]**.

   ![](/help/admin/admin/c-server-call-usage/assets/server_call_alert.png)

1. Definiera aviseringen.

   ![](/help/admin/admin/c-server-call-usage/assets/sc_alert.png)

   * **Titel**: Ange ett beskrivande namn. Du kan inte spara aviseringen utan ett namn.
   * **Tidsgranularitet**: Anger hur ofta varningen ska kontrolleras. *Vi stöder endast granularitet varje vecka just nu.* Det innebär att varningen kontrolleras varje vecka och att data från den aktuella användningsperioden kommer att återsökas.
   * **Mottagare**: Ange alla i organisationen som ska få ett e-postmeddelande när aviseringen utlöser det angivna tröskelvärdet.
   * **Förfallodatum**: Som standard är förfallodatumet ett år från det datum då aviseringen skapades.
   * **Skicka en avisering när**:

      * Någon av dessa mått-utlösare
Lägg till typen av serveranrop som ett mått och ange aviseringströskeln genom att välja modifieraren och tröskelvärdet:
         * är över eller lika med
         * är under eller lika med
      * Med
Ange tröskelvärde och villkor (ligger över eller är lika med eller under) för den använda användningsperioden.

1. Klicka på **[!UICONTROL Save]**.

## Hantera användningsaviseringar för serveranrop {#manage}

![](/help/admin/admin/c-server-call-usage/assets/alert_mgmt.png)

Så här hanterar du aviseringar:

1. Markera kryssrutan bredvid en eller flera aviseringar. Varningshanteringsåtgärderna visas högst upp.
1. Slutför en eller flera av dessa åtgärder:

   | Åtgärd | Definition |
   |--- |--- |
   | + Lägg till | Gå till [varningsverktyget](/help/admin/admin/c-server-call-usage/scu-alerts.md) genom att klicka på [!UICONTROL + Add]. |
   | Tagg | Märk varningar för att ordna dem så att de blir lätta att använda. |
   | Ta bort | Du kan ta bort alla aviseringar förutom standardaviseringar. |
   | Byt namn | Du kan byta namn på alla aviseringar förutom standardaviseringar. |
   | Godkänn | Godkänn aviseringar för att göra dem&quot;officiella&quot;. |
   | Aktivera/inaktivera | Du kan aktivera eller inaktivera alla aviseringar, även standardaviseringar. |
   | Förnya | När en eller flera aviseringar har valts kan de förnyas. Detta utökar deras förfallodatum till 1 år från den dag [!UICONTROL Renew] klickades på, oavsett deras ursprungliga förfallodatum. |
   | Exportera till CSV | Se [Hämta användningsrapport](/help/admin/admin/c-server-call-usage/report-suite-usage.md) |

   {style="table-layout:auto"}
