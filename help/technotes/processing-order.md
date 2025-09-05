---
title: Bearbetningsordning för data i Adobe Analytics
description: Lär dig ordningen på komponenter och tjänster som bearbetar data i Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Bearbetningsordning för data i Adobe Analytics

Adobe erbjuder många sätt att ändra eller ändra data innan de visas i rapporter. På den här sidan visas i vilken ordning olika Adobe Analytics-funktioner bearbetar data. Du kan använda den här listan för att felsöka inkonsekvenser i data eller för att fastställa den bästa funktionen som ska användas när datajusteringar är nödvändiga.

![Behandlingsorder](assets/processing-order.png)

## Data innan de skickas till Adobe

Innan data skickas till Adobe kompileras de vanligtvis på klientsidan på något av följande sätt:

* **AppMeasurement**: En JavaScript-fil som finns på din webbplats och som refereras till på varje sida. Data skickas direkt till Adobe Analytics.
* **Adobe Experience Platform Web SDK**: En JavaScript-fil som lagras på din webbplats och som refereras till på varje sida. Data skickas till Adobe Experience Platform Edge Network.
* **Taggar i Adobe Experience Cloud Data Collection**: En JavaScript-fil som refereras till på varje sida och som innehåller regler som skapats i användargränssnittet för datainsamling. Adobe Analytics-tillägget är ett enklare sätt att implementera AppMeasurement. Web SDK är ett enklare sätt att implementera Web SDK.

Om du skickar data till Edge Network kan du konfigurera det så att data vidarebefordras till Adobe Analytics (och till många andra Adobe Experience Cloud-lösningar). Oavsett implementeringsmetod skickas i slutändan en bildbegäran med de önskade variablerna till Adobe datainsamlingsservrar.

## Data som kommer till Adobe Analytics datainsamlingsservrar

När data kommer till Adobe Analytics kan du justera data efter behov med följande funktioner:

1. **Uppslagstabeller**: Dimensioner som använder Adobe-interna uppslagstabeller (till exempel dimensionen [Webbläsare](/help/components/dimensions/browser.md)) matchas mot motsvarande värde.
2. [**Dynamiska variabler**](/help/implement/vars/page-vars/dynamic-variables.md): Om en dynamisk variabel visas i någon del av en bildbegäran kopieras värdet över och behandlas som ett oberoende värde som flyttas framåt.
3. [**Punktregler**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md): Använd standard- eller anpassad robotfiltrering för att exkludera data från rapportering.
4. [**Bearbetar regler**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md): Anpassade regler som din organisation har tillämpat på dina data. Inkluderar mappningen av [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) till respektive variabel.
5. **VISTA-regler**: Anpassade flexibla regler som tillämpas på dina data av en Adobe-konsult. VISTA-regler kan köras före eller efter att regler bearbetas, beroende på organisationens behov. De flesta VISTA-regler körs vanligtvis efter bearbetningsregler, men varje organisation har konfigurerats på olika sätt. Kontakta Adobe Account Team om du vill ha mer information om befintliga VISTA-regler.
6. [**Bearbetningsregler för marknadsföringskanaler**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md): Du kan använda [Bearbetningsregler](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) för att förbereda data för användning i regler för bearbetning av marknadsföringskanaler.
7. **Geoplatsdata**: Dimensioner som förlitar sig på IP-adresssökning (till exempel dimensionen [Länder](/help/components/dimensions/countries.md)) fylls i.
8. [**IP-förfalskning**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): Om din organisation har valt att dölja IP-adresser i rådata utförs detta när alla andra bearbetningsfunktioner har slutförts.

I det här skedet registreras den enskilda träffen i rapportsvitens datatabeller. Efter standardintervallet [latens](latency.md) är det tillgängligt i rapporter.

## Ändra data efter att de har bearbetats

Data i Adobe Analytics är i huvudsak permanenta, men det finns vissa funktioner som kan möjliggöra selektiv datainjustering eller -borttagning:

* [**API för datareparation**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Redigera vissa kolumner eller ta bort önskade datarader.
* [**Datastyrning**](/help/technotes/privacy/privacy-overview.md): Acceptera sekretessförfrågningar för permanent borttagning av data.
* [**Klassificeringar**](/help/components/classifications/classifications-overview.md): Skapa dimensioner baserat på regler eller överförda data som gör att du kan ordna data på ett annat sätt. Den underliggande rapportsvitens data ändras inte, så du kan fritt redigera eller skriva över klassificeringsdata.
* [**Virtuella rapportsviter**](/help/components/vrs/vrs-about.md): Skapa en alternativ rapportsvy som kan ändra tidsgränsen för besöket eller tillåta [Enhetsövergripande analys](/help/components/cda/overview.md).
