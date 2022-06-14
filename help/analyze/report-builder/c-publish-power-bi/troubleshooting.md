---
description: Vanliga problem vid användning av Report Builder med Power BI.
title: Felsöka Power BI-integrering
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: a30564e9d8969457aaa8709c3aa3c17ba6d0a2d3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Felsöka Power BI-integrering

Utforska och åtgärda vanliga problem när du använder Report Builder med Power BI.

## Det gick inte att publicera till Power BI

Schemalagda arbetsböcker som kräver Power BI-publicering är beroende av att Power BI-tjänster är igång. Två huvudorsaker till att publiceringen inte lyckas är:

* Power BI-tjänsterna kan vara nere.
* Användaren som har schemalagt arbetsboken har inte längre giltiga Microsoft-kontouppgifter.

Varje schemalagd Report Builder-aktivitet får tre försök per schemalagd körning:

* Efter det första misslyckade försöket får du följande meddelande: &quot;&quot;Det gick inte att publicera den schemalagda arbetsboken på Microsoft Power BI. Vi kommer att försöka igen inom kort.&quot;
* Efter det andra misslyckade försöket får du inget meddelande.
* Efter det tredje misslyckade försöket får du följande meddelande: &quot;Det gick inte att publicera arbetsboken på Power BI.&quot;

## Brutna visualiseringar i Power BI

Här är de viktigaste skälen till varför du kan få brutna visualiseringar efter att ha publicerat Report Builder-begäranden till Power BI:

* Du redigerade en begäran i Report Builder, till exempel om att ändra mått och mått, och publicerade sedan om den till Power BI. Om du redigerar begäranden kan visualiseringarna gå förlorade.
* Du tog bort en begäran som användes i en visualisering.

## Report Builder måste ha behörighet att komma åt organisationens resurser. Den här åtkomsten kan bara beviljas av en administratör. Be en administratör att ge dig tillstånd.

Be en Microsoft-administratör granska inställningen&quot;Användare kan registrera program&quot; som finns under: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. Om det här alternativet är inställt på Nej kan administratören registrera dessa typer av program.

Användare kan bevilja åtkomst genom att använda följande [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Administratörer beviljade åtkomst för var och en genom att använda följande [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## API-gränsen nås

Rapportering i Power BI fungerar med API:t för analysrapportering, så API-tröskelvärden gäller. Mer information finns i [Vad är hastighetsbegränsningen för API-anrop?](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/#what-is-the-rate-limit-for-api-calls).
