---
description: Här beskrivs stegen för hur du aktiverar din Adobe Analytics-implementering för att ge stöd åt de registrerade för åtkomst till och radering av data.
title: Arbetsflöde för sekretess
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: c774d05ca3b1f9f45ec118b0e7b8a839a03b87e3
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 15%

---

# Arbetsflöde för sekretess

Det här arbetsflödet beskriver de steg du måste vidta för att göra din implementering av Adobe Analytics redo att stöda de registrerade personernas åtkomst till och rättigheter till åtkomst och radering avseende datasekretess.

1. Börja med [Översikt över Privacy Servicen](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) i Adobe Experience Platform för att få en uppfattning om vilka frågor som behöver ställas innan ni märker era analysdata.
1. **Ange din datalagringspolicy.** En datalagringspolicy krävs för att Adobe ska kunna hantera förfrågningar om dataåtkomst/radering.  Mer information finns i [Vanliga frågor om datalagring](/help/technotes/data-retention.md). Om du vill använda Privacy Services-API:t måste du se till att datalagringsperioden är angiven i Adobe Analytics.
1. **Bekanta dig med etiketter för datasekretess, Adobe Analytics ID:n, namnutrymmen och ID-expansion.** Se [Dataintegritetsetiketter för analysvariabler](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) och [Bästa praxis för etikettering](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Bekanta dig med DULE/Data Privacy-etiketter, Adobe Analytics ID:n, namnutrymmen och ID-expansion.** Se [Dataintegritetsetiketter för analysvariabler](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) och [Bästa praxis för etikettering](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Tilldela etiketter för identitet, känslighet och datastyrning till varje variabel i en rapportserie.** Märkningen måste granskas varje gång en ny rapportserie skapas eller när en ny variabel aktiveras i en befintlig rapportserie. Granska även etiketten när nya lösningar har integrerats, eftersom de kan visa nya variabler som kan kräva etiketter. En omimplementering av dina mobilappar eller webbplatser kan ändra det sätt på vilket befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketter. Se [Data för Label Report Suite](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).
1. **Anslut till Adobe API för dataskydd och skicka in begäran om åtkomst och borttagning.** Som Adobe Analytics-kund kan du skicka in förfrågningar om personlig datasekretess för att få tillgång till och ta bort kunddata genom att ringa [API för Adobe Experience Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html). Du kan skicka alla Analytics-identifierare (som beskrivs i avsnittet [Bästa praxis för etikettering](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)) i begäranden tillsammans med deras respektive namnområdes-ID (ID för datakälla).
1. **Visa och hantera inställningarna för dataintegritet i din rapportsserie.** Se [Visa inställningar för datastyrning i Report Suite](/help/admin/admin/c-data-governance/data-labeling/gdpr-view-settings.md).
