---
description: Information om de tre sätten att logga in på Report Builder.
title: Inloggning i Report Builder
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: 5b130de23d7826a266f34ed1830540c8c0865560
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 3%

---


# Inloggning i Report Builder

>[!IMPORTANT]
>
>Report Builder version 5.6.47 och senare stöder endast inloggning med Experience Cloud och stöder inte äldre inloggningar som Site Catalyst Single Sign-on eller Standard Login. Senast den 30 april 2021 måste alla användare av Report Builder uppdatera tillägget Report Builder till version 5.6.47 eller senare, vilket inkluderar en viktig uppdatering av inloggningsprocessen.

Om du vill logga in på Report Builder använder du ditt Experience Cloud-inloggningskonto.

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

Med inloggningen Experience Cloud kan du använda Enterprise ID (e-post och lösenord) för att logga in på Adobe Experience Cloud. Klicka på **[!UICONTROL Sign In]** > **[!UICONTROL Sign in with an Enterprise ID]** om du vill omdirigeras till företagets inloggningssida. Mer information om Enterprise ID får du om du klickar [här](https://helpx.adobe.com/enterprise/kb/enterprise-id-faq.html#whatis).

![](assets/adobe_id_login.png)

>[!NOTE]
>
>Experience Cloud-inloggningen är sessionsbaserad och token upphör att gälla efter 30 dagar.

## Logga in på Report Builder

Logga in i Report Builder

1. Klicka på **[!UICONTROL Add-Ins]** i Excel.
1. Klicka på **[!UICONTROL Sign In]**. Andra åtgärder som loggar in dig är:

   * Klicka på **[!UICONTROL Create]**.
   * [Välj en begäran i Begäranhanteraren](/help/analyze/report-builder/manage-requests/r-arb-manage-requests.md) och klicka sedan på  **[!UICONTROL Add]** eller  **[!UICONTROL Manage]**.
   * Dubbelklicka på en begäran i Excel.

1. Fyll i fälten på sidan [!UICONTROL Login] och klicka sedan på **[!UICONTROL OK]**.

## Äldre inloggningstyper

>[!IMPORTANT]
>
>Den 30 april 2021 kommer äldre inloggningstyper inte att fungera. Alla användare av Report Builder måste uppdatera tillägget Report Builder till version 5.6.47 eller senare, vilket innehåller en viktig uppdatering av inloggningsprocessen. **Report Builder version 5.6.47 och senare stöder endast inloggning med Experience Cloud och stöder inte äldre inloggningar som standardinloggning eller enkel inloggning i Site Catalyst.**

<!-- ![](assets/login_screen.png) -->

* [Standard](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Site Catalyst enkel inloggning](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)

## Standard {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Använd den här inloggningen om du vill logga in på Report Builder med dina Adobe Analytics-inloggningsuppgifter.

**Inloggning från Report Builder - fältdefinitioner**

| Fält | Definition |
|--- |--- |
| Företag | De företagsinloggningsuppgifter som du använder för Adobe Analytics. |
| Användarnamn | Inloggningen för användarnamn som du använder för Adobe Analytics. Schemalagda aktiviteter för en användare är länkade till användarnamnet. Du kan visa dina schemalagda aktiviteter från vilken dator som helst om du loggar in på Report Builder med samma inloggningsuppgifter. |
| Lösenord | Ditt Analytics-lösenord. |
| Kom ihåg mig | Inloggningsinformationen krypteras och lagras i en användarprofilfil på den dator där Report Builder är installerat. Eftersom inloggningsinformationen sparas kan alla som använder samma dator som den som skapar rapporten, och som öppnar ett kalkylblad som innehåller en rapport, uppdatera och redigera informationen. Om du delar datorn med andra och vill hålla kalkylbladsdata privata ska du inte aktivera det här alternativet.  Om du vill inaktivera den automatiska inloggningsinställningen klickar du på **[!UICONTROL Log in With Different Credentials]** i verktygsfältet och inaktiverar **[!UICONTROL Remember Me]**. |
| Använd en proxyserver | Aktivera om du ansluter till Internet via en proxyserver och måste ange ett proxyanvändarnamn och lösenord. |

## Enkel inloggning {#section_6970A5F926774976B85FFE576610E85F}

Den här (äldre) enkla inloggningen loggar endast in dig på Adobe Analytics, inte på hela Experience Cloud.

Du kan också skriva in en domän så känner systemet igen domänen och dirigerar om dig till ditt företags inloggningssida för att logga in på Adobe Analytics.
