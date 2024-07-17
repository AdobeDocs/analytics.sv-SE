---
description: Här beskrivs stegen för hur du aktiverar din Adobe Analytics-implementering för att ge stöd åt de registrerade för åtkomst till och radering av data.
title: Arbetsflöde för sekretess
feature: Privacy
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 16%

---

# Arbetsflöde för sekretess

Det här arbetsflödet beskriver de steg du måste vidta för att göra din implementering av Adobe Analytics redo att stöda de registrerade personernas åtkomst till och rättigheter till åtkomst och radering avseende datasekretess.

1. Börja med sidan [Översikt över Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) i Adobe Experience Platform för att få en uppfattning om vilka frågor som ska ställas innan du märker dina Analytics-data.
1. **Ange din datalagringspolicy.** En datalagringspolicy krävs för att Adobe ska kunna hantera dataåtkomstbegäranden/borttagningsbegäranden.  Mer information finns i [Vanliga frågor om datalagring](/help/technotes/data-retention.md). Om du vill använda Privacy Services-API:t måste du se till att datalagringsperioden är angiven i Adobe Analytics.
1. **Bekanta dig med dataintegritetsetiketter, Adobe Analytics-ID:n, namnutrymmen och ID-expansion.** Se [Etiketter för datasekretess för analysvariabler](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) och [Bästa praxis för etiketter](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Bekanta dig med DULE/Data Privacy-etiketter, Adobe Analytics-ID:n, namnutrymmen och ID-expansion.** Se [Etiketter för datasekretess för analysvariabler](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) och [Bästa praxis för etiketter](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Tilldela etiketter för identitet, känslighet och datastyrning till varje variabel i en rapportserie.**-etiketter måste granskas varje gång en ny rapportserie skapas eller när en ny variabel aktiveras i en befintlig rapportserie. Granska även etiketten när nya lösningar har integrerats, eftersom de kan visa nya variabler som kan kräva etiketter. En omimplementering av dina mobilappar eller webbplatser kan ändra det sätt på vilket befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketter. Se [Etikettrapportsvitens data](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).
1. **Anslut till API:t för dataskydd i Adobe och skicka in begäranden om åtkomst och borttagning.** Som Adobe Analytics-kund kan du skicka enskilda datasekretessförfrågningar för att få tillgång till och ta bort kunddata genom att ringa [Adobe Experience Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html). Du kan skicka alla Analytics-identifierare (som beskrivs i avsnittet [Bästa praxis för etikettering](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)) i begäranden tillsammans med deras respektive namnområdes-ID (ID för datakälla).
1. **Visa och hantera inställningarna för dataintegritet i rapportsviten.** Se [Visa datastyrningsinställningar för Report Suite](/help/admin/admin/c-data-governance/data-labeling/gdpr-view-settings.md).
