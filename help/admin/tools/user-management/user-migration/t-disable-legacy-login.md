---
description: Lär dig hur du inaktiverar äldre inloggningar för Analytics-användare.
title: Inaktivera äldre inloggningar
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Inaktivera äldre inloggningar

Lär dig hur du inaktiverar äldre inloggningar för Analytics-användare.

När användarna har migrerat från det äldre användarhanteringssystemet Analytics till Adobe Admin Console kan du inaktivera deras gamla inloggningar. Om du inaktiverar äldre inloggningar dirigeras användare om till Experience Cloud-inloggningen om de försöker använda den gamla inloggningen.

1. Öppna migreringsverktyget i **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User ID Migration]**.
1. I avsnittet [!DNL User Information] letar du reda på domänen som innehåller de användare du vill arbeta med och klickar sedan på **[!UICONTROL Select Users]**.
1. Markera de användare med äldre inloggningar som du vill inaktivera.

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

   Användarna som är berättigade får statusen *`Migrated`* under kolumnen Migreringsstatus. Du kan inte inaktivera en användares tidigare inloggning förrän användaren har migrerats.
1. Klicka på **[!UICONTROL Disable Legacy Login]** och sedan på **[!UICONTROL Done]**.

   Inaktivera äldre inloggning anger vilka av dina användare som kan fortsätta att använda sitt gamla [!DNL my.omniture.com]-användarnamn och lösenord.

   Du kan inte inaktivera äldre inloggningar för en användare som ännu inte har migrerats. När det är inaktiverat måste användaren använda sitt Experience Cloud ID för att logga in och få åtkomst till Analytics.
