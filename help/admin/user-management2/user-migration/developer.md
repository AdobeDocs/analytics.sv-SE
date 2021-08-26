---
description: Visar API:er som påverkas av användarmigreringen
title: API:er som påverkas av användarmigreringen
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# API:er som påverkas av användarmigreringen{#apis-affected-by-the-migration}

Adobe migrerar alla inloggningsföretag för Analytics från [!DNL my.omniture.com] och till autentisering via Adobe Experience Cloud. När ett företag väl har påbörjat migreringen stöds inte längre programmatiska användargenereringar och hantering via de Analytics-specifika behörigheterna och `GetLoginKey`-metoder som är tillgängliga via v1.3 och v1.4 i API:t för Analytics Admin. Sådana åtgärder kommer nu att aktiveras över hela Experience Cloud via [!DNL adobe.io].

## API-metoder som påverkas {#section-d19051ac26cc49aeb124f767c4760254}

Följande API-metoder i v1.3 och v1.4 i Admin API stöds inte längre när du börjar migrera användare:

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## Funktioner {#section-8b0b89a862614f729ebdbe092ce99027}

Om ditt företag för närvarande använder dessa metoder bör du leta efter ett meddelande före migrering från och med den 31 mars 2018. Meddelandet skickas minst 30 dagar innan ditt företag påbörjar migreringen till autentiseringen Experience Cloud, och då upphör stödet för dessa metoder.

Om ditt företag inte använder någon av dessa metoder behöver du inte vidta någon annan åtgärd än att se till att du inte börjar använda dessa metoder.

Ytterligare information:

* [Allmän information om användarhantering](https://helpx.adobe.com/enterprise/help/users.html)
* [API:er för användarhantering via adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [API-forum för användarhantering](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migrering av användaråtkomst och hantering för Analytics till Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html)
