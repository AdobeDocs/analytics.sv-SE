---
description: Vidarebefordran på serversidan är utformad för kunder som vill dela data från Analytics till andra Experience Cloud-lösningar i realtid. När det här alternativet är aktiverat kan Analytics även överföra data till andra Experience Cloud-lösningar och för att dessa lösningar ska skicka data till Analytics under datainsamlingsprocessen.
solution: Audience Manager
title: Översikt över vidarebefordran på serversidan
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: b7ef2f8b097540799a19c3964dfc64d59babd4a6

---


# Översikt över vidarebefordran på serversidan

Vidarebefordran på serversidan är utformad för kunder som vill dela data från Analytics till andra Experience Cloud-lösningar i realtid. När det här alternativet är aktiverat kan Analytics även överföra data till andra Experience Cloud-lösningar och för att dessa lösningar ska skicka data till Analytics under datainsamlingsprocessen.

Vidarebefordran på serversidan förbättrar datainsamlingen eftersom den:

* Minskar samtal från sidan. Med vidarebefordran på serversidan behöver [!DNL Audience Manager] kunderna inte längre använda DIL för datainsamling eftersom den vidarebefordras från Analytics. Att ta bort DIL innebär att man tar bort ett `"/event"` samtal. Färre samtal hjälper till att förbättra sidans laddningstid, vilket ger en bättre kundupplevelse på er webbplats.
* Gör att ni kan dra nytta av datadelning mellan Experience Cloud-lösningar.
* Följer de bästa metoderna för implementering och driftsättning av Audience Manager-kod.

>[!TIP]
>
>Nuvarande Audience Manager-kunder som använder Analytics bör migrera till vidarebefordran på serversidan. Nya kunder inom Adobe Analytics och Audience Manager bör implementera vidarebefordran på serversidan (i stället för DIL) som standardmetod för datainsamling och överföring.

>[!IMPORTANT]
>På uppmaning av EU:s regler om cookie-kompatibilitet har datakontroller (analyskunder) nu möjlighet att begränsa förhandsgodkännande av data till Adobe Analytics och förhindra att de vidarebefordras på serversidan till Adobe Audience Manager (AAM). Med en ny sammanhangsvariabel för implementering kan du flagga träffar där samtycke inte har tagits emot. När variabeln är inställd hindras dessa träffar från att skickas till AAM tills samtycke har erhållits. Mer information finns i [GDPR_eIntegritetsefterlevnad och vidarebefordran](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md)på serversidan.

Gå igenom följande valideringssteg för att förstå var din organisation befinner sig när det gäller implementering av vidarebefordran på serversidan:

## ![step1_icon.png image](assets/step1_icon.png) Kontrollera implementeringen av ECID-tjänsten

Kontrollera om tjänsten Experience Cloud ID (ECID) har implementerats genom att granska [Analytics Tracking-begäran](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html).

Kontrollera att ett ECID-värde anges på fliken Begäran. Detta anger att identitetstjänsten implementeras på rätt sätt, vilket är en förutsättning för vidarebefordran på serversidan.

* Om du ser ett ECID-värde fortsätter du till steg 2.
* Om du inte ser något ECID-värde [implementerar du identitetstjänsten](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) innan du fortsätter till steg 2.

## ![step2_icon.png image](assets/step2_icon.png) Verifiera implementeringsversion för vidarebefordran på serversidan

Kontrollera om du redan har en version av vidarebefordran på serversidan implementerad genom att [granska Analytics-spårningsbegäran](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

På fliken Svar kontrollerar du att svaret innehåller data för Audience Manager. Om du ser:

* A **JSON response from Audience Manager that includes such as &quot;postbacks&quot; or &quot;dcs_region&quot;**: någon form av vidarebefordran på serversidan är redan aktiverad. Fortsätt till steg 3.
* The **&quot;status&quot;:&quot;SUCCESS&quot;**: du har implementerat Audience Management Module, men inte har vidarebefordring på serversidan korrekt konfigurerat. Fortsätt till steg 3.
* En **2 x 2-bild**: du inte har vidarebefordring på serversidan eller Audience Management Module implementerad. Så här korrigerar du det:

   * **AAM-kunder med DIL**: koordinera följande två objekt i nära samverkan:

      1. Ta bort DIL-koden och installera [koden för Audience Management Module](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) .
      1. Aktivera vidarebefordran på serversidan i gränssnittet för Analytics Admin enligt beskrivningen i steg 3. Om du aktiverar den här inställningen innan du tar bort DIL-koden dupliceras data och ytterligare fakturerade serveranrop skapas till Audience Manager.
   * **Nya AAM-kunder** - installera [koden för Audience Management Module](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) och fortsätt till steg 3. Data skickas inte till Audience Manager förrän vidarebefordran på serversidan är aktiverat i steg 3.


## ![step3_icon.png image](assets/step3_icon.png) Verifiera vidarebefordran på serversidan av rapportsviten

Kontrollera om vidarebefordran på serversidan har implementerats på rapportsvitsnivå, i stället för på den gamla spårningsservern.

Vidarebefordran på rapportsvitnivå på serversidan rekommenderas framför den äldre spårningsservermetoden eftersom du kan styra vilka data som delas från Analytics på en finare nivå. Det är också en förutsättning för den här Audience Analytics-integreringen.

Gå till **Analytics** > **Admin** > **Report Suites** > (välj **rapportsviter**) > **Edit Settings** **** ****>¥General¥ >¥Serverside Forwarding¥. Om kryssrutan är:

* **Inaktiv** (Du kan inte göra en markering eller så finns inte menyn): du inte har de valda rapportsviterna mappade till din IMS-organisation. Se till att dina tillämpliga rapportsviter mappas till rätt Experience Cloud-organisation med [rapportsvitens mappningsgränssnitt](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* **Inaktiverad**: Vidarebefordran på serversidan är inte aktiverad. Läs innehållet på sidan och fortsätt sedan med att aktivera funktionen.
* **Aktiverad**: Du har etablerats för vidarebefordran på serversidan. Ni kan också konfigurera den här Audience Analytics-integreringen.

> [!NOTE] Data visas inte i andra Experience Cloud-lösningar, som [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) eller [Audience](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) , förrän alla tre stegen är slutförda. När inställningen är aktiverad tar det flera timmar innan den börjar gälla.

