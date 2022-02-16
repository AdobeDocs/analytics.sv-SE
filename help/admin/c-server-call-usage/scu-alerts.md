---
description: Lägg till eller hantera alla användningsvarningar för servern. När du skapar en avisering gäller den alla rapportsviter i alla inloggningsföretag för ett faktureringsföretag.
title: Varningar om användning av serversamtal
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 2%

---

# Varningar om användning av serversamtal

När du skapar en avisering gäller den alla rapportsviter i alla inloggningsföretag för ett faktureringsföretag.

## Översikt

En ny aviseringskategori som heter **[!UICONTROL Server Calls Usage Alert]** är en del av den befintliga [Varningshantering](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html) användargränssnitt.

Den är förifylld med **1 standardvarning** som visas i ett inloggningsföretag som har åtkomst till funktionen Serversamtalsanvändning. Den här varningen utlöser ett meddelande adresserat till alla inloggningsföretagets administratörer om något av följande villkor uppfylls:

* &quot;Valfri&quot; användning av serveranrop som &quot;är över eller lika med&quot; 100 % för alla typer av serveranrop som du är berättigad till, ELLER
* &quot;Valfri&quot; användning av serveranrop som &quot;är över eller lika med&quot; 90 % för alla typer av serveranrop som du är berättigad till, ELLER
* &quot;Valfri&quot; användning av serveranrop som &quot;är över eller lika med&quot; 75 % för alla typer av serveranrop som du är berättigad till, OCH &quot;Förbrukad tidsperiod&quot; &quot;är under eller lika med&quot; 75 % av användningsperioden.

![](assets/alerts.png)

Du kan få åtkomst till varningar om användning av serversamtal på två sätt:

* Klicka **[!UICONTROL Manage Alerts]** i det övre högra hörnet på fliken Aktuell användning eller fliken Användning i Report Suite, eller
* Navigera till **[!UICONTROL Components]** > **[!UICONTROL Alerts]** i Adobe Analytics.

## Skapa användningsaviseringar för serversamtal {#section_2A2882C6D48D47C1944D52FB7C766BEC}

Om du vill skapa ytterligare aviseringar

1. Klicka på **[!UICONTROL + Add]** och välj **[!UICONTROL Server Call Usage Alert]**.

   ![](assets/server_call_alert.png)

1. Definiera aviseringen.

   ![](assets/sc_alert.png)

   * **Titel**: Ange ett beskrivande namn. Du kan inte spara aviseringen utan ett namn.
   * **Tidsgranularitet**: Anger hur ofta varningen ska kontrolleras. *Vi stöder endast granularitet varje vecka just nu.* Detta innebär att registreringen kontrolleras varje vecka och att uppgifterna från den aktuella användningsperioden kommer att återkomma.
   * **Mottagare**: Ange alla i organisationen som ska få ett e-postmeddelande när aviseringen utlöser det angivna tröskelvärdet.
   * **Förfallodatum**: Som standard är förfallodatumet ett år från det datum då varningen skapades.
   * **Skicka en varning när**:

      * Alla dessa mått för utlösare Lägg till typen av serveranrop som ett mått och ange aviseringströskeln genom att välja modifierare och tröskelvärde:
         * är över eller lika med
         * är under eller lika med
      * Med Ange tröskelvärde och villkor (ligger över eller är lika med eller under) för den använda användningsperioden.

1. Klicka på **[!UICONTROL Save]**.

## Hantera användningsaviseringar för serveranrop {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

Så här hanterar du aviseringar:

1. Markera kryssrutan bredvid en eller flera aviseringar. Varningshanteringsåtgärderna visas högst upp.
1. Slutför en eller flera av dessa åtgärder:

   | Åtgärd | Definition |
   |--- |--- |
   | + Lägg till | Öppna [Varningsverktyg](/help/admin/c-server-call-usage/scu-alerts.md) genom att klicka  [!UICONTROL + Add]. |
   | Tagg | Märk varningar för att ordna dem så att de blir lätta att använda. |
   | Ta bort | Du kan ta bort alla aviseringar förutom standardaviseringar. |
   | Byt namn | Du kan byta namn på alla aviseringar förutom standardaviseringar. |
   | Godkänn | Godkänn aviseringar för att göra dem&quot;officiella&quot;. |
   | Aktivera/inaktivera | Du kan aktivera eller inaktivera alla aviseringar, även standardaviseringar. |
   | Förnya | När en eller flera aviseringar har valts kan de förnyas. Detta förlänger deras förfallodatum till 1 år från dagen [!UICONTROL Renew] har klickats, oavsett ursprungligt förfallodatum. |
   | Exportera till CSV | Se [Hämta användningsrapport](/help/admin/c-server-call-usage/report-suite-usage.md) |
