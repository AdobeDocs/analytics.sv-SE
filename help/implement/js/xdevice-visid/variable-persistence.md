---
description: När besökarprofiler sammanfogas efter att de har associerats med samma variabel för besökar-ID, ändras inte attribueringen i den historiska datauppsättningen.
keywords: Analytics Implementation
title: Attribution och persistence
topic: Developer and implementation
uuid: 5dd706be-83f6-498a-a856-e3c5af995348
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Attribution och persistence

> [!IMPORTANT] Den här metoden för att identifiera besökare på olika enheter rekommenderas inte längre. Se [Enhetsövergripande analys](/help/components/cda/cda-home.md) i användarhandboken för komponenter.

När besökarprofiler sammanfogas efter att de har associerats med samma variabel för besökar-ID, ändras inte attribueringen i den historiska datauppsättningen.

* När variabeln `s.visitorID` anges och skickas vid en träff söker Adobe efter andra besökarprofiler som har ett matchande besökar-ID.
* Om det finns en profil används den besökarprofil som redan finns i systemet från och med den tidpunkten och den tidigare besökarprofilen används inte längre.
* Om inget matchande besökar-ID hittas skapas en ny profil.

När en oautentiserad kund först kommer till er webbplats tilldelas den kunden en besökarprofil av Adobe Analytics. När den nya profilen skapas avslutas ett besök och ett nytt besök börjar.

## Exempel 1

Exemplet nedan visar hur data skickas till Adobe Analytics när en kund autentiserar för första gången på den första enheten:

* `eVar16` har en förfallotid på 1 dag och `evar17` går ut vid besök.
* Kolumnen representerar den profil som hanteras av Adobe Analytics. `post_visitor_id` Postkolumner visas vanligtvis i dataflöden. Se [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md) i användarhandboken för Export.
* Kolumnerna `post_evar16` och `post_evar17` kolumnerna visar eVars beständighet.
* `cust_visid` representerar ett värde som anges i `s.visitorID`.
* Varje rad är en träff, en enda förfrågan som skickas till datainsamlingsservrarna för Adobe Analytics.

![Exempel på olika enheter 1](assets/xdevice_first.jpg)

På den första dataanslutningen som innehåller ett tidigare okänt `s.visitorID` värde (`u999` ovan) skapas en ny profil. Beständiga värden från den tidigare profilen överförs till den nya profilen.

* Varor som förfaller vid besök kopieras inte till den autentiserade profilen. Observera att värdet `car` ovan inte bevaras.
* Varor som har satts till att upphöra att gälla av andra åtgärder kopieras till den autentiserade profilen. Observera att värdet `apple` är beständigt.
* Inga instansvärden registreras för de eVars som är beständiga. Det innebär att när du använder identifieringen av besökare på olika enheter är det möjligt att se rapporter där det unika besöksmåttet för ett eVar-värde är större än förekomstmåttet.

> [!NOTE] Om en användare är ny på din webbplats (aldrig har besökt den här enheten tidigare) och autentiseras inom ungefär 3 minuter efter att den har anlänt, kvarstår inga värden för den autentiserade profilen.

## Exempel 2

Exemplet nedan visar hur data skickas till Adobe Analytics när en kund autentiserar på en ny enhet efter att tidigare ha autentiserats på en annan enhet.

![Exempel på olika enheter 2](assets/xdevice-subsequent.jpg)

När kunden autentiserar matchas de mot den tidigare autentiserade profilen - `2947539300`. Den profil som användes i början av besöket ( `5477766334477`) används inte längre och inga data finns kvar från filen.

* Geosegmenteringsdata registreras baserat på besökets första träff och ändras inte för ett enda besök oavsett vilken enhet som används. Detta innebär att data för geosegmentering i en senare dataanslutning på en ny enhet i allmänhet inte inkluderas.
* Teknikkolumner som webbläsare, operativsystem och färgdjup registreras vid första besöket. Precis som Geo-segmenteringsvärden kopieras de inte till den sammanfogade profilen.
* Marknadskanaler skriver över andra kanaler på en efterföljande dataanslutning som innehåller en första autentisering för den enheten.
