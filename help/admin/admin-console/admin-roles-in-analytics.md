---
title: Administratörsroller i Adobe Analytics
description: Lär dig hur du kommer igång med Adobe Analytics, allmänna rolltyper och loggar in i användargränssnittet.
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
role: Admin
source-git-commit: a7cc0efe42ff7dc4aacc841156e25e3cab6b82f4
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 0%

---

# Administratörsroller i Adobe Analytics

Adobe Analytics stöder olika typer av administratörer. Fullständiga Adobe Analytics-administratörer har tillgång till allt i Adobe Analytics, medan andra administratörer och användare kan utföra mer specialiserade uppgifter.

>[!NOTE]
>
>Innan användare kan tilldelas roller i Adobe Analytics måste en användare tilldelas som första administratör i Experience Cloud. Den första administratören kan sedan tilldela användare i organisationen andra nyckelroller, enligt beskrivningen i den här artikeln. Mer information om den första administratören finns i [Adobe Analytics första administrationshandbok](/help/admin/admin-console/first-admin-guide.md).


## Viktiga roller i Experience Cloud och Adobe Analytics

Tänk på följande nyckelroller när du använder Adobe Analytics:

* **Fullständiga Adobe Analytics-administratörer:** Dessa användare har fullständig åtkomst till allt i Adobe Analytics, inklusive rapportsvitsinställningar och användarbehörigheter. Beroende på hur organisationen är strukturerad kan olika personer eller team ansvara för olika aspekter av Analytics-administration. En person ansvarar t.ex. för att fastställa vilka variabler som ska användas i en implementering. En annan person kan ansvara för att användarna kan dra in rapporter på rätt sätt genom att se till att alla har rätt behörigheter. Identifiera minst en användare som kan vara ansvarig för inställningarna för Analytics-rapportsviten och användarbehörigheter, och de kan bjuda in andra Analytics-administratörer därifrån.
* **Administratörer för datainsamling:** De här användarna har fullständig åtkomst till allt i Adobe Experience Platform Data Collection, inklusive publiceringsbehörigheter, skapande av behållare och användarbehörigheter. Dessa användare behöver inte nödvändigtvis vara programmerare, men det är bra att åtminstone ha en nybörjare som känner till HTML, CSS och JavaScript. De ansvarar för att samarbeta med webbplatsägarna i din organisation för att få tag på era webbplatser. Identifiera minst en användare som är ansvarig för implementeringen av din organisation, och de kan bjuda in andra administratörer för datainsamling därifrån.
* **Produktadministratör:** En produktadministratör hanterar en produkt i Admin Console samt användarrättigheter för den produkten.
* **Administratörer för produktprofiler:** Dessa användare kan lägga till eller ta bort användare i en produktprofil, justera behörighetsobjekt i sin produktprofil och tilldela eller ta bort produktprofiler till användargrupper. Produktprofiladministratörer har inte fullständig åtkomst till Adobe Analytics. De är dock idealiska för gruppledare och chefer som behöver ge och hantera åtkomst till Adobe Analytics för sitt team. Mer information om produktprofiler finns i [Produktprofiler för Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Supportadministratör**: Användarna kallas även användare som stöds och har inga ytterligare behörigheter i Analytics-gränssnittet. I stället får de ytterligare privilegier när de kommunicerar med Adobe kundtjänst. De här användarna är nästan alltid Analytics-administratörer också, eftersom det hjälper kundtjänst att felsöka problem med dem. Identifiera minst en Analytics-administratör som ansvarar för att underlätta interaktionen mellan slutanvändare och Adobe kundtjänst.
* **Webbplatsägare:** Dessa personer eller team ansvarar för kodning och utveckling av din webbplats. De behöver inga konton, men de vill arbeta med datainsamlingsadministratörer för att hämta taggkoden och implementera den på din webbplats.
* **Slutanvändare:** de här användarna visar vanligtvis rapporter och söker efter svar på affärsfrågor. Analysadministratörer ger dessa användare behörighet att arbeta i produkten.

## Ge fullständig produktadministratörsåtkomst för Analytics

Administratörer på systemnivå har inte direkt tillgång till produkter, men de kan ge sig själva tillgång genom att lägga till sig själva som produktnivåadministratör.

Så här ger du Adobe Analytics tillgång till dig själv eller andra:

1. Logga in på [Admin Console](https://adminconsole.adobe.com/) med dina Adobe ID-inloggningsuppgifter.
1. Klicka på fliken **[!UICONTROL Products]** överst. Alla produkter som köpts av organisationen finns till vänster. Klicka på **[!UICONTROL Adobe Analytics]** och sedan på knappen **[!UICONTROL New Profile]**.
1. Ge den här profilen namnet Analytics full admin access och klicka sedan på **[!UICONTROL Next]** > **[!UICONTROL Save]**.
1. Gå tillbaka till sidan Produktprofiler, klicka på den nyligen skapade profilen och klicka sedan på fliken **[!UICONTROL Permissions]**.
1. Klicka på ett av behörighetsposterna. Aktivera **[!UICONTROL Auto-include]** om det är tillgängligt. Om **[!UICONTROL Auto-include]** inte är tillgänglig klickar du på **[!UICONTROL Add all]**. Båda alternativen flyttar alla behörighetsobjekt till den högra kolumnen.
1. Klicka på **[!UICONTROL Save]**.
Upprepa ovanstående steg för alla behörighetskategorier.
1. När alla behörighetskategorier har tilldelats profilen går du tillbaka till sidan Produkter genom att klicka på **[!UICONTROL Product]** överst.
1. Klicka på **[!UICONTROL Assign Users]** under Adobe Analytics-rutan.
1. Ange den e-postadress som du vill ge fullständig Analytics-åtkomst till och tilldela dem den nya fullständiga administratörsåtkomstprofilen. Klicka på **[!UICONTROL Save]**.

Användaren har nu fullständig åtkomst till Adobe Analytics.

## Ge produktadministratörsåtkomst för datainsamling i Experience Platform

Produktadministratörsåtkomst för datainsamling i Experience Platform är nästan identisk med att ge produktadministratörsåtkomst för Analytics.

1. Logga in på [Adobe Admin Console](https://adminconsole.adobe.com) med dina Adobe ID-inloggningsuppgifter.
1. Klicka på fliken **[!UICONTROL Products]** överst. Alla produkter som köpts av organisationen finns till vänster. Klicka på **[!UICONTROL Experience Platform Launch]** och sedan på **[!UICONTROL New Profile]**.
1. Ge den här profilen namnet&quot;fullständig administratörsåtkomst för datainsamling&quot; och klicka sedan på **[!UICONTROL Done]**.
1. Gå tillbaka till sidan **[!UICONTROL Product Profiles]**, klicka på den nya profilen och klicka sedan på fliken **[!UICONTROL Permissions]**.
1. Klicka på ett av behörighetsposterna. Aktivera **[!UICONTROL Auto-include]** om det är tillgängligt. Om automatisk inkludering inte är tillgängligt klickar du på **[!UICONTROL Add all]**. Båda alternativen flyttar alla behörighetsobjekt till den högra kolumnen.
1. Klicka på **[!UICONTROL Save]**. Upprepa ovanstående steg för alla behörighetskategorier.
1. När alla behörighetskategorier har tilldelats profilen går du tillbaka till sidan Översikt genom att klicka på **[!UICONTROL Overview]** överst.
1. Klicka på **[!UICONTROL Assign Users]** under rutan [!UICONTROL Experience Platform Launch].
1. Ange den e-postadress som du vill ge fullständig Analytics-åtkomst till och tilldela dem den nya fullständiga administratörsåtkomstprofilen. Klicka på **[!UICONTROL Save]**.
1. Användaren har nu fullständig åtkomst till Experience Platform Data Collection.

## Bevilja produktadministratörsåtkomst för produktprofiler

Mer information om hur du tilldelar användare som produktprofiladministratörer finns i avsnittet Hantera produktprofiladministratörer i artikeln [Hantera produktprofiler för företagsanvändare](https://helpx.adobe.com/se/enterprise/using/manage-product-profiles.html) i användarhandboken för Enterprise.

## Nästa steg

[Skapa en rapportserie](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Låt Analytics-administratören logga in på verktyget och skapa en rapportsvit för datainsamling

[Skapa en analystaggegenskap](/help/implement/launch/create-analytics-property.md): Låt din Data Collection-administratör logga in på verktyget och skapa en egenskap som ska implementeras på din webbplats

Innan användare kan tilldelas roller i Adobe Analytics måste en användare tilldelas som första administratör i Experience Cloud. Den första administratören kan sedan tilldela användare i organisationen andra nyckelroller, enligt beskrivningen i den här artikeln.

En första administratör är startpunkten för att göra det möjligt för resten av organisationen att använda varje Experience Cloud-lösning.

När ett kontrakt har signerats

1. Provisioneringsteamet på Adobe förbereder det konto som ska skapas.

1. Den första administratören får ett e-postmeddelande med inloggningsuppgifter innan avtalets startdatum.

>[!IMPORTANT]
>
>   Vi rekommenderar starkt att du ser till att den första administratörens kontaktinformation skickas till Adobe innan kontraktet signeras.
