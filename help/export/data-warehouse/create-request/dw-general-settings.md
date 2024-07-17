---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Allmänna inställningar för begäran om Data Warehouse
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: baac0c0384b714cf2ca536149ca10eec3a7065ad
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 1%

---

# Allmänna inställningar för begäran om Data Warehouse

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar allmänna inställningar för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Så här konfigurerar du allmänna inställningar för en Data Warehouse:

1. Börja skapa en begäran om Data Warehouse i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Markera fliken [!UICONTROL **Allmänna inställningar**] på sidan Ny Data Warehouse.

   ![Fliken Rapportmål](assets/dw-general-settings.png)

1. Ange följande fält:

   | Alternativ | Funktion |
   |---------|----------|
   | Namn på begäran | Det här namnet visas på huvudsidans Data Warehouse när begäranden hanteras. |
   | Datumintervall | Välj det datumintervall som ska inkluderas i rapporten. <p>Du kan välja anpassade datum eller ett förinställt datumintervall. Förinställningsintervall är relativa till det datum då rapporten skickas.</p><p>Följande förinställningsalternativ är tillgängliga:</p><ul><li>Idag</li><li>Igår</li><li>De senaste 7 dagarna</li><li>De senaste 30 dagarna</li><li>Den här veckan</li><li>Senaste veckan</li><li>De senaste två veckorna</li><li>De senaste 3 veckorna</li><li>De senaste 4 veckorna</li><li>Den här månaden</li><li>Senaste månaden</li><li>Senaste timmen</li></ul> |
   | Kornighet | <!--what does this setting do? It's not the schedule/frequency... --> Tidsgranulariteten. Giltiga värden är None, Hour, Day, Week, Month, Quarter och Year.<p>För rapportgranularitet krävs ytterligare bearbetningstid. Om du rapporterar månadsvis granularitet för ett helt år kommer rapportprocessen att gå mycket snabbare om du skickar in en rapportförfrågan för varje månad.</p> |
   | Gör tillgänglig för användare i din organisation | Alla datalagerbegäranden är bara synliga för dig och alla systemadministratörer. Aktivera det här alternativet om du vill att begäran ska vara synlig för alla i organisationen. <p>Det här alternativet är användbart om du vill att andra användare i organisationen ska kunna skapa eller uppdatera begäran.</p> |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-förfrågan på fliken [!UICONTROL **Bygg din rapport**]. Mer information finns i [Skapa en rapport för en Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).
