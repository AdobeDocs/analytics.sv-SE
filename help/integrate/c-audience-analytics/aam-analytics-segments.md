---
description: Både Analytics och Audience Manager använder segment. Ett Analytics-segment är dock inte exakt detsamma som ett Audience Manager-segment. Dessa skillnader bidrar delvis till de skillnader som du kommer att se i dina Analytics- och Audience Manager-rapporter. Därför är det viktigt och användbart att försöka förstå dessa skillnader när du börjar arbeta med segment i båda dessa lösningar.
title: Förstå segment i Analytics och Audience Manager
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---

# Förstå segment i Analytics och Audience Manager

Både Analytics och Audience Manager använder segment. Ett Analytics-segment är dock inte exakt detsamma som ett Audience Manager-segment. Dessa skillnader bidrar delvis till de skillnader som du kommer att se i dina Analytics- och Audience Manager-rapporter. Därför är det viktigt och användbart att försöka förstå dessa skillnader när du börjar arbeta med segment i båda dessa lösningar.

## Audience Manager Segments {#aam-segments}

Ett Audience Manager-segment är en grupp besökare (användar-ID) som är kvalificerade för en uppsättning definierade egenskaper som förenas med logiska regler. Det finns fyra kriterier som avgör om en besökare (användar-ID) är en del av ett segment i Audience Manager:

* Regler anges för själva segmenten och de egenskaper som utgör varje segment. Dessa regler definierar villkoren som ett användar-ID måste uppfylla eller visa för att kvalificera sig för ett segment.
* Algoritmisk modellering. Användare som är kvalificerade för ett visst segment kan kvalificera sig för andra segment baserat på algoritmisk modellering och analys.
* TTL-intervall (Time-to-live). Segmentmedlemskap kan upphöra efter ett angivet intervall eller fortsätta i oändlighet.
* Nyhet och frekvens. Genom att definiera när och hur ofta användare har en interaktion (trait-implementering) kan du skapa segment baserat på den verkliga (eller upplevda) intressenivån på en webbplats, ett avsnitt eller en viss kreativ nivå.

Audience Manager segmentmedlemskap är smidigt. Användare kan ange eller ta bort från ett segment beroende på om de uppfyller villkoren för segmentet vid den aktuella tidpunkten eller inte. Detta innebär att befolkningen i ett Audience Manager-segment kan öka eller minska med tiden.

Ett Audience Manager-segment betecknas som en målgrupp i Analytics.

Mer information finns i [Trait and Segment Population Data in Segment Builder](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html) och [Signals, Traits och Segments](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html).

## Analyssegment {#analytics-segments}

Ett Analytics-segment är en filtreringsmekanism för data i era rapporter. Filtrering kan ske på besöks-, besöks- eller träffnivå, i stället för strikt på besökarnivå som i Audience Manager. Det finns flera viktiga faktorer att tänka på när man jämför ett Analytics-segment med ett Audience Manager-segment:

* Analyssegment använder en annan uppsättning data än Audience Manager-segment. Under datainsamlingen tillämpar Analytics många olika efterbearbetningssteg på data som inte är tillgängliga för Audience Manager. Efterbearbetningen kan omfatta eVar persistence, bearbetningsregler, uppslag (geolocation, mobile device), VISTA och många andra. Audience Manager tar emot förbearbetade data via vidarebefordran på serversidan (eller DIL).

  Vanliga datameddelanden inträffar när segment jämförs baserat på dimensioner som aldrig förfaller i Analytics, med samma dimension i Audience Manager. Till exempel listVars eller merchandising eVars som aldrig förfaller.

  Om till exempel eVar = blue och ställs in på att aldrig förfalla i Analytics, kommer alla segment i Analytics som har kriterierna &quot;eVar = blue&quot; alltid att inkludera den här besökaren. I Audience Manager kan den besökaren falla ur ett segment som är definierat på liknande sätt efter en viss tidsperiod.

* Analyssegment har fler funktioner än Adobe Audience Manager-segment. Audience Manager segment utvärderas alltid på besökarnivå. Analyssegment kan definieras på besöks-, besöks- eller träffnivå (eller en kombination av dessa nivåer). Dessutom har Analytics stöd för avancerade segmenteringsfunktioner som Audience Manager inte har, till exempel sekventiell segmentering.

* Som tidigare nämnts kan Audience Manager besökare komma in i eller släppa ut ur ett segment beroende på om de uppfyller villkoren för segmentet vid den aktuella tidpunkten eller inte.

  Omvänt kommer besökare i Analytics att inkluderas eller exkluderas från ett segment baserat på rapporteringsdatumintervallet. En enskild besökare gjorde till exempel ett köp förra månaden. I Adobe Audience Manager inkluderas besökaren i ett&quot;köpsegment&quot;, oavsett datumintervall. I Analytics skulle en rapport som baseras på den här månaden inte inkludera besökaren i segmentet. En rapport baserad på den här månaden och förra månaden skulle dock inkludera besökaren i segmentet.

Mer information finns i [segmenteringshandboken för analyser](/help/components/segmentation/seg-home.md).
