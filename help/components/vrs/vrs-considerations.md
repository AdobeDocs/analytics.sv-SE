---
description: Virtuella rapportsviter och märkning av flera programsviter har olika fördelar. Ta reda på vilket som är bäst för er organisation.
keywords: Virtual Report Suite
title: Virtuella rapportsviter och taggar för flera programsviter
feature: VRS
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
source-git-commit: 6e9ea48df286b2bde6a071ab3d0f29a764382c6d
workflow-type: tm+mt
source-wordcount: '1634'
ht-degree: 0%

---

# Virtuella rapportsviter och taggar för flera programsviter

Med virtuella rapportsviter kan du visa data från en rapportserie som samlar in data från era digitala resurser, men med ett segment som används permanent.

I många fall kan du använda virtuella rapportsviter för att ersätta taggning för flera programsviter. Genom att växla till virtuella rapportsviter kan du effektivt ta bort behovet av [sekundära serveranrop](/help/admin/admin/c-server-call-usage/overage-overview.md). Din organisation har t.ex. sex olika webbplatser, där alla skickar data till sina egna rapporteringsprogram samt en kombinerad global rapportserie. Varje webbplats får ett sekundärt serveranrop, ett till den enskilda varumärkesrapporten och en andra till den globala rapportsviten. I stället kan ni skicka data från alla webbplatser enbart till den globala rapportsviten och sedan använda flera virtuella rapportsviter för att separera varje varumärke.

Genom att ersätta taggning för flera programsviter med en global rapportserie och Virtual Report Suite kan ni förenkla er Adobe Analytics-implementering och minska förbrukningen av serversamtal. Detta är en god praxis som vi rekommenderar. Det finns dock några viktiga begränsningar för virtuella rapportsviter att tänka på. Följande riktlinjer kan hjälpa dig att avgöra om implementering av virtuella rapportsviter som bygger på en global rapportserie är rätt strategi för dig.

## Riktlinjer

Om du är osäker på om de användningsområden som beskrivs gäller för dig och din organisation, kontaktar du andra Adobe Analytics-administratörer eller ditt kontoteam på Adobe. De kan hjälpa er att bedöma era affärsbehov och ge en rekommendation.

Tänk på följande när du avgör om du ska använda taggar för flera sviter eller virtuella rapportsviter:

### Publicera segment till Adobe Experience Cloud

Delning av segment till Adobe Experience Cloud stöds inte för virtuella rapportsviter. Användare som vill dela ett segment med Experience Cloud måste ha tillgång till källrapportsviten.

Segment kan ännu inte publiceras till Adobe Experience Cloud från en virtuell rapportsvit för personalisering och målinriktning. Alla användare som publicerar segment måste ha tillgång till källrapportsviten för detta ändamål. Du vill t.ex. att användarna bara ska ha tillgång till data för sina geografiska regioner, men du vill att de ska kunna skapa och dela segment från Adobe Analytics till Adobe Experience Cloud för målinriktning i Adobe Target. I det här fallet rekommenderar Adobe att du använder taggar för flera programsviter. Om du inte har något emot att användare har tillgång till den globala rapportsviten eller att du inte behöver publicera segment för användning i andra lösningar, kan virtuella rapportsviter användas.

### Unika (lågtrafik) gränser

Om du har en global rapportserie som kombinerar ett stort antal webbplatser, är det möjligt att du ofta stöter på [lågtrafikposten](/help/technotes/low-traffic.md). Om du använder taggar för flera programsviter är detta bara ett problem för den globala rapportsviten (det är mindre troligt att lågtrafik visas i enskilda rapportsviter). Om du använder virtuella rapportsviter delas unika gränser, vilket gör att enskilda rapportsviter även visar låg trafik. Överväg att använda flera svittaggar om du vill undvika att lagra data i låg trafik.

En stor medieorganisation äger till exempel 100 webbegenskaper. Varje fastighet publicerar ett fåtal tusen nyhetsartiklar varje månad, förutom att ha alla artiklar från föregående månader. Den här organisationen använder en global rapportserie där eVar1 är &#39;Artikelnamn&#39;. Anta att det i den här rapporten finns ungefär 5 miljoner unika artikelnamn varje månad från de olika egenskaperna. Om du använder ett virtuellt rapportpaket inkluderas bara en del av de 5 miljoner värdena i det virtuella rapportpaketet. Resten inkluderas under lågtrafik. Om du använder taggar för flera programsviter kan varje enskild rapportserie se sin egen uppsättning med unika värden.

Adobe kundtjänst kan ibland öka unika värdegränser för ett litet antal dimensioner, vilket helt kan eliminera problemet. Kontakta ditt kontoteam och kundtjänst för mer information.

### Delade variabler i olika rapportsviter

Virtuella rapportsviter har inte sina egna uppsättningar med mått och mätvärden. De ärver dessa från sin källrapportsvit. Den globala rapportsviten måste fånga alla dimensioner och mätvärden för alla webbplatser. Rapportsviter har för närvarande högst 250 eVars- och 1 000 anpassade händelser.

Olika webbplatser har olika implementeringsbehov. Vissa dimensioner och händelser kan delas mellan två platser. En e-postregistrering kan till exempel använda samma händelse på flera webbplatser och utlösa samma anpassade händelse. Andra dimensioner kan vara specifika för en plats. Till exempel kan bara en av dina webbplatser ändra sin profilbild. Den här anpassade händelsen kommer bara att implementeras på den webbplats som stöder den.

