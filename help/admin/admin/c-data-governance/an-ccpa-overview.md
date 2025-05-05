---
description: Det här dokumentet beskriver vad du måste göra i Adobe Analytics för att stöda de registrerades åtkomst- och borttagningsrättigheter enligt CCPA.
title: Adobe Analytics och CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 86%

---

# Adobe Analytics och CCPA

Det här dokumentet beskriver vad du måste göra i Adobe Analytics för att stöda de registrerades åtkomst- och borttagningsrättigheter enligt CCPA.

## Översikt över Adobe

>[!IMPORTANT]
>
>Innehållet i detta dokument är inte juridisk rådgivning och är inte avsett att ersätta juridisk rådgivning. Rådfråga företagets juridiska avdelning angående CCPA.

Den 1 januari 2020 träder California Consumer Privacy Act (CCPA) i kraft. Mer information om Adobes svar och vad detta innebär för dig som Adobe-kund finns i [Adobes Sekretesscenter.](https://www.adobe.com/se/privacy.html)

När Adobe tillhandahåller programvara och tjänster till ett företag, agerar Adobe som personuppgiftsbiträde för alla personuppgifter som det tar emot och lagrar för våra kunders räkning, som en del av att tillhandahålla tjänsterna. Som personuppgiftsbiträde behandlar Adobe personuppgifter i enlighet med ditt företags tillstånd och instruktioner (till exempel enligt vad som anges i ditt avtal med Adobe).

Som personuppgiftsansvarig bestämmer du vilka personuppgifter Adobe behandlar och lagrar för din räkning. Om du använder Adobe Experience Cloud-lösningar kan Adobe lagra personuppgifter för dig beroende på vilka lösningar du använder och vilken information du väljer att skicka till ditt Adobe Experience Cloud-konto. Du finner en lista över exempel i [Adobe Experience Cloud-sekretess.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## Så hanterar Adobe CCPA-data

Adobe Experience Cloud erbjuder en integrerad lösning som kopplar samman ert varumärkes infrastruktur för datastyrning med de Adobe-verktyg som används för att skapa och hantera kundupplevelser. Adobe Experience Cloud datastyrningsfunktioner möjliggör en direkt koppling mellan datastyrningspolicyn och dataanvändningen.

Bekanta dig med [hur Adobe Analytics hanterar GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html), som diskuterar steg för sekretessberedskap och hur ni kan integrera med sekretesstjänste-API:t för Adobe Experience Cloud.

## CCPA-beredskap och dina Adobe Analytics-data

Adobe inser att du är mest bekant med anpassade data i dina rapportsviter och vi ger dig möjlighet att definiera inställningar och preferenser för datastyrning.
Adobe Analytics tillhandahåller före detta ändamål ett användargränssnitt för datastyrning som du i egenskap av personuppgiftsansvariga kan använda för att ange [sekretessetiketter](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels) i dina Analytics-rapportsviter och alla dimensioner och metriker i dessa rapportsviter. Du kan identifiera de kolumner i datauppsättningen som innehåller direkt identifierbara data eller indirekt identifierbara data, så att du kan skicka dina begäranden om åtkomst och borttagning för att hantera dessa data. För varje begäran kommer etiketterna som definieras i användargränssnittet för Analytics Data Governance att respekteras för den specifika identifierare som motsvarar den begäran.

Mer information om hur du ställer in etiketterna finns i [Data i etikettrapportsvit](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md).

## Förutsättningar

* Bekanta dig med [GDPR-terminologi.](/help/admin/c-data-governance/gdpr-terminology.md)
* Koppla ditt inloggningsföretag till en Experience Cloud-organisation, om det inte redan är det. Kontakta Adobes kundtjänst och se [Organisationer och kontolänkning.](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=sv-SE)
* Ange en policy för datalagring för varje rapportsvit så att CCPA-begäranden om borttagning och åtkomst kan hanteras.

  Adobe Analytics kan inte hjälpa dig med att behandla begäranden till API:t för sekretesstjänster, d.v.s. att behandla de begäranden om åtkomst och borttagning som du får från dina slutanvändare, om datalagringsperioden inte har angetts i Adobe Analytics. Kontakta kontoteamet på Adobe för att ange din datalagringsperiod.

* Kontrollera dina behörigheter: Om du vill använda gränssnittet för datahantering i Adobe Analytics måste du vara Adobe Analytics-administratör.
* Överväg att implementera [variabeln för hantering av samtycke](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) för att spåra godkännandestatus på en träffnivå.
