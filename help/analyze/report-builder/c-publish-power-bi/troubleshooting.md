---
description: Vanliga problem vid användning av Report Builder med Power BI.
title: Felsöka Power BI-integrering
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 2%

---


# Felsöka Power BI-integrering

Utforska och åtgärda vanliga problem när du använder Report Builder med Power BI.

## Det gick inte att publicera till Power BI

Schemalagda arbetsböcker som kräver Power BI-publicering är beroende av att Power BI-tjänster är igång. Två huvudorsaker till att publiceringen inte lyckas är:

* Power BI-tjänsterna kan vara nere.
* Användaren som har schemalagt arbetsboken har inte längre giltiga autentiseringsuppgifter för Microsoft-kontot.

Varje schemalagd Report Builder-aktivitet får tre försök per schemalagd körning:

* Efter det första misslyckade försöket får du följande meddelande: &quot;&quot;Det gick inte att publicera den schemalagda arbetsboken på Microsoft Power BI. Vi kommer att försöka igen inom kort.&quot;
* Efter det andra misslyckade försöket får du inget meddelande.
* Efter det tredje misslyckade försöket får du följande meddelande: &quot;Det gick inte att publicera arbetsboken på Power BI.&quot;

## Brutna visualiseringar i Power BI

Här är de viktigaste skälen till varför du kan få brutna visualiseringar efter att ha publicerat Report Builder-begäranden till Power BI:

* Du redigerade en begäran i Report Builder, till exempel om att ändra mått och mått, och publicerade sedan om den till Power BI. Om du redigerar begäranden kan visualiseringarna gå förlorade.
* Du tog bort en begäran som användes i en visualisering.

## Report Builder måste ha behörighet att komma åt organisationens resurser. Den här åtkomsten kan bara beviljas av en administratör. Be en administratör att ge dig tillstånd.

Låt en Microsoft Admin granska inställningen &quot;Användare kan registrera program&quot; som finns under: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. Om det här alternativet är inställt på Nej kan administratören registrera dessa typer av program.

Användare kan bevilja åtkomst via följande [länk](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Administratörer beviljade åtkomst för var och en genom att använda följande [länk](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).
