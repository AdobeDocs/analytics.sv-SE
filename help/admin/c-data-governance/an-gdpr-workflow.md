---
description: Här beskrivs stegen för hur du aktiverar din Adobe Analytics-implementering för att ge stöd åt de registrerade för åtkomst till och radering av data.
title: Arbetsflöde för sekretess
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 93%

---

# Arbetsflöde för sekretess

Det här arbetsflödet beskriver de steg du måste vidta för att göra din implementering av Adobe Analytics redo att stöda de registrerade personernas åtkomst till och rättigheter till åtkomst och radering avseende datasekretess.

| Uppgiftsbeskrivning | Länkar till instruktioner och mer information |
|--- |--- |
| **Steg 1**: Se till att alla era rapportsviter som kan innehålla data som är relevanta för datasekretess mappas till din Experience Cloud-organisation (eller IMS-organisation).  Begäranden om datasekretess skickas in via en Experience Cloud-organisation och tillämpas på alla rapporteringsprogram som den organisationen gör anspråk på. Begäranden gäller inte för rapportsviter som inte är mappade till den organisationen, även om de ingår i ditt inloggningsföretag. | Se [Mappa rapportsviter till en organisation](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Steg 2**: Ange din policy för datalagring. | Det måste finnas en policy för datalagring för att Adobe ska kunna hantera begäranden om åtkomst till/radering av data.  Mer information finns i [Vanliga frågor om lagring av analysdata](/help/technotes/data-retention.md). |
| **Steg 3**: Bekanta dig med DULE/Data Privacy-etiketter, Adobe Analytics-ID:n, namnutrymmen och ID-expansion. | Läs följande avsnitt i den här dokumentationsuppsättningen:<ul><li>[Datasekretessetiketter för analysvariabler](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Bästa praxis för etikettering](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Steg 4**: Tilldela etiketter för identitet, känslighet och datastyrning till varje variabel i en rapportsvit.  Obs! Kom ihåg att etikettering måste granskas varje gång en ny rapportsvit skapas eller när en ny variabel aktiveras i en befintlig rapportsvit. Du kan också behöva granska etiketteringen när nya lösningar är aktiverade, eftersom de kan visa nya variabler som kan kräva etiketter. En återimplementering av dina mobilappar eller webbplatser kan ändra hur befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketter. | Följ instruktionerna i [Data i etikettrapportsvit](/help/admin/c-data-governance/gdpr-setup-reportsuite.md). |
| **Steg 5**: Anslut till API:n för Adobe-datasekretess och skicka begäran om åtkomst och borttagning. | Som Adobe Analytics-kund kan du skicka individuella begäranden om datasekretess för att få åtkomst till och radera kunddata genom att anropa [API:n för Adobe Experience Cloud-datasekretess](https://www.adobe.io/apis/experienceplatform/gdpr.html). Du kan skicka alla Analytics-identifierare (som beskrivs i avsnittet [Bästa praxis för etikettering](/help/admin/c-data-governance/gdpr-analytics-ids.md)) i begäranden tillsammans med deras respektive namnområdes-ID (ID för datakälla). |
| **Steg 6**: Visa och hantera inställningarna för datasekretess i din rapportsvit. | Följ instruktionerna i [Visa rapportsvitens inställningar för datastyrning](/help/admin/c-data-governance/gdpr-view-settings.md). |
