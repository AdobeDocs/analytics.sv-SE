---
description: 'null'
title: API:er som påverkas av migreringen
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# API:er som påverkas av migreringen{#apis-affected-by-the-migration}

## API:er som påverkas av migreringen {#topic-8d34296a67d74b1081c3f7e8f650f3ce}

Adobe migrerar alla inloggningsföretag för Analytics från [!DNL my.omniture.com] och till autentisering via Adobe Experience Cloud. När ett företag väl har påbörjat migreringen kommer det inte längre att finnas stöd för programmatisk användargenerering och hantering via de analysspecifika behörigheter och `GetLoginKey` metoder som är tillgängliga via v1.3 och v1.4 i API:t för Analytics-administratörer. Sådana åtgärder kommer nu att aktiveras i hela Experience Cloud via [!DNL adobe.io].

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

Om ditt företag för närvarande använder dessa metoder bör du leta efter ett meddelande före migrering från och med den 31 mars 2018. Meddelandet skickas minst 30 dagar innan ditt företag börjar migrera till Experience Cloud-autentiseringen, och då upphör stödet för dessa metoder.

Om ditt företag inte använder någon av dessa metoder behöver du inte vidta någon annan åtgärd än att se till att du inte börjar använda dessa metoder.

Ytterligare information:

* [Allmän information om användarhantering](https://helpx.adobe.com/enterprise/help/users.html)
* [API:er för användarhantering via adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [API-forum för användarhantering](https://forums.adobe.com/community/umapi/overview)
* [Migrering av användaråtkomst och hantering för Analytics till Experience Cloud](https://docs.adobe.com/content/help/en/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html)

