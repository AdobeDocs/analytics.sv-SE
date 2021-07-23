---
description: Data som samlas in från webbplatser, mobilappar eller överförs med hjälp av webbtjänste-API:er eller datakällor behandlas och lagras i Adobe Data warehouse. Dessa råa klickströmsdata utgör den datauppsättning som används av Adobe Analytics.
keywords: klickström;datafeed;datafeed;datafeed
title: Översikt över Analytics Data Feed
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 5%

---

# Översikt över Analytics Data Feed

Dataflöden är ett kraftfullt sätt att få ut rådata från Adobe Analytics. Dessa rådata kan användas på andra plattformar utanför Adobe efter eget gottfinnande. Data levereras i timbatchar vid varje timmes slut, eller i dagliga satser vid varje dags slut.

## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder dataflöden.

* Ha en FTP-plats och autentiseringsuppgifter tillgängliga. Dataflöden kan bara skickas till ett servermål. Din organisation tillhandahåller vanligtvis FTP-autentiseringsuppgifter. Adobe kan tillhandahålla en FTP-plats med en liten mängd lagringsutrymme på din begäran. Kontakta kundtjänst om du vill begära en FTP-destination för dataflöden.
* En fungerande implementering som skickar data till Adobe datainsamlingsservrar. Se [Validera och publicera en implementering](/help/implement/launch/validate-publish-prod.md) i Implementera användarhandboken.
* Ditt konto är en produktadministratör för Analytics, eller så tillhör ditt konto en produktprofil med tillgång till dataflöden.

## Steg för att komma igång

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
3. Navigera till Admin > Dataflöden i det övre navigeringsfältet.
4. Klicka på [!UICONTROL Add]. En ny sida med tre huvudkategorier visas: [!UICONTROL Feed information], [!UICONTROL Destination] och [!UICONTROL Data Column Definitions].
5. Fyll i [!UICONTROL Feed Information]-fält.
   * Namn: Alla önskade namn, till exempel &quot;Test data feed&quot;.
   * Rapportsvit: Välj önskad rapportsvit.
   * Mejla när det är klart: Ange din e-postadress.
   * Feedintervall: Välj önskat intervall (timme eller dag).
   * Fördröjning: Kan lämnas som [!UICONTROL No Delay].
   * Start- och slutdatum: Välj ett startdatum från flera dagar sedan och idag som slutdatum.
6. Fyll i [!UICONTROL Destination]-fält.
   * Typ: FTP
   * Värd: Ange önskad mål-URL för FTP. Exempel, `ftp://ftp.omniture.com`.
   * Sökväg: Kan lämnas tomt
   * Användarnamn: Ange användarnamnet för att logga in på FTP-platsen.
   * Lösenord och bekräfta lösenord: Ange lösenordet för att logga in på FTP-platsen.
7. Fyll i [!UICONTROL Data Column Definitions].
   * Välj den senaste mallen All Adobe Columns (Alla) i listrutan.
   * Komprimeringsformat: Gzip
   * Paketeringstyp: Flera filer
   * Manifest: Ingen fil
8. Klicka på [!UICONTROL Save] överst till höger.
9. När data har sparats börjar den historiska databearbetningen. När data har bearbetats för en dag placeras filen på FTP-platsen.
10. Logga in på FTP-webbplatsen med Utforskaren i Windows eller en dedikerad FTP-klient.
11. Hämta den komprimerade datafeeden till din lokala dator.
12. Zippa upp den komprimerade filen med ett program som stöder `.tar.gz` filtillägg.
13. Öppna `hit_data.tsv`-filen i kalkylbladet eller det databasprogram du vill använda för att visa rådata för den dagen.

## Nästa steg

När ni förstår det grundläggande arbetsflödet för att hämta dataflöden kan ni arbeta med team inom organisationen för att lagra eller importera rådata till en databas.

* [Skapa en datafeed](create-feed.md): Teknisk information för att skapa en datafeed, förklara enskilda fält mer i detalj
* [Hantera dataflöden](df-manage-feeds.md): Läs mer om navigering i dataflödesgränssnittet
* [Innehåll](c-df-contents/datafeeds-contents.md) i datafeed: Förstå vad som finns i den komprimerade filen
* [Datakolumndefinitioner](c-df-contents/datafeeds-reference.md): En omfattande lista med alla tillgängliga kolumner

## Ytterligare resurser

Video som navigerar i datafeedgränssnittet:

>[!VIDEO](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/data-feeds/data-feeds-management-ui.html)
