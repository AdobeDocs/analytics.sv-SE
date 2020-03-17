---
description: I det här dokumentet beskrivs vad du behöver göra i Adobe Analytics för att ge stöd åt de registrerade för CCPA-åtkomst och borttagningsrättigheter.
title: Adobe Analytics och CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Adobe Analytics och CCPA

I det här dokumentet beskrivs vad du behöver göra i Adobe Analytics för att ge stöd åt de registrerade för CCPA-åtkomst och borttagningsrättigheter.

## Adobe - översikt

>[!IMPORTANT] Innehållet i detta dokument är inte juridisk rådgivning och är inte avsett att ersätta juridisk rådgivning. Rådfråga företagets juridiska avdelning om råd angående CCPA.

Den 1 januari 2020 träder California Consumer Privacy Act (CCPA) i kraft. Mer information om Adobes svar och vad detta innebär för dig som Adobe-kund finns i [Adobes Sekretesscenter.](https://www.adobe.com/privacy.html)

När Adobe tillhandahåller programvara och tjänster till ett företag agerar Adobe som personuppgiftsbiträde för alla personuppgifter som det tar emot och lagrar för våra kunders räkning, som en del av att tillhandahålla tjänsterna. Som personuppgiftsbiträde behandlar Adobe personuppgifter i enlighet med ditt företags tillstånd och instruktioner (till exempel enligt vad som anges i ditt avtal med Adobe).

Som personuppgiftsansvarig bestämmer du vilka personuppgifter Adobe behandlar och lagrar å dina vägnar. Om ni använder Adobe Experience Cloud-lösningar kan Adobe lagra personuppgifter för er beroende på vilka lösningar ni använder och vilken information ni väljer att skicka till ert Adobe Experience Cloud-konto. En lista över exempel finns i [Adobe Experience Cloud-sekretess.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## Hur Adobe hanterar CCPA-data

Adobe Cloud Platform (ACP) är en integrerad lösning som kopplar samman ert varumärkes datastyrningsinfrastruktur med de Adobe-verktyg det använder för att skapa och hantera kundupplevelser. Funktionerna för datastyrning i Adobe Cloud-plattformen gör det möjligt att länka datastyrningspolicyn direkt till dataanvändningen.

Bekanta dig med [hur Adobe Analytics hanterar GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) , som diskuterar steg för sekretessberedskap och hur ni kan integrera med API:t för Adobe Experience Cloud Privacy Service.

## CCPA-beredskap och era Adobe Analytics-data

Adobe inser att ni är mest bekanta med anpassade data i era rapportsviter och vi ger er möjlighet att definiera inställningar och inställningar för datastyrning.
I detta syfte har Adobe Analytics ett användargränssnitt för datastyrning som gör att ni som personuppgiftsansvariga kan ange [integritetsetiketter](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) i era analysrapportsviter och alla mått och mått i dessa rapportsviter. Du kan identifiera de kolumner i datauppsättningen som innehåller direkt identifierbara data eller indirekt identifierbara data, så att du kan skicka din åtkomst och ta bort förfrågningar för att hantera dessa data. För varje begäran kommer etiketterna som definieras i användargränssnittet för Analytics Data Governance att respekteras för den specifika identifierare som motsvarar den begäran.

Mer information om hur du ställer in etiketterna finns i [Label Report Suite-data](/help//admin/c-data-governance/gdpr-setup-reportsuite.md) .

## Förutsättningar

* Bekanta dig med [GDPR-terminologi.](/help/admin/c-data-governance/gdpr-terminology.md)
* Länka ditt inloggningsföretag till en Experience Cloud-organisation, om det inte redan är det. Kontakta Adobes kundtjänst och se [Organisationer och kontolänkning.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Mappa alla Adobe Analytics-rapportsviter som ni vill konfigurera för datastyrning till [er Experience Cloud-organisation.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* Ange en datalagringspolicy för varje rapportsserie så att CCPA-begäranden om borttagning och åtkomst kan hanteras.

   Adobe Analytics kan inte hjälpa er med att bearbeta förfrågningar till API:t för integritetstjänster, dvs. att behandla de förfrågningar om åtkomst och borttagning som ni får från era slutanvändare, om datalagringsperioden inte har angetts i Adobe Analytics. Kontakta din Customer Success Manager för att ange din datalagringsperiod.

* Kontrollera dina behörigheter: Om du vill använda gränssnittet för datahantering i Adobe Analytics måste du vara Adobe Analytics-administratör.
* Överväg att implementera [variabeln](/help/admin/c-data-governance/consent-variables.md) för hantering av samtycke för att spåra godkännandestatus på en träffnivå.
