---
title: Spårningskod
description: Namnet på spårningskoden eller kampanjen.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 1%

---

# Spårningskod

Spårningskod [dimension](overview.md) visar namnen på spårningskoderna på din plats. Du kan placera länkar med olika parametervärden för frågesträngar på olika platser på Internet. Denna dimension hjälper er att förstå vilka länkar som var mest framgångsrika när det gäller att köra trafik till er webbplats.

Det är vanligt att lägga till spårningskodfrågesträngar i e-postmeddelanden, annonser, inlägg i sociala medier och andra marknadsföringsaktiviteter som används i organisationen.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`v0`-frågesträngen ](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet samlar in dessa data med variabeln [`campaign`](/help/implement/vars/page-vars/campaign.md).

## Dimensioner

Bland Dimensionerna finns namnen på spårningskoderna på webbplatsen. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Mer information finns i [Kampanjspårning](/help/implement/use-cases/campaign-tracking.md).

## Jämför spårningskoddimensionen med marknadsföringskanaler som samlar in spårningskoder

Vissa användare som konfigurerar regler för bearbetning av marknadsföringskanaler konfigurerar en regel som tar alla värden som används i spårningskoddimensionen. Även om de är en utmärkt metod är de olika på grund av de inbyggda bearbetnings- och arkitekturskillnaderna. I följande lista förklaras varför dessa två metoder, även om de liknar varandra i korthet, kan ändra attribueringsbeteendet.

### Tidigare kanaler i bearbetningsregler

Bearbetningsregler för marknadsföringskanaler som ligger högre upp i listan kan förhindra träffar från att tillskrivas marknadsföringskanalen i era spårningskoder. Exempel:

1. Du har &#39;Sociala nätverk&#39; konfigurerat som din första regel och &#39;Spårningskoder&#39; som din andra.
2. En användare publicerar en länk till din webbplats som innehåller en spårningskod på en webbplats för sociala medier, och flera av deras vänner klickar på länken till din webbplats.

Eftersom&quot;sociala nätverk&quot; är den första regeln för bearbetning av marknadsföringskanaler tilldelar dessa användare marknadsföringskanalen&quot;sociala nätverk&quot;, och inte marknadsföringskanalen för spårningskoder.

### Andra marknadsföringskanaler kan ta attribuering genom sista handen

När du arbetar med en standarddimension för spårningskoder behöver du inte bekymra dig om att andra delar av din webbplats stjäl attribuering. Men med marknadsföringskanaler kan en användare matcha en annan regel och ge olika attribuering. Exempel:

1. Du har &#39;Spårningskoder&#39; som din första kanal och &#39;Direkt&#39; som din andra.
2. En användare kommer till webbplatsen via en spårningskod, men lämnar den sedan.
3. Nästa dag skriver de in din URL i adressfältet och gör sedan ett köp.

I det här exemplet skulle marknadsföringskanalen för spårningskoder inte få sista touch-kredit för det köpet. Istället skulle det gå till marknadsföringskanalen&quot;Direct&quot;.


### Utgångsskillnader

Marknadsföringskanalerna har en rullande 30-dagars förfallotid för besökarengagemang, oavsett om en kanal berördes eller inte. Spårningskoder har en förfallotid baserat på när variabeln angavs. Exempel:

1. Du har 30 dagars förfallotid för besökarengagemang och har även konfigurerat spårningskoddimensionen så att den upphör att gälla efter 30 dagar.
2. En användare kommer till din webbplats via en spårningskod. De surfar på webbplatsen och går sedan iväg.
3. Tre veckor senare kommer de tillbaka utan en spårningskod eller marknadsföringskanal och lämnar dem sedan igen.
4. Två veckor senare (fem veckor efter deras första besök) kommer de tillbaka utan spårningskod eller marknadsföringskanal och gör sedan ett köp.

Användaren har slutligen gjort ett köp som är längre än 30 dagar, men aldrig varit inaktiv i mer än 30 dagar. I det här fallet skulle ni se intäkter som tillskrivs marknadsföringskanalen för spårningskoder, men inte själva dimensionen för spårningskod.



