---
description: Vidarebefordran på serversidan är avsedd för kunder som vill dela data från Analytics till andra Experience Cloud-lösningar i realtid. När det här alternativet är aktiverat kan vidarebefordran på serversidan även skicka data till andra Experience Cloud-lösningar och för att dessa lösningar ska skicka data till Analytics under datainsamlingsprocessen.
solution: Audience Manager
title: Översikt över vidarebefordran på serversidan
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 2%

---


# Översikt över vidarebefordran på serversidan

Vidarebefordran på serversidan är avsedd för kunder som vill dela data från Analytics till andra Experience Cloud-lösningar i realtid. När det här alternativet är aktiverat kan vidarebefordran på serversidan även skicka data till andra Experience Cloud-lösningar och för att dessa lösningar ska skicka data till Analytics under datainsamlingsprocessen.

Vidarebefordran på serversidan förbättrar datainsamlingen eftersom den:

* Minskar samtal från sidan. Med vidarebefordran på serversidan behöver [!DNL Audience Manager] kunderna inte längre använda DIL för datainsamling eftersom den vidarebefordras från Analytics. Att ta bort DIL innebär att man tar bort ett `"/event"` samtal. Färre samtal hjälper till att förbättra sidans laddningstid, vilket ger en bättre kundupplevelse på er webbplats.
* Gör att du kan utnyttja datadelning mellan Experience Cloud.
* Följer de bästa metoderna för implementering och driftsättning av kod i Audience Manager.

>[!TIP]
>
>Nuvarande Audience Manager-kunder som använder Analytics bör migrera till vidarebefordran på serversidan. Nya kunder som använder Adobe Analytics och Audience Manager bör implementera vidarebefordran på serversidan (i stället för DIL) som standardmetod för datainsamling och överföring.

>[!IMPORTANT]
>På uppmaning av EU:s regler om cookie-kompatibilitet har personuppgiftsansvariga (Analytics-kunder) nu möjlighet att begränsa förhandsmedgivanden till Adobe Analytics och förhindra att dessa vidarebefordras till Adobe Audience Manager (AAM) på serversidan. Med en ny sammanhangsvariabel för implementering kan du flagga träffar där samtycke inte har tagits emot. När variabeln är inställd hindras dessa träffar från att skickas till AAM tills samtycke har erhållits. Mer information finns i [GDPR_eIntegritetsefterlevnad och vidarebefordran](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md)på serversidan.

Gå igenom följande valideringssteg för att förstå var din organisation befinner sig när det gäller implementering av vidarebefordran på serversidan:

## ![step1_icon.png image](assets/step1_icon.png) Kontrollera implementeringen av ECID-tjänsten

Kontrollera om tjänsten Experience Cloud ID (ECID) är implementerad genom att granska [Analytics](https://docs.adobe.com/content/help/en/id-service/using/implementation/test-verify.html)-spårningsbegäran.

Kontrollera att ett ECID-värde anges på fliken Begäran. Detta anger att identitetstjänsten implementeras på rätt sätt, vilket är en förutsättning för vidarebefordran på serversidan.

* Om du ser ett ECID-värde fortsätter du till steg 2.
* Om du inte ser något ECID-värde [implementerar du identitetstjänsten](https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html) innan du fortsätter till steg 2.

## ![step2_icon.png image](assets/step2_icon.png) Verifiera implementeringsversion för vidarebefordran på serversidan

Kontrollera om du redan har en version av vidarebefordran på serversidan implementerad genom att [granska Analytics-spårningsbegäran](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

Kontrollera att svaret innehåller Audience Manager data på fliken&quot;Svar&quot;. Om du ser:

* Ett **JSON-svar från Audience Manager som innehåller bl.a. &quot;postback&quot; eller &quot;dcs_region&quot;**: någon form av vidarebefordran på serversidan är redan aktiverad. Fortsätt till steg 3.
* The **&quot;status&quot;:&quot;SUCCESS&quot;**: du har implementerat Audience Management Module, men inte har vidarebefordring på serversidan korrekt konfigurerat. Fortsätt till steg 3.
* En **2 x 2-bild**: du inte har vidarebefordring på serversidan eller Audience Management Module implementerad. Så här korrigerar du det:

   * **AAM-kunder med DIL**: koordinera följande två objekt i nära samverkan:

      1. Ta bort DIL-koden och installera [koden för Audience Management Module](https://docs.adobe.com/content/help/en/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) .
      1. Aktivera vidarebefordran på serversidan i användargränssnittet för Analytics Admin enligt beskrivningen i steg 3. Om du aktiverar den här inställningen innan du tar bort DIL-koden dupliceras data och ytterligare fakturerade serversamtal skapas till Audience Manager.
   * **Nya AAM-kunder** - installera [koden för Audience Management Module](https://docs.adobe.com/content/help/en/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) och fortsätt till steg 3. Data skickas inte till Audience Manager förrän vidarebefordran på serversidan är aktiverat i steg 3.


## ![step3_icon.png image](assets/step3_icon.png) Verifiera vidarebefordran på serversidan av rapportsviten

Kontrollera om vidarebefordran på serversidan har implementerats på rapportsvitsnivå, i stället för på den gamla spårningsservern.

Vidarebefordran på rapportsvitnivå på serversidan rekommenderas framför den äldre spårningsservermetoden eftersom du på en mer detaljerad nivå kan kontrollera vilka data som delas från Analytics. Det är också en förutsättning för denna integrering med Audience Analytics.

Gå till **Analytics** > **Admin** > **Rapportsviter** > (välj **rapportsviter**) > **Redigera inställningar** **** ****>¥General¥ >¥Serversidvidarebefordring¥. Om kryssrutan är:

* **Inaktiv** (Du kan inte göra en markering eller så finns inte menyn): du inte har de valda rapportsviterna mappade till din IMS-organisation. Se till att dina tillämpliga rapportsviter mappas till rätt Experience Cloud-organisation med hjälp av [rapportsvitens mappningsgränssnitt](https://docs.adobe.com/content/help/sv-SE/core-services/interface/about-core-services/report-suite-mapping.html).
* **Inaktiverad**: Vidarebefordran på serversidan är inte aktiverad. Läs innehållet på sidan och fortsätt sedan med att aktivera funktionen.
* **Aktiverad**: Du har etablerats för vidarebefordran på serversidan. Du kan också konfigurera denna integrering med Audience Analytics.

>[!NOTE]
>
>Data visas inte i andra Experience Cloud-lösningar, som [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html) eller [Publiker](https://docs.adobe.com/content/help/sv-SE/core-services/interface/audiences/audience-library.html) , förrän alla tre stegen är klara. När inställningen är aktiverad tar det flera timmar innan den börjar gälla.

