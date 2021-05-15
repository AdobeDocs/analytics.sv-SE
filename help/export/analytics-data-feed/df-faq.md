---
description: Vanliga frågor och svar om dataflöden
keywords: Datautmatning;jobb;förkolumn;efterkolumn;skiftlägeskänslighet
title: Vanliga frågor om dataflöden
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 7312b61b8d73f45afa3eb9aac73cc4d5fd39bc82
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 0%

---

# Vanliga frågor om dataflöden

Vanliga frågor och svar om dataflöden.

## Måste feed-namnen vara unika?{#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Namnen på datafeedsfilerna består av rapportsvitens ID och datumet. Alla två flöden som är konfigurerade för samma RSID och datum får samma filnamn. Om dessa flöden levereras till samma plats skriver en fil över den andra. Om du vill förhindra att en fil skrivs över kan du inte skapa en feed som kan skriva över en befintlig feed på samma plats.

Om du försöker skapa en feed när det finns en annan med samma filnamn visas följande meddelande:

Om du får det här felet bör du tänka på följande tillfälliga lösningar:

* Ändra leveransväg
* Ändra datumen om möjligt
* Ändra rapportsviten om det är möjligt

## När behandlas data? {#section_6346328F8D8848A7B81474229481D404}

Innan timdata eller dagliga data bearbetas väntar dataflödena tills alla träffar som matades in inom tidsramen (dag eller timme) har skrivits ut till data warehouse. När detta inträffar samlar dataflödena in data med tidsstämplar som ligger inom tidsramen, komprimerar dem och skickar dem via FTP. För timmatningar skrivs filer vanligtvis ut till data warehouse inom 15-30 minuter efter timmen, men det finns ingen fast tidsperiod. Om det inte fanns några data med tidsstämplar som ligger inom tidsramen försöker processen igen nästa tidsram. Den aktuella dataflödesprocessen använder fältet `date_time` för att avgöra vilka träffar som tillhör timmen. Det här fältet baseras på rapportsvitens tidszon.

## Vad är skillnaden mellan kolumner med ett `post_`-prefix och kolumner utan ett `post_`-prefix?

Kolumner utan `post_`-prefixet innehåller data exakt som de skickades till datainsamlingen. Kolumner med ett `post_`-prefix innehåller värdet efter bearbetning. Exempel som kan ändra ett värde är variabelbeständighet, bearbetningsregler, VISTA-regler, valutakonvertering eller annan logik på serversidan som gäller Adobe. Adobe rekommenderar att du använder `post_`-versionen av en kolumn där det är möjligt.

Om en kolumn inte innehåller en `post_`-version (till exempel `visit_num`) kan kolumnen betraktas som en postkolumn.

## Hur hanterar dataflöden skiftlägeskänslighet?

I Adobe Analytics betraktas de flesta variabler som skiftlägeskänsliga i rapporteringssyfte. Till exempel betraktas alla&quot;snö&quot;,&quot;snö&quot;,&quot;snö&quot; och&quot;sNow&quot; som samma värde. Skiftlägeskänsligheten bevaras i dataflöden.

Om du ser olika skiftlägesvariationer av samma värde mellan icke-post- och postkolumner (till exempel&quot;snö&quot; i pre-kolumnen och&quot;Snö&quot; i post-kolumnen), använder implementeringen både versaler och gemener på webbplatsen. Skiftlägesvariationen i postkolumnen överfördes tidigare och lagras i den virtuella cookien, eller bearbetades samtidigt för rapportsviten.

## Filtreras robotar av administratörskonsolens robotregler i dataflöden?

