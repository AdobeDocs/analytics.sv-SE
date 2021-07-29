---
title: Handbok för nya Adobe Analytics-administratörer
description: Lär dig hur du kommer igång med Adobe Analytics, allmänna rolltyper och loggar in i användargränssnittet.
exl-id: fbbbd335-0d22-473e-adef-f92f8eab7bf0
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 1%

---

# Handbok för nya Adobe Analytics-administratörer

En första administratör är utgångspunkten när det gäller att göra det möjligt för resten av organisationen att använda varje Experience Cloud-lösning. När ett kontrakt har undertecknats förbereder ett provisioneringsteam på Adobe för det konto som ska skapas. Den första administratören får ett e-postmeddelande med inloggningsuppgifter innan avtalets startdatum. Vi rekommenderar starkt att du ser till att den första administratörens kontaktinformation skickas till Adobe innan kontraktet signeras.

## Nyckelroller i Experience Cloud

Om din organisation har köpt Adobe Analytics finns det flera viktiga roller att tänka på:

* **Adobe Analytics-administratörer:** Dessa användare har fullständig åtkomst till allt i Adobe Analytics, inklusive rapportsvitsinställningar och användarbehörigheter. Beroende på hur organisationen är strukturerad kan olika personer eller team ansvara för olika aspekter av Analytics-administration. En person ansvarar till exempel för att identifiera vilka variabler som ska användas i en implementering. En annan person kan ansvara för att användarna kan dra in rapporter på rätt sätt genom att se till att alla har rätt behörigheter. Identifiera minst en användare som kan vara ansvarig för inställningarna för Analytics-rapportsviten och användarbehörigheter, och de kan bjuda in andra Analytics-administratörer därifrån.
* **Administratörer för datainsamling:** Dessa användare har fullständig åtkomst till allt i användargränssnittet för datainsamling (tidigare användargränssnittet i Experience Platform Launch), inklusive publiceringsbehörigheter, skapande av behållare och användarbehörigheter. De här användarna behöver inte nödvändigtvis vara programmerare, men det är bra att åtminstone ha en nybörjarkunskap om HTML, CSS och JavaScript. De ansvarar för att samarbeta med webbplatsägarna i din organisation för att implementera Experience Platform-taggarna på din webbplats. Identifiera minst en användare som är ansvarig för implementeringen av din organisation, och de kan bjuda in andra administratörer för datainsamling därifrån.
* **Supportrepresentant**: De kallas även användare som stöds och har inga ytterligare behörigheter i Analytics-gränssnittet. I stället får de ytterligare behörigheter när de kommunicerar med Adobe kundtjänst. De här användarna är nästan alltid Analytics-administratörer också, eftersom det hjälper kundtjänst att felsöka problem med dem. Identifiera minst en Analytics-administratör som ansvarar för att underlätta interaktionen mellan slutanvändare och Adobe kundtjänst.
* **Webbplatsägare:** Dessa personer eller team ansvarar för kodning och utveckling av din webbplats. De behöver inga konton, men de vill arbeta med datainsamlingsadministratörer för att hämta taggkoden och implementera den på din webbplats.
* **Slutanvändare:** dessa användare visar vanligtvis rapporter och söker svar på affärsfrågor. Analysadministratörer ger dessa användare behörighet att arbeta i produkten.

Som första administratör kan din roll överlappa en eller flera av de här rollerna. Så länge var och en av dessa grundläggande ansvarsområden täcks kan du ge behörigheter för att få andra i organisationen att komma igång.

## Bevilja produktadministratörsåtkomst för Analytics

Administratörer på systemnivå har inte direkt tillgång till produkter, men de kan ge sig själva tillgång genom att lägga till sig själva som produktnivåadministratör. Om du vill ge dig själv eller andra tillgång till Adobe Analytics kan du följa dessa steg.

1. Logga in på [Admin Console](https://adminconsole.adobe.com/) med dina inloggningsuppgifter för Adobe ID.
1. Klicka på fliken Produkter överst. Alla produkter som köpts av organisationen finns till vänster. Klicka på Adobe Analytics och sedan på knappen Ny profil.
1. Ge den här profilen namnet&quot;Analytics full admin access&quot; och klicka sedan på Done.
1. Gå tillbaka till sidan Produktprofiler, klicka på den nya profilen och sedan på fliken Behörigheter.
1. Klicka på ett av behörighetsposterna. Om Automatisk inkludering är tillgängligt aktiverar du det. Om automatisk inkludering inte är tillgängligt klickar du på Lägg till alla. Båda alternativen flyttar alla behörighetsobjekt till den högra kolumnen.
1. Klicka på Spara. Upprepa ovanstående steg för alla behörighetskategorier.
1. När alla behörighetskategorier har tilldelats profilen går du tillbaka till sidan Översikt genom att klicka på Översikt överst.
1. Klicka på Tilldela användare under rutan Adobe Analytics.
1. Ange den e-postadress som du vill ge fullständig Analytics-åtkomst till och tilldela dem den nya fullständiga administratörsåtkomstprofilen. Klicka på Spara.
1. Användaren har nu fullständig åtkomst till Adobe Analytics.

## Bevilja produktadministratörsåtkomst för datainsamling i Experience Platform

Produktadministratörsåtkomst för datainsamling i Experience Platform är nästan identisk med att ge produktadministratörsåtkomst för Analytics.

1. Logga in på [Adobe Admin Console](https://adminconsole.adobe.com) med dina inloggningsuppgifter för Adobe ID.
1. Klicka på fliken **[!UICONTROL Products]** överst. Alla produkter som köpts av organisationen finns till vänster. Klicka på **[!UICONTROL Experience Platform Launch]** och sedan på **[!UICONTROL New Profile]**.
1. Ge den här profilen namnet&quot;fullständig administratörsåtkomst för datainsamling&quot; och klicka sedan på **[!UICONTROL Done]**.
1. Gå tillbaka till sidan **[!UICONTROL Product Profiles]**, klicka på den nya profilen och klicka sedan på fliken **[!UICONTROL Permissions]**.
1. Klicka på ett av behörighetsposterna. Om **[!UICONTROL Auto-include]** är tillgängligt aktiverar du det. Om automatisk inkludering inte är tillgängligt klickar du på **[!UICONTROL Add all]**. Båda alternativen flyttar alla behörighetsobjekt till den högra kolumnen.
1. Klicka på **[!UICONTROL Save]**. Upprepa ovanstående steg för alla behörighetskategorier.
1. När alla behörighetskategorier har tilldelats profilen går du tillbaka till sidan Översikt genom att klicka på **[!UICONTROL Overview]** överst.
1. Klicka på **[!UICONTROL Assign Users]** under rutan [!UICONTROL Experience Platform Launch].
1. Ange den e-postadress som du vill ge fullständig Analytics-åtkomst till och tilldela dem den nya fullständiga administratörsåtkomstprofilen. Klicka på **[!UICONTROL Save]**.
1. Användaren har nu fullständig åtkomst till Experience Platform Data Collection.

## Nästa steg

[Skapa en rapportsvit](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Låt din Analytics-administratör logga in på verktyget och skapa en rapportserie för datainsamling

[Skapa en analystaggegenskap](/help/implement/launch/create-analytics-property.md): Låt din Data Collection-administratör logga in på verktyget och skapa en egenskap som ska implementeras på webbplatsen
