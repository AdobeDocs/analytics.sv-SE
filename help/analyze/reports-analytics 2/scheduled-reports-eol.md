---
title: Meddelande om att giltighetstiden har löpt ut för schemalagda rapporter
description: Adobe har för avsikt att pausa alla schemalagda rapporter som har ett skapandedatum som är längre än två år.
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 6e5039cd-0f40-44f7-b97d-eb17d9db25a4
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Meddelande om att giltighetstiden har löpt ut för schemalagda rapporter

Den 21 april 2022 meddelade vi att ett antal funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse för de tidigare annonserade [slutet på livscykeln för rapporter och analyser](https://www.adobe.com/go/analytics_rnaeol_en). Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag. Som svar på kundförfrågningar som söker en förlängning och för att underlätta övergången från rapporter och analyser har vi beslutat att utöka åtkomsten till dessa funktioner tills **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. Leveransen av rapport och dataextrahering pausas i slutet av perioden om inte schemat återaktiveras.

För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023, innan du måste migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics.

Alla schemalagda rapporter som fortfarande ska skickas kan återaktiveras genom att logga in i Analytics och öppna [!UICONTROL Scheduled Reports] chef. Klicka på **[!UICONTROL Edit]** och ange en ny schemalagd tid och förfallotid. Alla rapporter som återaktiveras har en standardförfallotid på 9 månader, såvida inte ett kortare förfallodatum väljs.

För rapporter med ett skapandedatum som är mindre än två år utan förfallodatum (eller med ett förfallodatum som är längre än två år) används ett standardförfallodatum på nio månader. Det nya förfallodatumet är 15 december 2022. Du kan redigera det här förfallodatumet så att det är mindre än 9 månader, men inte större.

Alla ändringar av en befintlig schemalagd rapport utan förfallodatum kräver ett förfallodatum på 9 månader eller mindre. I annat fall kan du inte spara några redigeringar eller ändringar i rapporten.

Den schemalagda rapporten pausas när den upphör att gälla. Rapporten kan dock återaktiveras med ett nytt 9-månaders förfallodatum. Inga rapporter eller data tas bort.

## Ny styrningspolicy

Syftet med denna åtgärd är att effektivt hantera och underhålla våra schemalagda rapporter medan vi förbereder för det tidigare utgivna slutet av livscykeln för rapporter och analyser. Detta kommer att fungera i takt med att vår nya styrningspolitik utvecklas:

* Inga nya schemalagda rapporter kan skapas efter den 31 januari 2023.
* Efter den 31 januari 2023 har alla schemalagda rapporter ett maximalt förfallodatum på 9 månader.
* Efter 9 månader har förfallna uppgifter pausats och kan återaktiveras, om det fortfarande behövs, till och med den 31 december 2023.
* Den 31 december 2023 kommer rapporter och analyser att bli inaktuella.
* Från och med den 31 januari 2023 kan du inte längre ställa in nya datautdrag. Befintliga kommer att fortsätta att köras, men inga nya kan schemaläggas.

Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst.
