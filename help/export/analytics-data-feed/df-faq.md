---
description: Få svar på vanliga frågor om dataflöden i Adobe Analytics.
keywords: Datautmatning;jobb;förkolumn;efterkolumn;skiftlägeskänslighet
title: Vanliga frågor om dataflöden
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 0eef1b1269dcfbc7648127602bdfe24d4789f4b7
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 0%

---

# Vanliga frågor om dataflöden

Vanliga frågor och svar om dataflöden.

## Måste feed-namnen vara unika?{#unique}

Namnen på datafeedsfilerna består av rapportsvitens ID och datumet. Alla två flöden som är konfigurerade för samma RSID och datum har samma filnamn. Om dessa flöden levereras till samma plats, skriver en fil över den andra. Om du vill förhindra att en fil skrivs över kan du inte skapa en feed som kan skriva över en befintlig feed på samma plats.

Om du försöker skapa en feed när det finns en annan med samma filnamn visas ett felmeddelande. Tänk på följande tillfälliga lösningar:

* Ändra leveransväg
* Ändra datumen om möjligt
* Ändra rapportsviten om möjligt

## När bearbetas data? {#processed}

Innan timdata eller dagliga data bearbetas väntar dataflödena tills alla träffar som matade in data inom tidsramen (dag eller timme) har skrivits ut till datalagret. När detta inträffar samlar dataflödena in data med tidsstämplar som ligger inom tidsramen, komprimerar dem och skickar dem via FTP. För timmatningar skrivs filer vanligtvis ut till datalagret inom 15-30 min efter timmen, men det finns ingen angiven tidsperiod. Om det inte fanns några data med tidsstämplar som ligger inom tidsramen försöker processen igen nästa tidsram. Den aktuella dataflödesprocessen använder fältet `date_time` för att avgöra vilka träffar som tillhör timmen. Det här fältet baseras på rapportsvitens tidszon.

## Vad är skillnaden mellan kolumner med ett `post_`-prefix och kolumner utan ett `post_`-prefix? {#post}

Kolumner utan prefixet `post_` innehåller data exakt som de skickades till datainsamlingen. Kolumner med ett `post_`-prefix innehåller värdet efter bearbetning. Exempel som kan ändra ett värde är variabelbeständighet, bearbetningsregler, VISTA-regler, valutakonvertering eller annan logik på serversidan som gäller Adobe. Adobe rekommenderar att du använder `post_`-versionen av en kolumn där det är möjligt.

Om en kolumn inte innehåller en `post_`-version (till exempel `visit_num`) kan kolumnen betraktas som en inläggskolumn.

## Hur hanterar dataflöden skiftlägeskänslighet? {#case}

I Adobe Analytics betraktas de flesta variabler som skiftlägeskänsliga i rapporteringssyfte. Till exempel betraktas alla&quot;snö&quot;,&quot;snö&quot;,&quot;snö&quot; och&quot;sNow&quot; som samma värde. Skiftlägeskänsligheten bevaras i dataflöden.

Om du ser olika skiftlägesvariationer av samma värde mellan icke-post- och postkolumner (till exempel &quot;snö&quot; i pre-kolumnen och &quot;Snö&quot; i post-kolumnen), använder implementeringen både versaler och gemener på webbplatsen. Skiftlägesvariationen i postkolumnen överfördes tidigare och lagras i den virtuella cookien, eller bearbetades samtidigt för rapportsviten.

## Filtreras robotar av administratörskonsolens robotregler i dataflöden? {#bots}

