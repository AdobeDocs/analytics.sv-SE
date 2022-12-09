---
description: Virtuella rapportsviter och märkning av flera programsviter har olika fördelar. Ta reda på vilket som är bäst för er organisation.
keywords: Virtual Report Suite, VRS
title: Virtuella rapportsviter och taggar för flera programsviter
feature: VRS
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '1753'
ht-degree: 0%

---

# Virtuella rapportsviter och taggar för flera programsviter

Med virtuella rapporteringsprogram (VRS) kan du visa data från en rapportsvit som samlar in data från era digitala resurser, men med ett segment som används permanent.

I många fall kan du använda virtuella rapportsviter för att ersätta taggning för flera programsviter. Genom att gå över till virtuella rapportsviter kan du effektivt ta bort behovet av [sekundära serveranrop](/help/admin/admin/c-server-call-usage/overage-overview.md). Din organisation har t.ex. sex olika webbplatser, där alla skickar data till sina egna rapporteringsprogram samt en kombinerad global rapportserie. Varje plats har ett sekundärt serveranrop. en till det enskilda varumärkesrapporteringsprogrammet och en andra till det globala rapportpaketet. I stället kan ni skicka data från alla webbplatser enbart till den globala rapportsviten och sedan använda flera virtuella rapportsviter för att separera varje varumärke.

Genom att ersätta taggning för flera programsviter med en global rapportserie och VRS kan ni förenkla er Adobe Analytics-implementering och minska förbrukningen av serversamtal. Detta är en god praxis som vi rekommenderar. Det finns dock vissa viktiga begränsningar av det frivilliga systemet för förtidspension att beakta. Följande riktlinjer kan hjälpa dig att avgöra om implementering av virtuella rapportsviter som bygger på en global rapportserie är rätt strategi för dig.

## Riktlinjer

Om du är osäker på om de användningsområden som beskrivs gäller för dig och din organisation, kontaktar du andra Adobe Analytics-administratörer eller din kontoansvarige på Adobe. De kan hjälpa er att bedöma era affärsbehov och ge en rekommendation.

Tänk på följande när du avgör om du ska använda taggar för flera sviter eller virtuella rapportsviter:

### Publicera segment till Adobe Experience Cloud

Delning av segment till Adobe Experience Cloud stöds inte för virtuella rapportsviter. Användare som vill dela ett segment med Experience Cloud måste ha tillgång till källrapportsviten.

Segment kan ännu inte publiceras till Adobe Experience Cloud från en virtuell rapportsvit för personalisering och målinriktning. Alla användare som publicerar segment måste ha tillgång till källrapportsviten för detta ändamål. Du vill t.ex. att användarna bara ska ha tillgång till data för sina geografiska regioner, men du vill att de ska kunna skapa och dela segment från Adobe Analytics till Adobe Experience Cloud för målinriktning i Adobe Target. I det här fallet rekommenderar Adobe att du använder taggar för flera programsviter. Om du inte har något emot att användare har tillgång till den globala rapportsviten eller att du inte behöver publicera segment för användning i andra lösningar, kan virtuella rapportsviter användas.

### Realtid och aktuella data

Realtidsrapporter stöds inte i virtuella rapportsviter eftersom data segmenteras. Aktuella data stöds inte heller i virtuella rapportsviter eftersom de inte stöder segmentering. Båda dessa funktioner är specifika för Rapporter och analyser.

[Realtidsrapporter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md) och [Aktuella data](/help/technotes/latency.md) är inte tillgängliga i virtuella rapportsviter. Detta påverkar användare som reagerar på trender som visas i rapporter och analyser inom några sekunder eller några minuter efter datainsamlingen. Det kan till exempel inkludera redaktörer i ett nyhetsrum som justerar rubriker baserat på innehållskonsumtion i realtid. Överväg att använda flera svit-taggning om du har betydande datatillgångar i realtid som är specifika för enskilda rapportsviter. Realtid och aktuella data kan fortfarande användas i den globala rapportsviten.

### Unika gränser

