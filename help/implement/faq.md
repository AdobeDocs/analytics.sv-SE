---
title: Vanliga frågor om implementering av Analytics
description: Vanliga frågor om implementering och länkar till mer information.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Vanliga frågor om implementering av Analytics

Vanliga frågor om implementering och länkar till mer information.

**Vad är skillnaden mellan variabel allokering och förfallotid?**

Allokering och förfallotid är båda inställningar som du kan tillämpa på anpassade variabler. *Allokering* används när du har ett beständigt variabelvärde och ett nytt variabelvärde. Det avgör om det gamla värdet eller det nya värdet behålls. *Förfallotid* används när du inte vill att ett variabelvärde ska fortsätta vara beständigt.

**Vad är skillnaden mellan Experience Clouds besökar-ID och Analytics besökar-ID?**

Identitetstjänsten tilldelar en unik, beständig identifierare som kan delas till andra lösningar i Experience Cloud. Analytics besökar-ID används bara av Analytics. Adobe rekommenderar att du använder Experience Clouds besökar-ID i din implementering.

**Hur ställs ett besökar-ID in om cookies blockeras?**

Om standardcookien `s_vi` inte är tillgänglig, skapas en reservcookie på webbplatsens domän med ett slumpmässigt genererat unikt ID. Denna cookie, som kallas `s_fid`, har en tvåårig förfallotid och används för reservidentifiering efter att den har ställts in.

**Hur implementerar jag videospårning med pulsslag?**

Se [Mäta ljud och video i Adobe Analytics](https://docs.adobe.com/content/help/sv-SE/media-analytics/using/media-overview.html).

**Kan ett avbrott i tjänsten hos Adobe påverka prestandan?**

Nej. JavaScript-filen finns inte på Adobes servrar, så ett driftavbrott hos Adobe påverkar inte ditt AppMeasurement-biblioteket. Om du använder Adobe Experience Platform Launch, lagras JavaScript-filen hos Akamai eller på en serverplats som bestäms av din organisation.

**Kan överföringen av data från webbläsaren till Adobes tjänster minska prestandan?**

AppMeasurement skapar ett bildobjekt på HTML-sidan och webbläsaren begär sedan bildobjektet från Adobes datainsamlingsservrar. Om datainsamlingsservrarna är långsamma eller inte svarar, kommer tråden som hanterar den aktuella begäran att fördröjas tills bilden returneras eller en timeout inträffar. Eftersom webbläsare hanterar bilder med flera trådar, får ett driftavbrott hos Adobe minimal inverkan på sidans inläsningstid, eftersom bara en tråd drabbas medan de andra fortsätter att fungera.

**Hur spårar jag en mobilapp?**

Du kan använda SDK:n för Adobe Experience Platform. Mer information finns i [översikten för SDK:n för Adobe Experience Platform](https://aep-sdks.gitbook.io/docs/).

**Vad är plugin-program?**

Plugin-program är kodfragment som utför avancerade funktioner. De utökar funktionerna i AppMeasurement och ger dig fler funktioner i implementeringen.
