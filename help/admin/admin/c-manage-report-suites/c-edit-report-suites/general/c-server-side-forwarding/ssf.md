---
description: Vidarebefordran på serversidan är avsedd för kunder som vill dela data från Analytics till andra Experience Cloud-lösningar i realtid. När det här alternativet är aktiverat kan Analytics även skicka data till andra Experience Cloud-lösningar och dessa lösningar skicka data till Analytics under datainsamlingsprocessen.
solution: Analytics
title: Översikt över vidarebefordran på serversidan
feature: Server-Side Forwarding
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 0%

---

# Översikt över vidarebefordran på serversidan

Vidarebefordran på serversidan är avsedd för kunder som vill dela data från Analytics till andra Experience Cloud-lösningar i realtid. När det här alternativet är aktiverat kan Analytics även skicka data till andra Experience Cloud-lösningar och dessa lösningar skicka data till Analytics under datainsamlingsprocessen.

Vidarebefordran på serversidan förbättrar datainsamlingen eftersom den:

* Minskar samtal från sidan. Med vidarebefordran på serversidan [!DNL Audience Manager] Kunder behöver inte längre använda DIL för datainsamling eftersom den vidarebefordras från Analytics. Att ta bort DIL innebär att eliminera en `"/event"` ring. Färre samtal hjälper till att förbättra sidans laddningstid, vilket ger en bättre kundupplevelse på er webbplats.
* Gör att du kan utnyttja datadelning mellan Experience Cloud.
* Följer de bästa metoderna för implementering och driftsättning av kod i Audience Manager.

>[!TIP]
>
>Nuvarande Audience Manager-kunder som använder Analytics bör migrera till vidarebefordran på serversidan. Nya kunder i Adobe Analytics och Audience Manager bör implementera vidarebefordran på serversidan (i stället för DIL) som standardmetod för datainsamling och överföring.

>[!IMPORTANT]
>På uppmaning av EU:s regler om cookie-kompatibilitet har datakontroller (analyskunder) nu möjlighet att begränsa förhandsmedgivanden till Adobe Analytics och förhindra att dessa vidarebefordras till Adobe Audience Manager på serversidan. Med en ny sammanhangsvariabel för implementering kan du flagga träffar där samtycke inte har tagits emot. När variabeln är inställd hindras dessa träffar från att skickas till Adobe Audience Manager tills samtycke har erhållits. Mer information finns i [GDPR_eIntegritetsefterlevnad och vidarebefordran på serversidan](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md).

Gå igenom följande valideringssteg för att förstå var din organisation befinner sig när det gäller implementering av vidarebefordran på serversidan:

## ![step1_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) Verifiera implementering av ECID-tjänst

Kontrollera om tjänsten Experience Cloud ID (ECID) är implementerad genom att granska [Analysspårningsbegäran](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html).

Kontrollera att ett ECID-värde anges på fliken Begäran. Detta anger att identitetstjänsten implementeras på rätt sätt, vilket är en förutsättning för vidarebefordran på serversidan.

* Om du ser ett ECID-värde fortsätter du till steg 2.
* Om du inte ser något ECID-värde [implementera identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html) innan du fortsätter till steg 2.

## ![step2_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) Verifiera implementeringsversion av vidarebefordring på serversidan

Kontrollera om du redan har en version av vidarebefordran på serversidan implementerad av [inspektera Analytics-spårningsbegäran](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md).

Kontrollera att svaret innehåller data från Audience Manager på fliken&quot;Svar&quot;. Om du ser:

* A **JSON-svar från Audience Manager som innehåller bl.a. &quot;postback&quot; eller &quot;dcs_region&quot;**: någon form av vidarebefordran på serversidan är redan aktiverad. Fortsätt till steg 3.
* The **&quot;status&quot;:&quot;SUCCESS&quot;**: du har implementerat Audience Management Module, men har inte vidarebefordring på serversidan korrekt konfigurerat. Fortsätt till steg 3.
* A **2 x 2 bilder**: du har inte vidarebefordring på serversidan eller Audience Management Module implementerad. Så här korrigerar du det:

   * **Adobe Audience Manager-kunder med DIL**: koordinerar följande två objekt i nära samverkan:

      1. Ta bort DIL-koden och installera [Modul för målgruppshantering](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) sidkod.
      1. Aktivera vidarebefordran på serversidan i gränssnittet för Analytics Admin enligt beskrivningen i steg 3. Om du aktiverar den här inställningen innan du tar bort DIL-kod dupliceras data och ytterligare fakturerade serversamtal skapas till Audience Manager.

   * **Nya Adobe Audience Manager-kunder** - installera [Modul för målgruppshantering](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) sidkod och fortsätt till steg 3. Data skickas inte till Audience Manager förrän vidarebefordran på serversidan är aktiverat i steg 3.

## ![step3_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) Verifiera implementering av vidarebefordring på serversidan för rapportsviten

Kontrollera om vidarebefordran på serversidan har implementerats på rapportsvitsnivå, i stället för på den gamla spårningsservern.

Vidarebefordran på rapportsvitnivå på serversidan rekommenderas framför den äldre spårningsservermetoden eftersom du kan styra vilka data som delas från Analytics på en finare nivå. Det är också en förutsättning för integreringen av Audience Analytics.

Gå till **Analyser** > **Administratör** > **Rapportsviter** > (välj **rapportsviter**) > **Redigera inställningar** > **Allmänt** > **Vidarebefordran på serversidan**. Om kryssrutan är:

* **Inaktiv** (Du kan inte göra ett val eller så finns inte menyn): du har inte den valda rapportsviten mappad till ett organisations-ID. Kontakta kundtjänst för att kontrollera att rapportsviten är korrekt mappad.
* **Handikappade**: Du har inte aktiverat vidarebefordran på serversidan. Läs innehållet på sidan och fortsätt sedan med att aktivera funktionen.
* **Aktiverad**: Du har etablerats för vidarebefordran på serversidan. Du kan också konfigurera den här integreringen med Audience Analytics.

>[!NOTE]
>
>Data visas inte i andra Experience Cloud-lösningar, som [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html) eller [Målgrupper](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) tills alla tre stegen är slutförda. När inställningen är aktiverad tar det flera timmar innan den börjar gälla.
