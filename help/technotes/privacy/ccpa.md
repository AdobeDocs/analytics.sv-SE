---
description: Det här dokumentet beskriver vad du måste göra i Adobe Analytics för att stöda de registrerades åtkomst- och borttagningsrättigheter enligt CCPA.
title: Adobe Analytics och CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 85%

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
Adobe Analytics tillhandahåller före detta ändamål ett användargränssnitt för datastyrning som du i egenskap av personuppgiftsansvariga kan använda för att ange [sekretessetiketter](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) i dina Analytics-rapportsviter och alla dimensioner och metriker i dessa rapportsviter. Du kan identifiera de kolumner i datauppsättningen som innehåller direkt identifierbara data eller indirekt identifierbara data, så att du kan skicka dina begäranden om åtkomst och borttagning för att hantera dessa data. För varje begäran kommer etiketterna som definieras i användargränssnittet för Analytics Data Governance att respekteras för den specifika identifierare som motsvarar den begäran.

Mer information om hur du ställer in etiketterna finns i [Data i etikettrapportsvit](/help/admin/tools/privacy-labeling/labeling-overview.md).
