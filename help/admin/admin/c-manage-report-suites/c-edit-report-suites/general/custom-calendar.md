---
description: Kalenderalternativ i andra format än den gregorianska modellen. Alternativen är kalendermodellerna 4-4-5, 4-5-4 och 5-4-4, som alla används som standard för detaljhandeln. Rapporteringen innehåller också en helt anpassningsbar kalender som du kan konfigurera själv.
title: Anpassa kalender
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
role: Admin
source-git-commit: d5bbba7518529befabb8815ac657336326562fd1
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---

# Anpassa kalender

Kalenderalternativ i andra format än den gregorianska modellen. Alternativen är kalendermodellerna 4-4-5, 4-5-4 och 5-4-4, som alla används som standard för detaljhandeln. Dessutom erbjuder rapportering ett alternativ för en helt anpassningsbar kalender som du kan konfigurera själv.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Customize Calendar]**

>[!CAUTION]
>
>Om du ändrar kalendern ändras det sätt som data behandlas på (dvs. definitionen av unika besökare varje vecka och månad). När en kalenders definition av veckor och månader ändras, ändras inte historiska data. Den här inställningen påverkar även segment som baseras på datumintervall.

Du kan använda kalendern för att definiera den första dagen i veckan och året eller använda ett annat återförsäljningsformat. Kalenderformaten används för olika syften, inklusive försäljningsjämförelse och prognosstandardisering, lönekostnadsanalys eller reglering av fysiskt lagerantal. Detaljhandeln använder till exempel räkenskapskalendern för 4-5-4 som stöd för försäljningssäsongens särdrag i detaljhandeln. Varje kalenderformat beskrivs nedan.

## Anpassa kalenderbeskrivningar {#section_B0D224DACB914A378902A4E0E1234889}

| Kalender | Beskrivning |
|--- |--- |
| Gregoriansk kalender | Använder det traditionella kalenderformatet (januari till december, med 30 eller 31 dagar och ett varierande antal veckor i varje månad). |
| Ändrad gregoriansk kalender | Använder den traditionella gregorianska kalendern, men du kan välja den första månaden på året och den första dagen i veckan. |
| 4-5-4 butikskalender | Varje månad delas upp med antalet veckor i månaden. Betydelse: Januari har fyra veckor och så vidare. The National Retail Federation använder kalenderformatet 4-5-4. |
| Anpassad kalender | Erbjuder tre format baserat på antalet veckor varje månad. Antalet veckor i varje månad beror på den valda första dagen på året.  Ett år har 52 veckor. Dela upp det i 4 kvartal så får du 13 veckor per kvartal. Men det finns tre månader på en kvart. 13 är inte delbart med tre, så det slutar med att du sätter den extra veckan i en av månaderna så att den alltid är konsekvent.<ul><li>5/4/4 betyder att den första månaden i kvartalet har den extra veckan. 4/5/4 betyder att den andra månaden har den extra veckan osv. I kalendern 5-4-4 läggs den 53:e veckan till på årets sista kvartal.</li><li>4-5-4:Januari har fyra veckor, februari har fem veckor, mars har fyra veckor och så vidare.</li><li>4-4-5: Januari har fyra veckor, februari har fyra veckor, mars har fem veckor och så vidare.</li><li>5-4-4: Januari har fem veckor, februari har fyra veckor, mars har fyra veckor och så vidare.</li></ul> |

>[!NOTE]
>De här kalenderalternativen stöds av alla Adobe Analytics-verktyg (Analysis Workspace, Report Builder, Activity Map), utom Data Warehouse. Data Warehouse stöder endast den gregorianska kalendern. När du väljer en icke-gregoriansk kalender använder Data Warehouse det förväntade datumintervallet för den icke-gregorianska kalendern, men dag-/vecka-/månadsuppdelningarna inom rapportens rader kanske inte är vad som förväntas av en icke-gregoriansk kalender.