Om du har en global rapportserie som kombinerar ett stort antal webbplatser kan det hända att du stöter på [lågtrafik](/help/technotes/low-traffic.md) radartikel ofta. Om du använder taggar för flera programsviter är detta bara ett problem för den globala rapportsviten (det är mindre troligt att lågtrafik visas i enskilda rapportsviter). Om du använder virtuella rapportsviter delas unika gränser, vilket gör att enskilda rapportsviter även visar låg trafik. Överväg att använda flera svittaggar om du vill undvika att lagra data i låg trafik.

En stor medieorganisation äger till exempel 100 webbegenskaper. Varje fastighet publicerar ett fåtal tusen nyhetsartiklar varje månad, förutom att ha alla artiklar från tidigare månader som webbhotell. Den här organisationen använder en global rapportserie där eVar1 är &#39;Artikelnamn&#39;. I den här rapporten finns det ungefär 4 miljoner unika artikelnamn varje månad från de olika egenskaperna. Om man använder sig av en virtuell rapporteringsserie ingår de 500 000 värden som utgör merparten av trafiken i de virtuella rapporteringssviterna. De återstående 3,5 miljoner inkluderas under lågtrafik. Om du använder taggar för flera programsviter kan varje enskild rapportserie se sina egna 500 kB-värden. Den globala rapportsvitens unika gränser är densamma när du använder taggar för flera sviter och virtuella rapportsviter.

Adobe kundtjänst kan öka de unika värdegränserna för ett litet antal dimensioner, vilket helt kan eliminera detta problem. Kontakta ditt kontoteam och kundtjänst för mer information.

### Delade variabler i olika rapportsviter

Virtuella rapporteringsprogram har inte sina egna uppsättningar mått och mätvärden. de ärver dessa från sina källrapporter. Den globala rapportsviten måste fånga alla dimensioner och mätvärden för alla webbplatser. Rapportsviter har för närvarande högst 250 eVars- och 1 000 anpassade händelser.

Olika webbplatser har olika implementeringsbehov. Vissa dimensioner och händelser kan delas mellan två platser. En e-postregistrering kan till exempel använda samma händelse på flera webbplatser och utlösa samma anpassade händelse. Andra dimensioner kan vara specifika för en plats. Till exempel kan bara en av dina webbplatser ändra sin profilbild. Denna anpassade händelse skulle bara implementeras på den webbplats som stöder den.

Se till att antalet unika mått och mätvärden får plats i en enda global rapportserie. Om du ser att det finns för många unika mått eller mätvärden granskar du varje dimension inom varje implementering. Det finns troligtvis överlappningar och dimensioner som inte är avgörande för företagets framgång. Överväg att använda [klassificeringar](/help/components/classifications/c-classifications.md) också. I stället för att hämta produktnamn i eVar5 skapar du till exempel en produktnamnsklassificering som baseras på produktdimensionen. Klassificeringar i en källrapportsserie är automatiskt tillgängliga för alla beroende virtuella rapportsviter.

>[!TIP]
>
>Med introduktionen av [kuration](/help/analyze/analysis-workspace/curate-share/curate.md)kan du ändra namnet på en viss dimension eller mätvärde per VRS.

### Segmenteringsenheter

Ett virtuellt rapportpaket på en grundläggande nivå är helt enkelt ett segment som tillämpas på ett rapportpaket. Besök- och besöksbaserade dimensioner kan ge intuitiva rapportresultat.

Du har till exempel två webbplatser, A och B, som båda skickar data till en global rapportserie. En del besökare kommer ofrånkomligen över från webbplats A till webbplats B, och den här förflyttningen från den ena till den andra syns i den globala rapportsviten. Om du bygger virtuella rapportsviter för webbplatserna A och B kommer ett besök som började på plats A och slutade på plats B inte att visa en startsida i VRS B. Startsidan för besöket började på webbplats A, som är uppdelad utanför den virtuella rapportsviten.

### Valutakonvertering

Virtuella rapportsviter rapporterar inte i en annan valuta än den rapportserie som de baseras på. I Adobe Analytics kan du konvertera valutor när du kör rapporter, men växelkursen baseras på den aktuella dagen (även för historiska data).

