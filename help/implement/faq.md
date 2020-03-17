---
title: Frågor och svar om Analytics-implementering
description: Frågor och svar om implementering och länkar till mer information.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Frågor och svar om Analytics-implementering

Frågor och svar om implementering och länkar till mer information.

**Vad är skillnaden mellan variabel allokering och förfallodatum?**

Allokering och förfallodatum är båda inställningar som du kan tillämpa på anpassade variabler. *Allokering* spelas upp när du har ett beständigt variabelvärde och ett nytt variabelvärde. Det avgör om det gamla värdet eller det nya värdet behålls. *Förfallotid* inträffar när du inte vill att ett variabelvärde ska fortsätta att gälla.

**Vad är skillnaden mellan besökar-ID:t för Experience Cloud och besökar-ID:t för Analytics?**

Identitetstjänsten tilldelar en unik, beständig identifierare som kan delas med andra lösningar i Experience Cloud. Besökar-ID:t för Analytics används bara av Analytics. Adobe rekommenderar att du använder Experience Cloud Visitor ID-tjänsten i din implementering.

**Hur anges ett besökar-ID om cookies blockeras?**

Om standardcookien inte är tillgänglig skapas en reservcookie på webbplatsens domän med ett slumpmässigt genererat unikt ID. `s_vi` Denna cookie, med namnet `s_fid`, har en tvåårig förfallotid och används som identifieringsmetod för reservlösningar.

**Hur implementerar jag videospårning med pulsslag?**

Se [Mäta ljud och video i Adobe Analytics](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).

**Kan ett avbrott i tjänsten hos Adobe påverka prestandan?**

Nej. JavaScript-filen finns inte på Adobe-servrar, så ett Adobe-avbrott påverkar inte AppMeasurement-biblioteket. Om du använder Adobe Experience Platform Launch lagras JavaScript-filen av Akamai, eller på en serverplats som bestäms av din organisation.

**Kan överföringen av data från webbläsaren till Adobes tjänster minska prestandan?**

AppMeasurement skapar ett bildobjekt på HTML-sidan och webbläsaren begär sedan bildobjektet från Adobes datainsamlingsservrar. Om datainsamlingsservrarna var långsamma eller inte svarade kommer trådhanteringen som begärdes att fördröjas tills bilden returneras eller en timeout inträffar. Eftersom webbläsare hanterar bilder med flera trådar skulle ett Adobe-avbrott ha minimal inverkan på sidans inläsningstid, vilket gör att en tråd kopplas ihop medan de andra fortfarande fungerar.

**Hur spårar jag en mobilapp?**

Du kan använda Adobe Experience Platform SDK. Mer information finns i Översikt över SDK för [Adobe Experience Platform](https://aep-sdks.gitbook.io/docs/) .

**Vad är plugin-program?**

Plugin-program är kodfragment som utför avancerade funktioner. De utökar funktionerna i AppMeasurement för att ge fler funktioner i implementeringen.
