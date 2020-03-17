---
description: Konfigurera användare och lär dig mer om datainsamling.
title: Administration
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Administration

Konfigurera användare och lär dig mer om datainsamling.

Mer [!DNL Admin Console] information finns i [Analytics Reference](https://marketing.adobe.com/resources/help/en_US/reference/index.html).

## Användarlicenser {#concept_C1440741C77C471EB38A243B013EA620}

Användaren måste beviljas en användarlicens innan användaren kan logga in. Användarlicenser är licenser för samtidig användning. Användare kan dela användarlicenser, men antalet användare vid en viss tidpunkt är begränsat till antalet köpta användarlicenser.

<!-- 

c_user_license.html

 -->

När antalet inloggade användare överstiger antalet tillgängliga licenser visas en dialogruta som meddelar användaren om att alla tillgängliga licenser används. Användarens position i kön visas tillsammans med en länk för att kontrollera köpositionen igen. När en licens blir tillgänglig meddelas användaren med ett e-postmeddelande och en popup-dialogruta som anger att ad hoc-analys är tillgänglig för åtkomst. Användaren har sedan 15 minuter på sig att svara innan han/hon förlorar sin position i kön.

## Bevilja användarlicenser {#task_22AE669703EC48BA9685414538D8B1FA}

Steg som beskriver hur lokala Rapporter- och Analytics-administratörer kan bevilja användarlicenser via behörighetssystemet.

<!-- 

t_user_licenses.xml

 -->

1. Logga in på [!DNL Experience Cloud].
1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Klicka på **[!UICONTROL Edit Groups]**.

   Om ditt företag har köpt användarlicenser visas [!UICONTROL Ad Hoc Analysis License Users] gruppen i [!UICONTROL Group Name] kolumnen. Antalet tillgängliga licenser för användarinloggningar visas också.

1. Klicka på **[!UICONTROL Edit]**.
1. Under [!UICONTROL Assign User Logins]markerar du de användare som du vill lägga till i gruppen och klickar sedan på **[!UICONTROL Add.]**
1. Klicka på **[!UICONTROL Save Group]**.

   Licenssystemet begränsar inte antalet användare som läggs till i en grupp. Antalet licenser som köpts samtidigt är begränsat.

## Hantera användarsessioner {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Steg som beskriver hur en administratör kan avsluta en användarsession. Den här funktionen förhindrar inte att en användare som har slutat logga in igen.

<!-- 

t_managing_users.xml

 -->

1. Klicka **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** och sedan på **[!UICONTROL Manage Users]**.
1. Leta reda på användaren och klicka sedan på **[!UICONTROL Terminate.]**

   På [!UICONTROL Active Ad Hoc Analysis Sessions] sidan visas den användare som har varit inaktiv längst upp i listan.

## Behörigheter {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

Du ställer in åtkomst till rapportsviter i [!DNL Administration Console]. Du kan konfigurera behörighet på rapportsvitnivå. Om du till exempel har flera rapportsviter aktiverade, men inte vill ge alla användare åtkomst till alla rapportsviter, kan du skapa grupper med specifika rapportsviter och sedan tilldela dessa användare till rätt grupp.

## Lägg till en användare i gruppen Alla rapportåtkomst {#task_E821BF3B4FDB434D844A98AAB15487A9}

Steg som beskriver hur du ger icke-adminanvändare åtkomst till alla rapportsviter.

<!-- 

t_permissions.xml

 -->

1. Logga in på **[!UICONTROL Experience Cloud]**.
1. Klicka på **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Klicka på **[!UICONTROL All Report Access]**.
1. I [!UICONTROL Available Users]markerar du användaren och klickar sedan på **[!UICONTROL Add.]**
1. Klicka på **[!UICONTROL Save Group]**.

## Skapa behörighetsgrupper {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Skapa behörighetsgrupper för icke-adminanvändare för specifika rapportsviter.

<!-- 

t_permission_groups.xml

 -->

1. Logga in på **[!UICONTROL Experience Cloud]**.
1. Klicka på **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Skapa en behörighetsgrupp för icke-admin-användare som innehåller de ad hoc-analysaktiverade rapportsviter som du vill ska vara tillgängliga för användarna.

   De rapportsviter som är tillgängliga för användaren visas på [!UICONTROL Report Cloud] menyn när du skapar ett nytt projekt.

## Konfigurera proxyprinciper i Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Steg som beskriver hur du konfigurerar proxyprinciper om du får ett serveranslutningsfel.

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis använder HTTP för att kommunicera med servern. Den omfattas av samma proxyprinciper som annan HTTP-trafik.

1. I [!DNL Windows Control Panel]startar du [!UICONTROL Java Control Panel].
1. On the **[!UICONTROL General]** tab, click **[!UICONTROL Network Settings]**.
1. Välj **[!UICONTROL Use browser settings]** eller konfigurera proxyinställningarna manuellt.
1. Klicka **[!UICONTROL OK]** och sedan **[!UICONTROL OK]** på [!UICONTROL Java Control Panel].

## Hur data samplas {#concept_8433CFD38E0243849E92DF4F1E743AC3}

Exempel på besöksdata tas för att skapa meningsfull och korrekt rapportering. Datumintervallet används som datasegment för ett inläst projekt. Ett segment representerar vanligtvis den aktuella månaden plus de föregående två månaderna.

<!-- 

c_overview_data_sampling.xml

 -->

För optimal bearbetning används vid ad hoc-analys cirka 750 miljoner som det högsta antalet träffar per segment. (träffar = sidvisningar + händelser.)

För att komma fram till den beräknade samplingsfrekvensen beräknas antalet träffar per datauppsättning och divideras sedan med 750 miljoner, vilket visas här:

* (Genomsn. dagliga träffar (x antal dagar i segmentet) / 750 miljoner

Om du till exempel har 10 miljoner träffar om dagen, med ett datasegment på 90 dagar:

* (10 000 000 x 90) / 750 000 000 = 1,2

För att hålla antalet träffar för detta 90-dagarssegment under 750 000 000 kan data samplas vid 1,2:1, men eftersom samplingar i heltal används är samplingsfrekvensen 2:1.

Ett annat exempel: om du har 10 miljoner träffar om dagen, med ett datasegment i 365 dagar:

* (10 000 000 x 365) / 750 000 000 = 4,8

För att hålla antalet träffar för detta 365-dagarssegment under 750 000 000 kan data samplas på 4,8:1. Om du använder heltal är samplingsfrekvensen 5:1.