Om din organisation gör sina analyser i en enda valuta orsakar detta inga problem. Men om ni har ett stort affärsbehov för olika regionala team som behöver se intäkterna i sin egen lokala valuta bör ni överväga att använda flersvitstaggning.

### Dataflöden

Datafeeds kan inte använda virtuella rapportsviter. Du kan dock ta emot en datafeed från en global rapportserie och sedan separera den.

Med dataflöden kan du få en daglig eller timbaserad export av alla dina Adobe Analytics-data på en enskild träffnivå. Dataflöden kan inte förhandssegmenteras innan de levereras till dig, så du kan bara ta emot en datafeed för din globala rapportserie. Om din organisation har ett starkt behov av enskilda dataflöden på ett varumärke, en egendom, en region eller annan detaljnivå bör du överväga att använda flera svittaggar.

### Dataanslutningar med partnerkonton

Vissa partnerintegreringar med Adobe i Adobe Analytics är begränsade till ett partnerkonto per rapportsvit. Vissa organisationer kan behöva flera partnerkonton för samma integrering.

Exempelvis tillåts bara en Google DCM per rapportserie. Många företag har flera DCM-konton, vilket gör att olika varumärken, affärsenheter och regioner kan hantera sina annonser separat från varandra. Det går inte att konfigurera integreringar i virtuella rapportsviter. Om du har beroende dataanslutningar med flera konton bör du överväga att använda flera svit-taggning.

### Sammanfattningsdatakällor

Med sammanfattande datakällor kan ni importera aggregerade mätvärden till Adobe Analytics på rapportsvitnivå. Eftersom överföringar av sammanfattande datakällor innehåller aggregerade mått *utan besökar-ID* kan de inte segmenteras i [!UICONTROL Visit] och [!UICONTROL Visitor] behållare. Eftersom VRS arbetar med segmentering kommer data som importeras med sammanfattningsdatakällor inte att vara tillgängliga i virtuella rapportsviter om segmentet byggs med en besöks- eller besöksbehållare.

Sammanfattningsdatakällor visas i den virtuella rapportsviten om en Träff-behållare används och om Träff-behållaren har regler som är villkorade att inkludera datakällinformationen.

>[!TIP]
>
>Datakällor med fullständig bearbetning stöder segmentering och kan användas i virtuella rapportsviter.

## Steg som ska följas om du har bestämt dig för att använda VRS

Om du väljer att ta bort sekundära serveranrop till förmån för virtuella rapportsviter:

1. Skapa virtuella rapportsviter för att matcha data i dina underordnade rapportsviter. Segmentera i en anpassad dimension som skiljer era webbplatser från varandra.
   * Om du migrerar från en befintlig taggad implementering av flera programsviter ska du jämföra den virtuella rapportsvitens segment med dina befintliga underordnade rapportsviter. Du måste se till att data är jämförbara innan du flyttar användare till den virtuella rapportsviten.
   * Det är en god vana att använda [segmentstapling](/help/components/segmentation/segmentation-workflow/seg-build.md) så att du kan redigera ett segment på en plats och låta det gälla för alla beroende virtuella rapportsviter.
   * Använd träffbehållare om du vill att virtuella rapportsviter ska vara mer ömsesidigt uteslutande.
2. När du har bekräftat att de virtuella rapportsviterna är korrekt konfigurerade tar du bort de sekundära rapportsvitens ID:n från implementeringen. Så här tar du bort sekundära rapportsviter:
   * I Adobe Analytics-tillägget i Adobe Experience Platform Data Collection klickar du på x bredvid de rapportsviter du inte längre vill använda.
   * I tidigare JavaScript-implementeringar hittar du `s.account` och ta bort alla ID:n för rapportsviten som du inte längre vill använda.
   * I samtliga fall lämnar du bara det globala/överordnade rapportsvitens ID för att samla in data för dina webbplatser och appar.
   * Gå till Admin > Rapportsviter och dölj eventuella sekundära rapportsviter som inte längre används.
