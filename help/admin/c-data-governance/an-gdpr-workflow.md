---
description: 'null'
title: Arbetsflöde för sekretess
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: dcb07f8717337da904b252864eb7f800f1728231

---


# Arbetsflöde för sekretess

I det här arbetsflödet beskrivs de steg du måste ta för att göra implementeringen av Adobe Analytics klar att stödja de registrerade personernas åtkomst till och borttagningsrättigheter för dataskydd.

| Uppgiftsbeskrivning | Länkar till instruktioner och mer information |
|--- |--- |
| **Steg 1**: Se till att alla era rapportsviter som kan innehålla data som är relevanta för datasekretess mappas till din Experience Cloud-organisation (eller IMS-organisation).  Begäranden om dataskydd skickas in med en Experience Cloud-organisation och kommer att tillämpas på alla rapporteringsprogram som den organisationen gör anspråk på. Begäranden gäller inte för rapportsviter som inte är mappade till den organisationen, även om de ingår i ditt inloggningsföretag. | Se [Kartrapportsviter för en organisation](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Steg 2**: Ange din datalagringspolicy. | Det måste finnas en datalagringspolicy för att Adobe ska kunna hantera förfrågningar om dataåtkomst/radering.  Mer information finns i Vanliga frågor om lagring av [analysdata](/help/technotes/data-retention.md). |
| **Steg 3**: Bekanta dig med DULE/Data Privacy-etiketter, Adobe Analytics-ID:n, namnutrymmen och ID-expansion. | Läs följande avsnitt i den här dokumentationsuppsättningen:<ul><li>[Dataintegritetsetiketter för analysvariabler](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Bästa praxis för etikettering](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Steg 4**: Tilldela etiketter för identitet, känslighet och datastyrning till varje variabel i en rapportserie.  Obs!  Kom ihåg att etiketter måste granskas varje gång en ny rapportserie skapas eller när en ny variabel aktiveras i en befintlig rapportserie. Du kan också behöva granska etiketten när nya lösningar är aktiverade, eftersom de kan visa nya variabler som kan kräva etiketter. En omimplementering av dina mobilappar eller webbplatser kan ändra det sätt på vilket befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketterna. | Följ instruktionerna i [Label Report Suite-data](/help/admin/c-data-governance/gdpr-setup-reportsuite.md). |
| **Steg 5**: Anslut till Adobe Data Privacy API och skicka begäran om åtkomst och borttagning. | Som Adobe Analytics-kund kan du skicka individuella förfrågningar om dataintegritet för att få tillgång till och ta bort kunddata genom att ringa [Adobe Experience Cloud-API:t](https://www.adobe.io/apis/experienceplatform/gdpr.html)för dataintegritet. Du kan skicka alla analysidentifierare (som beskrivs i avsnittet [Etikettering av bästa praxis](/help/admin/c-data-governance/gdpr-analytics-ids.md)) i förfrågningarna tillsammans med deras respektive namnområdes-ID (ID för datakälla). |
| **Steg 6**: Visa och hantera inställningarna för dataintegritet i din rapportsserie. | Följ instruktionerna i [Visa Report Suites inställningar](/help/admin/c-data-governance/gdpr-view-settings.md)för datastyrning. |
