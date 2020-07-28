---
description: Det här dokumentet beskriver vad du måste göra i Adobe Analytics för att stöda de registrerades åtkomst- och borttagningsrättigheter enligt GDPR.
title: Adobe Analytics och GDPR
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 100%

---


# Adobe Analytics och GDPR

Det här dokumentet beskriver vad du måste göra i Adobe Analytics för att stöda de registrerades åtkomst- och borttagningsrättigheter enligt GDPR.

## Översikt över Adobe {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>Innehållet i detta dokument är inte juridisk rådgivning och är inte avsett att ersätta juridisk rådgivning. Rådfråga företagets juridiska avdelning angående GDPR.

Den 25 maj 2018 trädde Europeiska unionens Dataskyddsförordning (GDPR) i kraft. Mer information om Adobes svar och vad detta innebär för dig som Adobe-kund finns i [GDPR och Ditt företag.](https://www.adobe.com/se/privacy/general-data-protection-regulation.html)

När Adobe tillhandahåller programvara och tjänster till ett företag, agerar Adobe som personuppgiftsbiträde för alla personuppgifter som det tar emot och lagrar för våra kunders räkning, som en del av att tillhandahålla tjänsterna. Som personuppgiftsbiträde behandlar Adobe personuppgifter i enlighet med ditt företags tillstånd och instruktioner (till exempel enligt vad som anges i ditt avtal med Adobe).

Som personuppgiftsansvarig bestämmer du vilka personuppgifter Adobe behandlar och lagrar för din räkning. Om du använder Adobe Experience Cloud-lösningar kan Adobe lagra personuppgifter för dig beroende på vilka lösningar du använder och vilken information du väljer att skicka till ditt Adobe Experience Cloud-konto. Du finner en lista över exempel i [Adobe Experience Cloud-sekretess.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

![](assets/privacy_ready.png)

## Så hanterar Adobe GDPR-data {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform (ACP) är en integrerad lösning som kopplar samman ert varumärkes datastyrningsinfrastruktur med de Adobe-verktyg det använder för att skapa och hantera kundupplevelser. Funktionerna för datastyrning i Adobe Cloud Platform gör det möjligt att koppla policyn för datastyrning direkt till dataanvändningen.

Bekanta dig med [hur Adobe Analytics hanterar GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html), som diskuterar steg för GDPR-beredskap och hur ni kan integrera med GDPR-API:t för Adobe Experience Cloud.

## GDPR-beredskap och DINA Adobe Analytics-data {#section_9A47CDCD614C42238F6E05CFF0180195}

Adobe inser att du är mest bekant med anpassade data i dina rapportsviter och vi ger dig möjlighet att definiera inställningar och preferenser för datastyrning.

Adobe Analytics tillhandahåller före detta ändamål ett användargränssnitt för datastyrning som du i egenskap av personuppgiftsansvariga kan använda för att ange [sekretessetiketter](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) i dina Analytics-rapportsviter och alla dimensioner och metriker i dessa rapportsviter. Du kan identifiera de kolumner i datauppsättningen som innehåller direkt identifierbara data eller indirekt identifierbara data, så att du kan skicka dina begäranden om åtkomst och borttagning för att hantera dessa data. För varje begäran kommer etiketterna som definieras i användargränssnittet för Analytics Data Governance att respekteras för den specifika identifierare som motsvarar den begäran.

Mer information om hur du ställer in etiketterna finns i [Data i etikettrapportsvit](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).

## Förutsättningar {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Bekanta dig med [GDPR-terminologi.](/help/admin/c-data-governance/gdpr-terminology.md)
* Koppla ditt inloggningsföretag till en Experience Cloud-organisation, om det inte redan är det. Kontakta Adobes kundtjänst och se [Organisationer och kontolänkning.](https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/organizations.html)
* Mappa alla Adobe Analytics-rapportsviter som du vill konfigurera för datastyrning till [din Experience Cloud-organisation.](https://docs.adobe.com/content/help/sv-SE/core-services/interface/about-core-services/report-suite-mapping.html)
* Ange en policy för datalagring för varje rapportsvit så att GDPR-begäranden om borttagning och åtkomst kan hanteras.

   >[!NOTE] Adobe Analytics kan inte hjälpa dig med att behandla begäranden till API:t för GDPR, d.v.s. att behandla de begäranden om åtkomst och borttagning som du får från dina slutanvändare, om datalagringsperioden inte har angetts i Adobe Analytics. Kontakta din Customer Success Manager för att ange din datalagringsperiod.

* Kontrollera dina behörigheter: Om du vill använda gränssnittet för datahantering i Adobe Analytics måste du vara Adobe Analytics-administratör.
