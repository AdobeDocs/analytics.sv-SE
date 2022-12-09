---
description: Fliken Report Suite-användning innehåller serveranvändningsdata för varje rapportsvit i alla inloggningsföretag som är kopplade till ditt faktureringsföretag, för den aktuella användningsperioden.
title: Visa användning av rapportsvit
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 2%

---

# Visa användning av rapportsvit

Fliken Report Suite-användning innehåller serveranvändningsdata för varje rapportsvit i alla inloggningsföretag som är kopplade till ditt faktureringsföretag, för den aktuella användningsperioden.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Server Call Usage]** > **[!UICONTROL Report Suite Usage]**

>[!IMPORTANT]
>
>Om en rapportsvit inte är länkad till en Experience Cloud-organisation visas inte dess användningsdata på den här instrumentpanelen. Ett fakturerings-ID kan även vara knutet till flera Experience Cloud Orgs. det inte alltid finns en 1:1-relation mellan en organisation och ett fakturerings-ID.

Kontrollpanelen för användning av Report Suite

* Visar den aktuella användningsperiodens användning av serveranrop (Alla anrop, Primär, Sekundär, Mobilprimär, Mobilsekundär) för varje rapportserie i din Experience Cloud-organisation.
* Visar procentandel av den totala användningen per kategori för serversamtal.
* Uppdateras dagligen.
* Kan laddas ned.
* Ger åtkomst till **[!UICONTROL Manage Alerts]** Gränssnitt.

![](/help/admin/admin/c-server-call-usage/assets/report-suite-usage.png)

| Kolumn | Definition |
|--- |--- |
| Namn på rapportsvit | Namn på rapportsviten |
| Alla samtal (% av totalt) | Alla serveranrop under den aktuella användningsperioden. |
| Primära samtal (%) | Alla primära serveranrop (och deras procentuella andel) som uppstått under den aktuella användningsperioden. |
| Sekundära anrop (%) | Alla sekundära serveranrop (och deras procentuella andel) som uppstått under den aktuella användningsperioden. |
| Primär mobil (%) | Alla mobilprimära serveranrop (och deras procentandel av det totala) som uppstått under den aktuella användningsperioden. |
| Sekundär mobil (%) | Alla anrop till sekundära mobilservrar (och deras procentandel av det totala) som uppstått under den aktuella användningsperioden. |


## Hämta användningsrapport {#section_D7345660B5E043CD8850954216509A3D}

Med det här alternativet kan du hämta aktuella användningsdata och data från tidsperioder före den aktuella användningsperioden (från januari 2015). Rapporten hämtas som en CSV-fil.

1. Välj minst en rapportserie.
1. Klicka på **[!UICONTROL Download Report]**.

   ![](/help/admin/admin/c-server-call-usage/assets/download_report.png)

| Rapportelement | Beskrivning |
|--- |--- |
| Filnamn | Hårdkodat namn: Användningsrapport `day and time of report creation.csv` |
| Inkluderade rapportsviter | Alla rapportsviter som du har valt på sidan Report Server-användning ingår i den här listan. |
| Inkluderade samtalstyper | Ange en kombination av dessa: Alla samtal (standard), primära, sekundära, primära, primära, sekundära, mobila. |
| Tidsintervall | Du kan välja den aktuella användningsperioden eller ange ett anpassat intervall.  Ange intervallstart och intervallslut för ett anpassat intervall. <br>**Obs!** Du kan inte hämta användningsdata före januari 2015 </br>. |

1. Klicka på **[!UICONTROL Download]**.

Här visas en skärmbild av hur den hämtade CSV-filen ser ut. Den innehåller en kolumn för rapportsvitens-ID. Rapportsvitens ID anger ett unikt ID som bara kan innehålla alfanumeriska tecken. Detta ID kan inte ändras efter att en rapportserie har skapats.

![](/help/admin/admin/c-server-call-usage/assets/download-usage.png)
