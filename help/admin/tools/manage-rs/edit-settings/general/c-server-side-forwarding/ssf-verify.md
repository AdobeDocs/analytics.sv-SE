---
description: För att verifiera att vidarebefordran på serversidan är korrekt aktiverad måste du granska HTTP-svaret från Analytics Tracking-begäran. Instruktionerna visar vilka indikatorer som måste finnas för att vidarebefordran på serversidan ska kunna aktiveras korrekt.
solution: Analytics
title: Så här verifierar du implementeringen av vidarebefordring på serversidan
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Så här verifierar du implementeringen av vidarebefordring på serversidan

För att verifiera att vidarebefordran på serversidan är korrekt aktiverad måste du granska HTTP-svaret från Analytics Tracking-begäran. Detta kan du göra med en webbläsares utvecklingsverktyg eller med hjälp av ett proxyverktyg som Charles Web Debugger. Följande instruktioner visar vilka indikatorer som måste finnas för att vidarebefordran på serversidan ska kunna aktiveras korrekt.

Så här kontrollerar du status för vidarebefordran på serversidan:

1. Läs in en testsida som innehåller uppdaterad AppMeasurement-kod.
1. Kontrollera HTTP-svaret från Analytics-spårningsbegäran i webbläsarens felsökningsverktyg eller med proxyprogramvaran (du kan enkelt filtrera detta genom att välja en sökväg som innehåller&quot;b/ss&quot;).
1. Kontrollera HTTP-svaret. Om svaret innehåller Audience Manager-data (som framgår nedan) fungerar vidarebefordran på serversidan.

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Om svaret innehåller nyckelvärdepar `"status":"SUCCESS"` eller en 2 x 2-bild är vidarebefordran på serversidan * inte* korrekt konfigurerat. Kontrollera att identitetstjänsten är korrekt distribuerad, att du har distribuerat modulen App Measurement, att den tillämpliga rapportsviten har mappats till rätt organisations-ID och att vidarebefordran på serversidan har aktiverats i Analytics Admin Tools.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
