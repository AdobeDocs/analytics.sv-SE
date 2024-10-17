---
description: Vanliga problem vid användning av Report Builder med Power BI.
title: Felsökning av integrering med Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Felsökning av integrering med Power BI

{{legacy-arb}}

Utforska och åtgärda vanliga problem när du använder Report Builder med Power BI.

## Det gick inte att publicera till Power BI

Schemalagda arbetsböcker som kräver Power BI-publicering är beroende av att Power BI-tjänster är igång. Två huvudorsaker till att publiceringen inte lyckas är:

* Power BI-tjänsterna kan vara nere.
* Användaren som har schemalagt arbetsboken har inte längre giltiga Microsoft-kontouppgifter.

Varje schemalagd Report Builder-aktivitet får tre försök per schemalagd körning:

* Efter det första misslyckade försöket får du följande meddelande: &quot;&quot;Det gick inte att publicera den schemalagda arbetsboken på Microsoft Power BI. Vi kommer att försöka igen inom kort.&quot;
* Efter det andra misslyckade försöket får du inget meddelande.
* Efter det tredje misslyckade försöket får du följande meddelande:&quot;Det gick inte att publicera arbetsboken på Power BI.&quot;

## Brutna visualiseringar i Power BI

Här är de viktigaste skälen till varför du kan få brutna visualiseringar efter att ha publicerat Report Builder-begäranden till Power BI:

* Du redigerade en begäran i Report Builder, till exempel om att ändra mått och mått, och publicerade sedan om den till Power BI. Om du redigerar begäranden kan visualiseringarna gå förlorade.
* Du tog bort en begäran som användes i en visualisering.

>[!IMPORTANT]
>
>Report Builder kräver att en administratör godkänner åtkomst till organisationens resurser. Om du behöver åtkomst ber du en administratör att ge dig behörighet.
> En Microsoft-administratör kan granska inställningen *Användare kan registrera program* som finns under: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. Om det här alternativet är inställt på **Nej** kan administratören registrera de här typerna av program.

Användare kan bevilja åtkomst genom att logga in på sitt [Microsoft Power BI-konto](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Administratörer kan ge alla åtkomst genom att logga in på deras [administratörs Microsoft Power BI-konto](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## API-gränsen nås

Rapportering i Power BI fungerar med API:t för analysrapportering, så API-tröskelvärden gäller. Mer information finns i [Felkoder för webbtjänster](https://github.com/AdobeDocs/analytics-1.4-apis/blob/3dda746890743c2098256719d6595109b7748262/docs/getting-started/c_Web_Services_Error_Codes.md).
