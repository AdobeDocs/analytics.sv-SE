---
description: Det här avsnittet innehåller information om vanliga problem.
keywords: Datafeed;felsökning
title: Felsöka datafeeds
uuid: 4be981ab-3a61-4099-9b0d-785d2ac2492a
exl-id: 58531afe-5e0e-49b6-9c9f-9c857be8dc75
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 0%

---

# Felsöka datafeeds

Det här avsnittet innehåller information om vanliga problem.

## Fel när feed {#section_EF38BB51A7E240D69DAD4C07A34D9AD5} sparades

Namnen på datafeedsfilerna består av rapportsvitens ID och datumet. Alla två flöden som är konfigurerade för samma RSID och datum får samma filnamn. Om dessa flöden levereras till samma plats skriver en fil över den andra. Om du vill förhindra att en fil skrivs över kan du inte skapa en feed som kan skriva över en befintlig feed på samma plats.

Om du försöker skapa en feed när det finns en annan med samma filnamn visas följande meddelande:

Om du får det här felet bör du tänka på följande tillfälliga lösningar:

* Ändra leveransväg
* Ändra datumen om möjligt
* Ändra rapportsviten om det är möjligt

## Inställningen BucketOwnerFullControl för Amazon S3-dataflöden {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Ett vanligt användningsexempel för Amazon S3 är att kontoägaren för Amazon Web Services (AWS) skapar en bucket, sedan skapar en användare som har behörighet att skapa objekt i den bucket och sedan anger inloggningsuppgifter för den användaren. I det här fallet tillhör en användares objekt samma konto, och kontoägaren har implicit fullständig kontroll över objektet (läs, ta bort osv.). Det liknar hur FTP-leverans fungerar.

AWS gör det även möjligt för en användare att skapa objekt i en bucket som tillhör ett helt annat användarkonto. Om till exempel två AWS-användare, userA och userB, inte tillhör samma AWS-konto men vill skapa objekt i andra bucket. Om userA skapar en bucket, till exempel bucketA, kan han eller hon skapa en bucket-princip som uttryckligen tillåter userB att skapa objekt i bucketA även om användaren inte äger bucket. Detta kan vara fördelaktigt eftersom det inte kräver att userA och userB utbyter autentiseringsuppgifter. I stället förser userB userA med sitt kontonummer och userA skapar en bucket-princip som i huvudsak säger&quot;let userB create objects in bucketA&quot;.

**** BucketOwnerFullControlger korskontobehörighet för att skapa objekt i andra grupper. Om userB överför ett objekt till userA:s bucket&quot;äger&quot; userB fortfarande det objektet, och som standard beviljas inte userA några behörigheter till det objektet, även om userA äger bucket. Objekten ärver inte behörigheter från den överordnade bucket. UserB måste uttryckligen tilldela userA-behörigheter eftersom userB fortfarande är objektets ägare. För denna kontoöverföring tillhandahåller AWS en BucketOwnerFullControl-åtkomstkontrollista genom att ange att användandet av denna åtkomstkontrollista av bucket-ägaren (userA) och beviljas fullständig behörighet till objektet (läsa, skriva, ta bort osv.), även om objektet är&quot;ägt&quot; av userB.

## Överföringsfel {#section_4BD44E9167F0494FB2B379D2BA132AD8}

I händelse av ett FTP-överföringsfel (inloggning nekad, förlorad anslutning, slut på kvot osv.) försöker Adobe automatiskt ansluta och skicka data upp till tre gånger. Om felet kvarstår markeras feeden som misslyckad och ett e-postmeddelande skickas.

Om överföringen misslyckas kan du köra ett jobb igen tills det lyckas.

## Alternativ för att skicka om {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

När du har verifierat/korrigerat leveransproblemet kör du jobbet igen för att hämta filerna.

## Dagsljussparande påverkan på timdataflöden {#section_70E867D942054DD09048E027A9474FFD}

För vissa tidszoner ändras tiden två gånger per år på grund av DST-definitioner (sommartid). Datafeeds följer den tidszon som rapportsviten har konfigurerats för. Om tidszonen för rapportsviten är en som inte använder DST kommer filleveransen att fortsätta som vanligt. Om tidszonen för rapportsviten är en som använder DST, ändras filleveransen för den timme då tidsändringen inträffar (vanligen 02:00).

När man gör STD -> DST-övergångar (&quot;Spring Forward&quot;) får man bara 23 filer. Timmen som hoppas över i DST-övergången utelämnas helt enkelt. Om övergången till exempel sker kl. 2 får de en fil för 1:00 timme och får en fil för 3:00 timme. Det kommer inte att finnas någon 2:00-fil, eftersom den blir 3:00 DST kl. 2:00 STD.

När man gör DST -> STD-övergångar (&quot;Fall Back&quot;) får man 24 filer. Övergångstimmen kommer dock att innehålla 2 timmars data. Om övergången till exempel sker klockan 02:00 kommer filen för 1:00 att fördröjas med en timme, men den kommer att innehålla data i två timmar. Den kommer att innehålla data från 1:00 DST till 2:00 STD (som skulle ha varit 3:00 DST). Nästa fil börjar klockan 2:00 STD.

## Inga data för en tidsperiod {#section_72510794694D42A9A75C966B812AEB0F}

Du kan konfigurera en datafeed så att den levererar en manifestfil om inga data samlas in under en viss period. Om du aktiverar det här alternativet får du en manifestfil som ser ut ungefär så här:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## Ingen domäninformation för domänrapportering {#section_B7508D65370442C7A314EAED711A2C75}

Vissa mobiloperatörer (som T-Mobile och O1) tillhandahåller inte längre domäninformation för omvända DNS-sökningar. Därför är dessa data inte tillgängliga för domänrapportering.

## Databearbetningsöversikt {#section_6346328F8D8848A7B81474229481D404}

Innan timdata eller dagliga data bearbetas väntar dataflödena tills alla träffar som matades in inom tidsramen (dag eller timme) har skrivits ut till data warehouse. När detta inträffar samlar dataflödena in data med tidsstämplar som ligger inom tidsramen, komprimerar dem och skickar dem via FTP. För timmatningar skrivs filer vanligtvis ut till data warehouse inom 15-30 minuter efter timmen, men det finns ingen fast tidsperiod. Om det inte fanns några data med tidsstämplar som ligger inom tidsramen försöker processen igen nästa tidsram. Den aktuella dataflödesprocessen använder fältet `date_time` för att avgöra vilka träffar som tillhör timmen. Det här fältet baseras på rapportsvitens tidszon.

## Dataflödesformaten &quot;Varje timme&quot; och &quot;varje dag&quot;

För data som är äldre än 7 dagar kombineras en dags&quot;timvisa&quot;-filer till en enda&quot;daglig&quot; fil.

Exempel: En ny datafeed skapas den 9 mars 2021 och informationen från 1 januari 2021 till 9 mars levereras som &quot;Varje timme&quot;. Filerna&quot;Varje timme&quot; före 2 mars 2021 kombineras dock i en enda&quot;daglig&quot; fil. Du kan bara extrahera&quot;timvisa&quot; filer från data som är mindre än 7 dagar gamla från det datum då de skapades. I detta fall från den 2 mars till den 9 mars.