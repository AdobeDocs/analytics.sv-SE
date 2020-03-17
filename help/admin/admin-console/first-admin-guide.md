---
title: Adobe Analytics First Admin Guide
description: Lär dig hur du kommer igång med Adobe Analytics, allmänna rolltyper och loggar in i användargränssnittet.
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Adobe Analytics First Admin Guide

En första administratör är utgångspunkten när det gäller att göra det möjligt för resten av organisationen att använda varje Experience Cloud-lösning. När ett kontrakt har undertecknats förbereder ett provisioneringsteam på Adobe det konto som ska skapas. Den första administratören får ett e-postmeddelande med inloggningsuppgifter innan avtalets startdatum. Vi rekommenderar starkt att du ser till att den första administratörens kontaktinformation skickas till Adobe och att den är korrekt innan avtalet signeras.

## Viktiga roller i Experience Cloud

Om din organisation har köpt Adobe Analytics finns det flera viktiga roller att tänka på:

- **Adobe Analytics-administratörer:** Dessa användare har fullständig tillgång till allt i Adobe Analytics, inklusive rapportsvitsinställningar och användarbehörigheter. Beroende på hur organisationen är strukturerad kan olika personer eller team ansvara för olika aspekter av Analytics-administration. En person ansvarar t.ex. för att fastställa vilka variabler som ska användas i en implementering. En annan person kan ansvara för att användarna kan dra in rapporter på rätt sätt genom att se till att alla har rätt behörigheter. Identifiera minst en användare som kan vara ansvarig för inställningarna för Analytics-rapportsviten och användarbehörigheter, och de kan bjuda in andra Analytics-administratörer därifrån.
- **Adobe Experience Platform Launch-administratörer:** Dessa användare har fullständig åtkomst till allt i Experience Platform Launch, inklusive publiceringsbehörigheter, skapande av behållare och användarbehörigheter. De här användarna behöver inte nödvändigtvis vara programmerare, men det är bra att åtminstone ha en nybörjarkunskap om HTML, CSS och JavaScript. De ansvarar för att samarbeta med webbplatsägarna i din organisation för att implementera koden för Experience Platform Launch på din webbplats. Identifiera minst en användare som kan vara ansvarig för implementeringen av din organisation, och de kan bjuda in andra Experience Platform Launch-administratörer därifrån.
- **Webbplatsägare:** Dessa personer eller team ansvarar för kodningen och utvecklingen av er webbplats. De behöver inga konton, men de vill arbeta med Experience Platform Launch-administratörer för att få koden Experience Platform Launch och implementera den på er webbplats.
- **Slutanvändare:** de här användarna tittar vanligtvis på rapporter och söker svar på affärsfrågor. Analysadministratörer ger dessa användare behörighet att arbeta i produkten.

Som första administratör kan din roll överlappa en eller flera av de här rollerna. Så länge var och en av dessa grundläggande ansvarsområden täcks kan du ge behörigheter för att få andra i organisationen att komma igång.

## Bevilja produktadministratörsåtkomst för Analytics

Administratörer på systemnivå har inte direkt tillgång till produkter, men de kan ge sig själva tillgång genom att lägga till sig själva som produktnivåadministratör. Om du vill ge dig själv eller andra tillgång till Adobe Analytics kan du följa dessa steg.

1. Logga in på [Admin Console](https://adminconsole.adobe.com/) med inloggningsuppgifterna för ditt Adobe ID.
1. Klicka på fliken Produkter överst. Alla produkter som köpts av organisationen finns till vänster. Klicka på Adobe Analytics och sedan på knappen New Profile.
1. Ge den här profilen namnet&quot;Analytics full admin access&quot; och klicka sedan på Done.
1. Gå tillbaka till sidan Produktprofiler, klicka på den nya profilen och sedan på fliken Behörigheter.
1. Klicka på ett av behörighetsposterna. Om Automatisk inkludering är tillgängligt aktiverar du det. Om automatisk inkludering inte är tillgängligt klickar du på Lägg till alla. Båda alternativen flyttar alla behörighetsobjekt till den högra kolumnen.
1. Klicka på Spara. Upprepa ovanstående steg för alla behörighetskategorier.
1. När alla behörighetskategorier har tilldelats profilen går du tillbaka till sidan Översikt genom att klicka på Översikt överst.
1. Klicka på Tilldela användare under panelen Adobe Analytics.
1. Ange den e-postadress som du vill ge fullständig Analytics-åtkomst till och tilldela dem den nya fullständiga administratörsåtkomstprofilen. Klicka på Spara.
1. Användaren har nu full tillgång till Adobe Analytics.

## Bevilja produktadministratörsåtkomst för Experience Platform Launch

Produktadministratörsåtkomst för Experience Platform Launch är nästan identisk med att ge produktadministratörsåtkomst för Analytics.

1. Logga in på Admin Console med inloggningsuppgifter för ditt Adobe ID.
1. Klicka på fliken Produkter överst. Alla produkter som köpts av organisationen finns till vänster. Klicka på Experience Platform Launch av Adobe och sedan på knappen Ny profil.
1. Ge den här profilen namnet&quot;Experience Platform Launch full admin access&quot; och klicka sedan på Done.
1. Gå tillbaka till sidan Produktprofiler, klicka på den nya profilen och sedan på fliken Behörigheter.
1. Klicka på ett av behörighetsposterna. Om Automatisk inkludering är tillgängligt aktiverar du det. Om automatisk inkludering inte är tillgängligt klickar du på Lägg till alla. Båda alternativen flyttar alla behörighetsobjekt till den högra kolumnen.
1. Klicka på Spara. Upprepa ovanstående steg för alla behörighetskategorier.
1. När alla behörighetskategorier har tilldelats profilen går du tillbaka till sidan Översikt genom att klicka på Översikt överst.
1. Klicka på Tilldela användare under Experience Platform Launch by Adobe.
1. Ange den e-postadress som du vill ge fullständig Analytics-åtkomst till och tilldela dem den nya fullständiga administratörsåtkomstprofilen. Klicka på Spara.
1. Användaren har nu fullständig åtkomst till Experience Platform Launch.

## Nästa steg

[Skapa en rapportsvit](create-report-suite.md): Låt din Analytics-administratör logga in på verktyget och skapa en rapportserie för datainsamling

[Skapa en egenskap i Experience Platform Launch](/help/implement/launch/create-analytics-property.md): Låt Experience Platform Launch-administratören logga in på verktyget och skapa en egenskap som ska implementeras på din webbplats
