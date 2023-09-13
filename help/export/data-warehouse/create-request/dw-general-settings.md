---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Allmänna inställningar för begäran om Data Warehouse
feature: Data Warehouse
source-git-commit: ea4c1ae21f2c83bad92723e6ffd2e706fac5e1e8
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 1%

---

# Allmänna inställningar för begäran om Data Warehouse

>[!AVAILABILITY]
>
>Vissa av de Data Warehouse som beskrivs i den här artikeln (och andra artiklar i den här Datan Warehouse) är endast tillgängliga i den begränsade testfasen av releasen och är kanske inte tillgängliga i din miljö ännu.
>
>Information om vilka funktioner som ännu inte är tillgängliga för alla kunder, samt information om tidslinjen för releasen av dessa funktioner, finns i [versionsinformation](/help/release-notes/latest.md).
>
>Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar allmänna inställningar för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Så här konfigurerar du allmänna inställningar för en Data Warehouse:

1. Börja skapa en begäran om Data Warehouse i Adobe Analytics genom att markera **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. På sidan Ny Data Warehouse väljer du [!UICONTROL **Allmänna inställningar**] -fliken.

   ![Målflik för rapport](assets/dw-general-settings.png)

1. Ange följande fält:

   | Alternativ |  -funktion |
   |---------|----------|
   | Namn på begäran | Det här namnet visas på huvudsidans Data Warehouse när begäranden hanteras. |
   | Datumintervall | Välj det datumintervall som ska inkluderas i rapporten. <p>Du kan välja anpassade datum eller ett förinställt datumintervall. Förinställningsintervall är relativa till det datum då rapporten skickas.</p><p>Följande förinställningsalternativ är tillgängliga:</p><ul><li>Idag</li><li>Igår</li><li>De senaste 7 dagarna</li><li>De senaste 30 dagarna</li><li>Den här veckan</li><li>Senaste veckan</li><li>De senaste två veckorna</li><li>De senaste 3 veckorna</li><li>De senaste 4 veckorna</li><li>Den här månaden</li><li>Senaste månaden</li><li>Senaste timmen</li></ul> |
   | Kornighet | <!--what does this setting do? It's not the schedule/frequency... --> Tidsgranulariteten. Giltiga värden är None, Hour, Day, Week, Month, Quarter och Year.<p>För rapportgranularitet krävs ytterligare bearbetningstid. Om du rapporterar månadsvis granularitet för ett helt år kommer rapportprocessen att gå mycket snabbare om du skickar in en rapportförfrågan för varje månad.</p> |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-förfrågan på [!UICONTROL **Bygg din rapport**] -fliken. Mer information finns i [Skapa en rapport för en Data Warehouse-förfrågan](/help/export/data-warehouse/create-request/dw-request-build-report.md).