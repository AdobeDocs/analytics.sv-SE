---
title: VRS och projekturval
description: Lär dig att strukturera vrs-komponenter och -projekt
translation-type: tm+mt
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# VRS och projekturval

När ni strukturerar projekt eller virtuella rapportsviter filtrerar ni i princip bort komponenter så att era målgrupper bara ser de projekt-/VRS-komponenter (mått, mätvärden, segment, datumintervall) som ni vill att de ska använda.

>[!NOTE]
>
>Produktprofiler är den primära mekanismen som styr vilka komponenter en användare kan se. De hanteras via [Admin Console](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles). Curation är ett sekundärt filter.

Vi har nyligen förbättrat kurationsupplevelsen. Här är en översikt över vad **[!UICONTROL Show All]** knappen visar, förutom de kuraterade komponenter som redan finns, i olika kuraterade upplevelser och på behörighetsnivå:

| Kurvtyp | Administratörer | Projektägare som inte är administratörer | Icke-administratörer |
|---|---|---|---|
| Kuraterad VRS | Alla VRS-komponenter som inte är kuraterade | Icke-förvaltade VRS-komponenter som den här rollen äger eller som har delats med dem | Icke-förvaltade VRS-komponenter som den här rollen äger eller som har delats med dem |
| Kuraterat projekt | Alla projektkomponenter som inte är kuraterade | Alla projektkomponenter som inte är kuraterade | Ej förvaltade projektkomponenter som den här rollen äger eller som har delats med dem |
| Kuraterat projekt i ett kuraterat VRS | Alla icke-förvaltade komponenter, visas under **[!UICONTROL Non-Curated Project Components]** och **[!UICONTROL Non-Curated VRS Components]** | Alla icke-förvaltade projektkomponenter OCH icke-förvaltade VRS-komponenter som den här rollen äger eller som har delats med dem | Icke-förvaltat VRS och projektkomponenter som den här rollen äger eller har delats med dem |

>[!IMPORTANT]
>
>VRS-kurering används alltid före projektkurering. Detta innebär att även om ditt kuraterade projekt innehåller vissa komponenter, kommer de att filtreras bort om det aktuella VRS inte innehåller dem.
