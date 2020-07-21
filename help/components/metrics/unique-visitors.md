---
title: Unika besökare
description: Antalet unika personer (eller enheter).
translation-type: tm+mt
source-git-commit: 9704267cd3ebf480facd68f6cca44167b1d9686d
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 2%

---


# Unika besökare

Måttet&quot;Unika besökare&quot; visar antalet besökar-ID:n för dimensionsvärdet. Det är en av de vanligaste måtten som används för att fastställa trafik, eftersom det ger en översikt på hög nivå över hur populärt ett dimensionsvärde är. En besökare kan till exempel komma till din webbplats varje dag i en månad, men de räknas ändå som en unik besökare.

Om du använder [Enhetsövergripande analys](../cda/overview.md)får det här måttet namnet namnet&quot;Unika enheter&quot;.

## unika besökare varje dag, vecka, månad, kvartal och år

Rapporter och Analytics innehåller alternativ för unika besökare varje dag, vecka, månad, kvartal och år. I stället för att räkna en unik besökare för hela tidsperioden, räknar unika besökare baserat på det valda mätvärdet. Du vill till exempel titta på unika besökare varje dag för din webbplats. Om en besökare kommer till er webbplats på morgonen och igen på natten räknas de som en enda unik besökare varje dag. Om en besökare kommer till er webbplats på måndag och igen på tisdag räknas de som två unika besökare varje dag.

Analysis Workspace behandlar unika besökare baserat på rapportens detaljrikedom. Om du till exempel använder dimensionen [Dag](../dimensions/day.md) visas unika besökare varje dag för varje dimensionsvärde. För rapportsumman har den dock ersatts med unika besökare för friformstabellens datumintervall.

## Hur det här måttet beräknas

Det här måttet räknar antalet unika besökar-ID:n för ett givet dimensionsvärde. Det använder flera avancerade mekanismer för att identifiera unika besökare, eftersom det finns flera sätt att identifiera dem. I följande tabell visas hur en besökare identifieras samt dess prioritet. Vissa träffar kan ha flera metoder för identifiering av besökare. I dessa fall används metoden med högre prioritet.

| Använd order | Frågeparameter (samlingsmetod) | Presentera när |
| --- | --- | --- |
| 1 | `vid` | Variabeln är [`visitorID`](/help/implement/vars/config-vars/visitorid.md) inställd. |
| 2 | `aid` | Besökaren har en befintlig [`s_vi`](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-analytics.html) cookie. Ange implementeringar utan eller innan du implementerar Visitor ID-tjänsten. |
| 3 | `mid` | Besökaren har en befintlig [`s_ecid`](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-analytics.html) cookie. Ange implementeringar med [Adobe Experience Cloud Identity-tjänsten](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html). |
| 4 | `fid` | Besökaren har en befintlig [`s_fid`](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-analytics.html) cookie, eller om `aid` och `mid` inte kunde anges av någon anledning. |
| 5 | IP-adress, användaragent, gateway-IP-adress | Den sista utvägen för att identifiera en unik besökare om besökarens webbläsare inte accepterar cookies. |

>[!NOTE]
>
>Varje besökar-ID från Analytics är knutet till en profil på Adobes servrar. Dessa besökarprofiler tas bort efter minst 13 månaders inaktivitet, oavsett när en cookie för besöks-ID förfaller.

## Beteende som påverkar antalet unika besökare

Unika besöksidentifierare lagras vanligtvis i en webbläsarcookie. En ny unik besökare räknas om de utför något av följande:

* Rensar cacheminnet när som helst
* Öppnar en annan webbläsare på samma dator. En unik besökare räknas per webbläsare.
* Samma person som surfar på din webbplats på olika enheter. En separat unik besökare räknas per enhet. Ni kan använda [enhetsövergripande analys](../cda/overview.md) för att kombinera besökare med [personmätaren](people.md) .
* Öppnar en privat surfsession (till exempel Chrome&#39;s Incognito-fliken).

En ny unik besökare räknas *inte* så länge cookie-identifieraren bevaras:

* Stänger webbläsaren under en längre period
* Uppgraderar webbläsaren till den senaste versionen