Se till att antalet unika mått och mätvärden får plats i en enda global rapportserie. Om du ser att det finns för många unika mått eller mätvärden granskar du varje dimension inom varje implementering. Det finns troligtvis överlappningar och dimensioner som inte är avgörande för företagets framgång. Du bör även använda [klassificeringar](/help/components/classifications/c-classifications.md). I stället för att hämta&quot;Produktnamn&quot; i eVar5 skapar du till exempel en produktnamnsklassificering som baseras på dimensionen&quot;Produkt&quot;. Klassificeringar i en källrapportsserie är automatiskt tillgängliga för alla beroende virtuella rapportsviter.

>[!TIP]
>
>Med introduktionen av [curation](/help/analyze/analysis-workspace/curate-share/curate.md) kan du ändra namnet på en given dimension eller ett givet mätvärde per Virtual Report Suite-bas.

### Segmenteringsenheter

Ett virtuellt rapportpaket på en grundläggande nivå är helt enkelt ett segment som tillämpas på ett rapportpaket. Besök- och besöksbaserade dimensioner kan ge intuitiva rapportresultat.

Du har till exempel två webbplatser, A och B, som båda skickar data till en global rapportserie. En del besökare kommer ofrånkomligen över från webbplats A till webbplats B, och den här förflyttningen från den ena till den andra syns i den globala rapportsviten. Om du bygger virtuella rapportsviter för webbplatserna A och B kommer ett besök som började på plats A och slutade på plats B inte att visa en startsida i Virtual Report Suite B. Startsidan för besöket började på webbplats A, som är uppdelad utanför den virtuella rapportsviten.

### Valutakonvertering

Virtuella rapportsviter rapporterar inte i en annan valuta än den rapportserie som de baseras på. I Adobe Analytics kan du konvertera valutor när du kör rapporter, men växelkursen baseras på den aktuella dagen (även för historiska data).

Om din organisation gör sina analyser i en enda valuta orsakar detta inga problem. Men om ni har ett stort affärsbehov för olika regionala team som behöver se intäkterna i sin egen lokala valuta bör ni överväga att använda flersvitstaggning.

### Dataflöden

Datafeeds kan inte använda virtuella rapportsviter. Du kan dock ta emot en datafeed från en global rapportserie och sedan separera den.

Med dataflöden kan du få en daglig eller timbaserad export av alla dina Adobe Analytics-data på en enskild träffnivå. Datafeeds kan inte förhandssegmenteras innan de levereras till dig, så du kan bara ta emot en datafeed för din globala rapportserie. Om din organisation har ett starkt behov av enskilda dataflöden på ett varumärke, en egendom, en region eller annan detaljnivå bör du överväga att använda flera svittaggar.

### Dataanslutningar med partnerkonton

Vissa partnerintegreringar med Adobe i Adobe Analytics är begränsade till ett partnerkonto per rapportsvit. Vissa organisationer kan behöva flera partnerkonton för samma integrering.

Exempelvis tillåts bara en Google DCM per rapportserie. Många företag har flera DCM-konton, vilket gör att olika varumärken, affärsenheter och regioner kan hantera sina annonser separat från varandra. Det går inte att konfigurera integreringar i virtuella rapportsviter. Om du har beroende dataanslutningar med flera konton bör du överväga att använda flera svit-taggning.

### Sammanfattningsdatakällor

Med sammanfattande datakällor kan ni importera aggregerade mätvärden till Adobe Analytics på rapportsvitnivå. Eftersom överföringar av sammanfattningsdatakällor innehåller aggregerade mått *utan besökar-ID*, kan de inte segmenteras i [!UICONTROL Visit]- och [!UICONTROL Visitor]-behållare. Eftersom den virtuella rapportsviten använder segmentering kommer data som importerats med sammanfattningsdatakällor inte att vara tillgängliga i virtuella rapportsviter om segmentet byggs med en besöks- eller besöksbehållare.

Sammanfattningsdatakällor visas i den virtuella rapportsviten om en Träff-behållare används och om Träff-behållaren har regler som är villkorade att inkludera datakällinformationen.

>[!TIP]
>
>Datakällor med fullständig bearbetning stöder segmentering och kan användas i virtuella rapportsviter.

## Steg som ska följas om du har valt att använda Virtual Report Suite

Om du väljer att ta bort sekundära serveranrop till förmån för virtuella rapportsviter:

1. Skapa virtuella rapportsviter för att matcha data i dina underordnade rapportsviter. Segmentera i en anpassad dimension som skiljer era webbplatser från varandra.
   * Om du migrerar från en befintlig taggad implementering av flera programsviter ska du jämföra den virtuella rapportsvitens segment med dina befintliga underordnade rapportsviter. Du måste se till att data är jämförbara innan du flyttar användare till den virtuella rapportsviten.
   * Det är en god idé att använda [segmentstackning](/help/components/segmentation/segmentation-workflow/seg-build.md) så att du kan redigera ett segment på en plats och låta det gälla för alla beroende virtuella rapportsviter.
   * Använd träffbehållare om du vill att virtuella rapportsviter ska vara mer ömsesidigt uteslutande.
2. När du har bekräftat att de virtuella rapportsviterna är korrekt konfigurerade tar du bort de sekundära rapportsvitens ID:n från implementeringen. Så här tar du bort sekundära rapportsviter:
   * I Adobe Analytics-tillägget i Adobe Experience Platform Data Collection klickar du på x bredvid de rapportsviter som du inte längre vill använda.
   * I tidigare JavaScript-implementeringar letar du reda på variabeln `s.account` och tar bort alla rapport-Suite-ID:n som du inte längre vill använda.
   * I samtliga fall lämnar du bara det globala/överordnade rapportsvitens ID för att samla in data för dina webbplatser och appar.
   * Gå till Admin > Rapportsviter och dölj eventuella sekundära rapportsviter som inte längre används.
