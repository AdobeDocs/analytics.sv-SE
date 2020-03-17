---
description: Steg som beskriver hur administratörer kan aktivera rapportåtkomst för ett datalager för en grupp användare.
title: Lägg till användargrupp för datalager
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Lägg till användargrupp för datalager

Steg som beskriver hur administratörer kan aktivera rapportåtkomst för ett datalager för en grupp användare.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Klicka på **[!UICONTROL Edit Groups]**.
1. Klicka på **[!UICONTROL Add New User Group]**.
1. Skriv ett namn i fältet Gruppnamn i **[!UICONTROL Define User Group]** avsnittet. tillhandahålla följande gruppinformation:

   Exempel, `Data Warehouse Access`.
1. Skriv en beskrivning i **[!UICONTROL Group Description]** fältet.
1. I **[!UICONTROL Report Suite Access]** avsnittet markerar du de rapportsviter som du vill att gruppmedlemmar ska kunna komma åt.
1. Under [!UICONTROL Tools], aktivera **[!UICONTROL All Tools]**.

   Du kan också klicka på **[!UICONTROL Customize]** och sedan aktivera **[!UICONTROL Custom Data Warehouse Report]**.

1. Under [!UICONTROL Assign User Logins]lägger du till önskade användarinloggningar.
1. Klicka på **[!UICONTROL Save Group]**.

   Nästa gång användare som läggs till i den här gruppen loggar in visas alternativet Datalager som lagts till på [!UICONTROL Reports & Analytics] menyn.

   >[!NOTE]
   >
   >Om behörigheter som är i konflikt med varandra (till exempel en användare som har tilldelats två grupper, av vilka den ena nekar åtkomst till en funktion och den andra beviljar samma åtkomst), begränsar systemet behörigheten. Användare som tillhör grupper som nekar åtkomst till datalager kan behöva tas bort från dessa grupper.

>[!MORELIKETHIS]
>
>* [Grupper](/help/admin/user-management2/c-user-groups/groups.md)

