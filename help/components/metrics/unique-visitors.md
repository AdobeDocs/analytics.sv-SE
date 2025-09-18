---
title: Unika besökare
description: Antalet unika besökar-ID.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: e242276f931e9939081b948a9d9ef8a087e16461
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Unika besökare

[Mått](overview.md) för unika besökare visar antalet besökar-ID för dimensionsobjektet. Det är ett av de vanligaste måtten som används för att fastställa trafik, eftersom det ger en översikt på hög nivå över en dimensionsposts popularitet. En besökare kan till exempel komma till din webbplats varje dag i en månad, men de räknas ändå som en unik besökare.

Om du använder [Enhetsövergripande analys](../cda/overview.md) ersätts det här måttet med måttet [Unika enheter](unique-devices.md).

## unika besökare varje dag, vecka, månad, kvartal och år

Analysis Workspace behandlar unika besökare utifrån rapportens detaljrikedom. Om du till exempel använder dimensionen [Dag](../dimensions/day.md) visas unika besökare dagligen för varje dimensionsobjekt. För rapportsumman har den dock ersatts med unika besökare för friformstabellens datumintervall.

## Hur det här måttet beräknas

Det här måttet räknar antalet unika besökar-ID:n för en given dimensionspost. Det använder flera avancerade mekanismer för att identifiera unika besökare, eftersom det finns flera sätt att identifiera dem. I följande tabell visas hur en besökare identifieras samt dess prioritet. Vissa träffar kan ha flera metoder för identifiering av besökare. I dessa fall används metoden med högre prioritet.

| Använd order | Frågeparameter (samlingsmetod) | Presentera när |
| --- | --- | --- |
| 1 | `vid` | Variabeln [`visitorID`](/help/implement/vars/config-vars/visitorid.md) har angetts. |
| 2 | `aid` | Besökaren har en befintlig [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)-cookie. Ange implementeringar utan eller innan du implementerar Visitor ID-tjänsten. |
| 3 | `mid` | Besökaren har en befintlig [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)-cookie. Ange implementeringar med hjälp av [Adobe Experience Cloud Identity-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html). Adobe rekommenderar att du använder ID-tjänsten för alla implementeringar där det är möjligt. |
| 4 | `fid` | Besökaren har en befintlig [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)-cookie, eller om `aid` och `mid` inte kunde anges av någon anledning. |
| 5 | IP-adress, användaragent, gateway-IP-adress | Den sista utvägen för att identifiera en unik besökare om besökarens webbläsare inte accepterar cookies. |

>[!NOTE]
>
>Varje besökar-ID för Analytics är knutet till en profil på Adobe servrar. Dessa besökarprofiler tas bort efter minst 13 månaders inaktivitet, oavsett när en cookie för besöks-ID förfaller.

## Beteende som påverkar antalet unika besökare

Unika besöksidentifierare lagras vanligtvis i en webbläsarcookie. En ny unik besökare räknas om de utför något av följande:

* Rensar cacheminnet när som helst
* Öppnar en annan webbläsare på samma dator. En unik besökare räknas per webbläsare.
* Samma person som surfar på din webbplats på olika enheter. En separat unik besökare räknas per enhet. Du kan använda [Enhetsövergripande analys](../cda/overview.md) för att kombinera besökare med hjälp av måttet [Personer](people.md).
* Öppnar en privat surfsession (till exempel fliken Chrome Incognito).

En ny unik besökare *räknas inte*, förutsatt att cookie-identifieraren bevaras:

* Stänger webbläsaren under en längre period
* Uppgraderar webbläsaren till den senaste versionen