Datafeeds innehåller inte bots som filtrerats av [administratörskonsolens robotregler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Varför ser jag flera `000`-värden i dataflödeskolumnen `event_list` eller `post_event_list`? {#values}

Vissa kalkylbladsredigerare, särskilt Microsoft Excel, rundar automatiskt av stora tal. Kolumnen `event_list` innehåller många kommaavgränsade tal, vilket ibland kan göra att Excel hanterar den som ett stort antal. Det avrundar de sista siffrorna till `000`.

Adobe rekommenderar att `hit_data.tsv` filer inte öppnas automatiskt i Microsoft Excel. Använd i stället Excel-dialogrutan Importera data och se till att alla fält behandlas som text.

## Är kolumner som `hitid_high`, `hitid_low`, `visid_high` och `visid_low` garanterat unika för träffen eller besöket? {#hitid}

I nästan alla fall identifierar sammanfogningen av `hitid_high` och `hitid_low` en träff unikt. Samma koncept gäller för sammanfogningen av `visid_high` och `visid_low` för besök. Bearbetningsavvikelser kan dock i sällsynta fall leda till att två träffar delar samma träff-ID. Adobe rekommenderar att man inte skapar dataflöden som inte är flexibla och som kräver att varje träff är unik.

## Varför saknas information i domänkolumnen för vissa bärare? {#domain}

Vissa mobiloperatörer (som T-Mobile och O1) tillhandahåller inte längre domäninformation för omvända DNS-sökningar. Därför är dessa data inte tillgängliga för domänrapportering.

## Varför kan jag inte extrahera&quot;timvisa&quot; filer från data som är mer än 7 dagar gamla? {#hourly}

För data som är äldre än 7 dagar kombineras en dags&quot;timvisa&quot;-filer till en enda&quot;daglig&quot; fil.

Exempel: En ny datafeed skapas den 9 mars 2021 och data från 1 januari 2021 till 9 mars levereras som &quot;Varje timme&quot;. Filerna&quot;Varje timme&quot; före den 2 mars 2021 kombineras dock i en enda&quot;daglig&quot; fil. Du kan bara extrahera&quot;timvisa&quot; filer från data som är mindre än 7 dagar gamla från det datum då de skapades. I detta fall från den 2 mars till den 9 mars.

## Vilken inverkan har Daylight Savings på timdataflöden? {#dst}

För vissa tidszoner ändras tiden två gånger per år på grund av DST-definitioner (sommartid). Datafeeds följer den tidszon som rapportsviten har konfigurerats för. Om tidszonen för rapportsviten är en som inte använder DST, fortsätter filleveransen normalt som någon annan dag. Om tidszonen för rapportsviten är en som använder DST, ändras filleveransen för den timme då tidsändringen inträffar (vanligen 02:00).

När man gör STD -> DST-övergångar (&quot;Spring Forward&quot;) får man bara 23 filer. Timmen som hoppas över i DST-övergången utelämnas. Om övergången till exempel sker kl. 2 får de en fil för 1:00 timme och en fil för 3:00 timme. Det finns ingen 2:00-fil eftersom den vid 2:00 STD blir 3:00 DST.

När man gör DST -> STD-övergångar (&quot;Fall Back&quot;) får man 24 filer. Övergångstimmen innehåller emellertid faktiskt två timmars data. Om övergången till exempel sker klockan 2:00 fördröjs filen för 1:00 med en timme, men den innehåller data i två timmar. Den innehåller data från 1:00 DST till 2:00 STD (som skulle ha varit 3:00 DST). Nästa fil börjar klockan 2:00 STD.

## Hur hanterar Analytics FTP-överföringsfel? {#ftp-failure}

Om en FTP-överföring misslyckas (på grund av nekad inloggning, förlorad anslutning, fel utanför kvoten eller något annat problem) försöker Adobe automatiskt ansluta och skicka data upp till tre gånger. Om felet kvarstår markeras feeden som misslyckad och ett e-postmeddelande skickas.

Om en överföring misslyckas kan du köra ett jobb igen tills det lyckas.

Om du har problem med att få en datafeed att visas på FTP-platsen kan du läsa [Felsöka datafeeds](troubleshooting.md).

## Hur skickar jag om ett jobb? {#resend}

När du har verifierat/korrigerat leveransproblemet kör du jobbet igen för att hämta filerna.

## Vad är inställningen BucketOwnerFullControl för Amazon S3-dataflöden? {#BucketOwnerFullControl}

**BucketOwnerFullControl** ger korskontobehörighet för att skapa objekt i andra grupper.

Det vanliga användningsområdet för Amazon S3 är att kontoägaren för Amazon Web Services (AWS) skapar en bucket, sedan skapar en användare som har behörighet att skapa objekt i den bucket och sedan anger inloggningsuppgifter för den användaren. I det här fallet tillhör en användares objekt samma konto och kontoägaren har implicit fullständig kontroll över objektet (läs, ta bort och så vidare). Den här processen liknar hur FTP-leverans fungerar.

AWS gör det även möjligt för en användare att skapa objekt i en bucket som tillhör ett annat användarkonto. Exempel: två AWS-användare, userA och userB, tillhör inte samma AWS-konto men vill skapa objekt i andra bucklar. Om userA skapar en bucket som kallas&quot;bucketA&quot; kan de skapa en bucket-princip som uttryckligen tillåter userB att skapa objekt i bucketA även om användaren inte äger bucket. Den här principen kan vara fördelaktig eftersom den inte kräver userA och userB för utbyte av autentiseringsuppgifter. I stället förser userB userA med sitt kontonummer och userA skapar en bucket-princip som i huvudsak säger&quot;let userB create objects in bucketA&quot;.

Objekten ärver dock inte behörigheter från den överordnade bucket. Om userB överför ett objekt till userA:s bucket&quot;äger&quot; därför userB fortfarande det objektet, och som standard beviljas inte userA några behörigheter till det objektet trots att userA äger bucket. UserB måste uttryckligen tilldela userA-behörigheter eftersom userB fortfarande är objektets ägare. För att ge denna behörighet måste userB överföra objektet med en BucketOwnerFullControl ACL, som anger att bucket-ägaren (userA) har fullständig behörighet till objektet (läsa, skriva, ta bort och så vidare), även om objektet är&quot;ägt&quot; av userB.

>[!NOTE]
>
>Adobe Analytics avgör inte om bucket har en princip som kräver att bucket-ägaren får fullständig kontroll över nya objekt, eller även om bucket-ägaren har ett annat konto än användaren som skriver data. I stället lägger Analytics automatiskt till bucket-ägaren i `BucketOwnerFullControl`-åtkomstkontrollistan med varje feed-överföring.