Dataflöden inkluderar inte botar som filtrerats av [administratörskonsolens robotregler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Varför ser jag flera `000`-värden i `event_list`- eller `post_event_list`-dataflödeskolumnen?

Vissa kalkylbladsredigerare, särskilt Microsoft Excel, rundar automatiskt av stora tal. Kolumnen `event_list` innehåller många kommaavgränsade tal, vilket ibland kan göra att Excel hanterar den som ett stort antal. Det avrundar de sista siffrorna till `000`.

Adobe rekommenderar att du inte öppnar `hit_data.tsv`-filer automatiskt i Microsoft Excel. Använd i stället Excel-dialogrutan Importera data och se till att alla fält behandlas som text.

## Varför saknas information i domänkolumnen för vissa bärare? {#section_B7508D65370442C7A314EAED711A2C75}

Vissa mobiloperatörer (som T-Mobile och O1) tillhandahåller inte längre domäninformation för omvända DNS-sökningar. Därför är dessa data inte tillgängliga för domänrapportering.

## Varför kan jag inte extrahera&quot;timvisa&quot; filer från data som är mer än 7 dagar gamla?

För data som är äldre än 7 dagar kombineras en dags&quot;timvisa&quot;-filer till en enda&quot;daglig&quot; fil.

Exempel: En ny datafeed skapas den 9 mars 2021 och informationen från 1 januari 2021 till 9 mars levereras som &quot;Varje timme&quot;. Filerna&quot;Varje timme&quot; före 2 mars 2021 kombineras dock i en enda&quot;daglig&quot; fil. Du kan bara extrahera&quot;timvisa&quot; filer från data som är mindre än 7 dagar gamla från det datum då de skapades. I detta fall från den 2 mars till den 9 mars.

## Vilken inverkan har Daylight Savings på timdataflöden? {#section_70E867D942054DD09048E027A9474FFD}

För vissa tidszoner ändras tiden två gånger per år på grund av DST-definitioner (sommartid). Datafeeds följer den tidszon som rapportsviten har konfigurerats för. Om tidszonen för rapportsviten är en som inte använder DST, fortsätter filleveransen normalt som någon annan dag. Om tidszonen för rapportsviten är en som använder DST, ändras filleveransen för den timme då tidsändringen inträffar (vanligen 02:00).

När man gör STD -> DST-övergångar (&quot;Spring Forward&quot;) får man bara 23 filer. Timmen som hoppas över i DST-övergången utelämnas. Om övergången till exempel sker kl. 2 får de en fil för 1:00 timme och en fil för 3:00 timme. Det finns ingen 2:00-fil eftersom den vid 2:00 STD blir 3:00 DST.

När man gör DST -> STD-övergångar (&quot;Fall Back&quot;) får man 24 filer. Övergångstimmen innehåller emellertid faktiskt två timmars data. Om övergången till exempel sker klockan 2:00 fördröjs filen för 1:00 med en timme, men den innehåller data i två timmar. Den innehåller data från 1:00 DST till 2:00 STD (som skulle ha varit 3:00 DST). Nästa fil börjar klockan 2:00 STD.

## Hur hanterar Analytics FTP-överföringsfel? {#section_4BD44E9167F0494FB2B379D2BA132AD8}

I händelse av ett FTP-överföringsfel (inloggning nekad, förlorad anslutning, slut på kvot osv.) försöker Adobe automatiskt ansluta och skicka data upp till tre gånger. Om felet kvarstår markeras feeden som misslyckad och ett e-postmeddelande skickas.

Om överföringen misslyckas kan du köra ett jobb igen tills det lyckas.

Om du har problem med att få en datafeed att visas på FTP-platsen kan du läsa [Felsöka jobb](jobs-troubleshooting.md).

## Hur skickar jag om ett jobb? {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

När du har verifierat/korrigerat leveransproblemet kör du jobbet igen för att hämta filerna.

## Vad är inställningen BucketOwnerFullControl för Amazon S3-dataflöden? {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Ett vanligt användningsexempel för Amazon S3 är att kontoägaren för Amazon Web Services (AWS) skapar en bucket, sedan skapar en användare som har behörighet att skapa objekt i den bucket och sedan anger inloggningsuppgifter för den användaren. I det här fallet tillhör en användares objekt samma konto och kontoägaren har implicit fullständig kontroll över objektet (läs, ta bort osv.). Den här processen liknar hur FTP-leverans fungerar.

AWS gör det även möjligt för en användare att skapa objekt i en bucket som tillhör ett annat användarkonto. Om till exempel två AWS-användare, userA och userB, inte tillhör samma AWS-konto men vill skapa objekt i andra bucket. Om userA skapar en bucket, till exempel bucketA, kan han eller hon skapa en bucket-princip som uttryckligen tillåter userB att skapa objekt i bucketA även om användaren inte äger bucket. Den här principen kan vara fördelaktig eftersom den inte kräver att userA och userB utbyter autentiseringsuppgifter. I stället förser userB userA med sitt kontonummer och userA skapar en bucket-princip som i huvudsak säger&quot;let userB create objects in bucketA&quot;.

**** BucketOwnerFullControlger korskontobehörighet för att skapa objekt i andra grupper. Om userB överför ett objekt till userA:s bucket&quot;äger&quot; userB fortfarande det objektet, och som standard beviljas inte userA några behörigheter till det objektet trots att userA äger bucket. Detta beror på att objekt inte ärver behörigheter från den överordnade bucket. UserB måste uttryckligen tilldela userA-behörigheter eftersom userB fortfarande är objektets ägare. För att ge den här behörigheten måste userB överföra objektet med en BucketOwnerFullControl ACL, som anger att bucket-ägaren (userA) har fullständig behörighet till objektet (läs, skriv, ta bort osv.), även om objektet är&quot;ägt&quot; av userB.

>[!MORELIKETHIS]
>
>* [Felsöka jobb](jobs-troubleshooting.md)

