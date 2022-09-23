---
title: Bearbetningsordning för data i Adobe Analytics
description: Lär dig ordningen på komponenter och tjänster som bearbetar data i Adobe Analytics.
source-git-commit: 0881efeb2ce4f7af96f42bc925e43ce5ba1f64a2
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 0%

---

# Bearbetningsordning för data i Adobe Analytics

Adobe erbjuder många sätt att ändra eller ändra data innan de visas i rapporter. På den här sidan visas i vilken ordning olika Adobe Analytics-funktioner bearbetar data. Du kan använda den här listan för att felsöka inkonsekvenser i data eller för att fastställa den bästa funktionen som ska användas när datajusteringar är nödvändiga.

![Behandlingsorder](assets/processing-order.png)

## Data innan de skickas till Adobe

Innan data skickas till Adobe kompileras den vanligtvis på klientsidan på något av följande sätt:

* **AppMeasurement**: En JavaScript-fil som finns på din webbplats och som refereras till på varje sida. Data skickas direkt till Adobe Analytics.
* **Adobe Experience Platform Web SDK**: En JavaScript-fil som finns på din webbplats och som refereras till på varje sida. Data skickas till Adobe Experience Edge.
* **Taggar i Adobe Experience Cloud Data Collection**: En JavaScript-fil som refereras till på varje sida och som innehåller regler som skapats i användargränssnittet för datainsamling. Adobe Analytics-tillägget är ett enklare sätt att implementera AppMeasurement. Web SDK-tillägget är ett enklare sätt att implementera Web SDK.

Om du skickar data till Adobe Experience Edge kan du konfigurera det för att vidarebefordra data till Adobe Analytics (och många andra Adobe Experience Cloud-lösningar). Oavsett implementeringsmetod skickas i slutändan en bildbegäran med önskade variabler till datainsamlingsservrarna i Adobe.

## Data som kommer till Adobe Analytics datainsamlingsservrar

När data kommer till Adobe Analytics kan du justera data efter behov med följande funktioner:

1. **Sök tabeller**: Dimensioner som förlitar sig på Adobe-interna söktabeller (t.ex. [Webbläsare](/help/components/dimensions/browser.md) dimension) matchas med motsvarande värde.
2. [**Dynamiska variabler**](/help/implement/vars/page-vars/dynamic-variables.md): Om en dynamisk variabel visas i någon del av en bildbegäran kopieras värdet över och behandlas som ett oberoende värde som flyttas framåt.
3. [**Punktregler**](/help/admin/admin/bot-removal/bot-rules.md): Använd standardfiltrering eller anpassad robotfiltrering för att exkludera data från rapportering.
4. [**Bearbetar regler**](/help/admin/admin/c-processing-rules/processing-rules.md): Anpassade regler som din organisation tillämpar på dina data. Inkluderar mappning av [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md) till respektive variabel.
5. **VISTA-regler**: Anpassade flexibla regler som tillämpas på data av en Adobe-konsult. VISTA-regler kan köras före eller efter att regler bearbetas, beroende på organisationens behov. De flesta VISTA-regler körs vanligtvis efter bearbetningsregler, men varje organisation har konfigurerats på olika sätt. Kontakta kontohanteraren för Adobe om du vill ha mer information om befintliga VISTA-regler.
6. [**Bearbetningsregler för marknadsföringskanaler**](/help/components/c-marketing-channels/c-rules.md): Du kan använda [Bearbetar regler](/help/admin/admin/c-processing-rules/processing-rules.md) för att förbereda data för användning i regler för bearbetning av marknadsföringskanaler.
7. **Geolokaliseringsdata**: Dimensioner som förlitar sig på IP-adresssökning (till exempel [Länder](/help/components/dimensions/countries.md) dimension) fylls i.
8. [**IP-förvrängning**](/help/admin/admin/general-acct-settings-admin.md): Om din organisation har valt att dölja IP-adresser i rådata, görs det när alla andra bearbetningsfunktioner har slutförts.

I det här skedet registreras den enskilda träffen i rapportsvitens datatabeller. Efter standarden [latens](latency.md) kan rapporteras.

## Ändra data efter att de har bearbetats

Data i Adobe Analytics är mestadels permanenta. Det finns dock vissa funktioner som kan möjliggöra selektiv datainjustering eller -borttagning:

* [**API för datareparation**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Redigera vissa kolumner eller ta bort önskade datarader.
* [**Datastyrning**](/help/admin/c-data-governance/an-gdpr-workflow.md): Ta bort data permanent.
* [**Klassificeringar**](/help/components/classifications/c-classifications.md): Skapa dimensioner baserat på regler eller överförda data som gör att du kan ordna data på ett annat sätt. Den underliggande rapportsvitens data ändras inte, så du kan fritt redigera eller skriva över klassificeringsdata.
* [**Virtuella rapportsviter**](/help/components/vrs/vrs-about.md): Skapa en alternativ rapportsvy som kan ändra tidsgränsen för besök eller tillåta [Enhetsövergripande analys](/help/components/cda/overview.md).
