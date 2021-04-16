---
description: Steg som beskriver hur administratörer kan aktivera rapportåtkomst i Data warehouse för en grupp användare.
title: Lägga till användargrupp i Data Warehouse
feature: Data Warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
exl-id: 8737ab60-2ad1-4795-808b-d0200078a333
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 10%

---

# Lägga till användargrupp i Data Warehouse

Steg som beskriver hur administratörer kan aktivera rapportåtkomst i Data warehouse för en grupp användare.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Klicka på **[!UICONTROL Edit Groups]**.
1. Klicka på **[!UICONTROL Add New User Group]**.
1. I avsnittet **[!UICONTROL Define User Group]** skriver du ett namn i fältet Gruppnamn. tillhandahålla följande gruppinformation:

   Exempel, `Data Warehouse Access`.
1. Skriv en beskrivning i fältet **[!UICONTROL Group Description]**.
1. I avsnittet **[!UICONTROL Report Suite Access]** markerar du de rapportsviter som du vill att gruppmedlemmar ska kunna komma åt.
1. Aktivera **[!UICONTROL All Tools]** under [!UICONTROL Tools].

   Du kan också klicka på **[!UICONTROL Customize]** och sedan aktivera **[!UICONTROL Custom Data Warehouse Report]**.

1. Lägg till önskade användarinloggningar under [!UICONTROL Assign User Logins].
1. Klicka på **[!UICONTROL Save Group]**.

   Nästa gång användare som läggs till i den här gruppen loggar in visas alternativet Data warehouse som lagts till på menyn [!UICONTROL Reports & Analytics].

   >[!NOTE]
   >
   >Om behörigheter som är i konflikt med varandra (till exempel en användare som har tilldelats två grupper, av vilka den ena nekar åtkomst till en funktion och den andra beviljar samma åtkomst), begränsar systemet behörigheten. Användare som tillhör grupper som inte tillåter åtkomst till data warehouse kan behöva tas bort från dessa grupper.

>[!MORELIKETHIS]
>
>* [Grupper](/help/admin/user-management2/c-user-groups/groups.md)

