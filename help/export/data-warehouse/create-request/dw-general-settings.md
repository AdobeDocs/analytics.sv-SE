---
description: Steg som beskriver hur du skapar en Data Warehouse-begäran.
title: Data Warehouse begär allmänna inställningar
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Data Warehouse begär allmänna inställningar

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse-begäran. Följande information beskriver hur du konfigurerar allmänna inställningar för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en Data Warehouse-begäran](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Så här konfigurerar du allmänna inställningar för en Data Warehouse-begäran:

1. Börja skapa en Data Warehouse-förfrågan i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en Data Warehouse-förfrågan](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. På sidan Ny begäran från Data Warehouse väljer du fliken [!UICONTROL **Allmänna inställningar**].

   ![Fliken Rapportmål](assets/dw-general-settings.png)

1. Ange följande fält:

   | Alternativ | Funktion |
   |---------|----------|
   | Namn på begäran | Det här namnet visas på Data Warehouse huvudsida när begäranden hanteras. |
   | Datumintervall | Välj det datumintervall som ska inkluderas i rapporten. <p>Du kan välja anpassade datum eller ett förinställt datumintervall. Förinställningsintervall är relativa till det datum då rapporten skickas.</p><p>Följande förinställningsalternativ är tillgängliga:</p><ul><li>Idag</li><li>Igår</li><li>De senaste 7 dagarna</li><li>De senaste 30 dagarna</li><li>Den här veckan</li><li>Senaste veckan</li><li>De senaste två veckorna</li><li>De senaste 3 veckorna</li><li>De senaste 4 veckorna</li><li>Den här månaden</li><li>Senaste månaden</li><li>Senaste timmen</li></ul> |
   | Kornighet | Tidsgranulariteten. Giltiga värden är None, Hour, Day, Week, Month, Quarter och Year.<p>För rapportgranularitet krävs ytterligare bearbetningstid. Om du rapporterar månadsvis granularitet för ett helt år kommer rapportprocessen att gå mycket snabbare om du skickar in en rapportförfrågan för varje månad.</p><p>**Obs!** När du tillämpar granularitet i en Data Warehouse-begäran läggs kolumnen Date till i rapporten. Beroende på vald granularitet ändras datumformatet enligt följande:</p><ul><li>**Timgranularitet**:<ul> <li>**Format**: `mmmm d, yyyy` Timme `H`</li><li>**Exempel**: 1 januari 20XX, timme 0 </li></ul><li>**Daglig granularitet**:<ul> <li>**Format**: `mmmm d, yyyy`</li><li>**Exempel**: 1 januari 20XX</li></ul><li>**Veckogranularitet**:<ul> <li>**Format**: Vecka `w, yyyy`</li><li>**Exempel**: Vecka 1, 20XX </li></ul><li>**Månatlig granularitet**:<ul> <li>**Format**: `mmmm yyyy`</li><li>**Exempel**: 20XX januari </li></ul><li>**Kvartalsvis granularitet**:<ul> <li>**Format**: `q` Kvartal `yyyy`</li><li>**Exempel**: första kvartalet 20XX </li></ul><li>**Årlig granularitet**:<ul> <li>**Format**: `yyyy`</li><li>**Exempel**: 20XX</li></ul> |
   | Gör tillgänglig för användare i din organisation | Alla datalagerbegäranden är bara synliga för dig och alla systemadministratörer. Aktivera det här alternativet om du vill att begäran ska vara synlig för alla i organisationen. <p>Det här alternativet är användbart om du vill att andra användare i organisationen ska kunna skapa eller uppdatera begäran.</p> |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-begäran på fliken [!UICONTROL **Bygg din rapport**]. Mer information finns i [Skapa en rapport för en Data Warehouse-förfrågan](/help/export/data-warehouse/create-request/dw-request-build-report.md).
