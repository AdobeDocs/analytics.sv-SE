---
description: Här beskrivs stegen för hur du aktiverar din Adobe Analytics-implementering för att ge stöd åt de registrerade för åtkomst till och radering av data.
title: Arbetsflöde för sekretess
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 31%

---

# Arbetsflöde för sekretess

Det här arbetsflödet beskriver de steg du måste vidta för att göra din implementering av Adobe Analytics redo att stöda de registrerade personernas åtkomst till och rättigheter till åtkomst och radering avseende datasekretess.

1. **Ange din datalagringspolicy.** En datalagringspolicy krävs för att Adobe ska kunna hantera förfrågningar om dataåtkomst/radering.  Mer information finns i [Vanliga frågor om datalagring](/help/technotes/data-retention.md).
1. **Bekanta dig med DULE/Data Privacy-etiketter, Adobe Analytics ID:n, namnutrymmen och ID-expansion.** Se [Dataintegritetsetiketter för analysvariabler](/help/admin/c-data-governance/gdpr-labels.md) och [Bästa praxis för etikettering](/help/admin/c-data-governance/gdpr-analytics-ids.md).
1. **Tilldela etiketter för identitet, känslighet och datastyrning till varje variabel i en rapportserie.** Märkningen måste granskas varje gång en ny rapportserie skapas eller när en ny variabel aktiveras i en befintlig rapportserie. Granska även etiketten när nya lösningar har integrerats, eftersom de kan visa nya variabler som kan kräva etiketter. En omimplementering av dina mobilappar eller webbplatser kan ändra det sätt på vilket befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketter. Se [Data för Label Report Suite](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
1. **Anslut till Adobe API för dataskydd och skicka in begäran om åtkomst och borttagning.** Som Adobe Analytics-kund kan du skicka individuella begäranden om datasekretess för att få åtkomst till och radera kunddata genom att anropa [API:n för Adobe Experience Cloud-datasekretess](https://www.adobe.io/apis/experienceplatform/gdpr.html). Du kan skicka alla Analytics-identifierare (som beskrivs i avsnittet [Bästa praxis för etikettering](/help/admin/c-data-governance/gdpr-analytics-ids.md)) i begäranden tillsammans med deras respektive namnområdes-ID (ID för datakälla).
1. **Visa och hantera inställningarna för dataintegritet i din rapportsserie.** Se [Visa inställningar för datastyrning i Report Suite](/help/admin/c-data-governance/gdpr-view-settings.md).
