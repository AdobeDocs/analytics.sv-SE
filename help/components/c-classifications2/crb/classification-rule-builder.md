---
description: I stället för att underhålla och överföra klassificeringar varje gång spårningskoderna ändras kan du skapa automatiska, regelbaserade klassificeringar och använda dem i flera rapportsviter. Regler behandlas med jämna mellanrum, beroende på hur mycket av klassificeringen som den relaterade trafiken är.
subtopic: Classifications
title: Arbetsflöde för klassificeringsregelbyggaren
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: f6b528f8a1b89a008a736fa62d58d6e83f13e4e4

---


# Arbetsflöde för klassificeringsregelbyggaren

I stället för att underhålla och överföra klassificeringar varje gång spårningskoderna ändras kan du skapa automatiska, regelbaserade klassificeringar och använda dem i flera rapportsviter. Regler behandlas med jämna mellanrum, beroende på hur mycket av klassificeringen som den relaterade trafiken är.

## Viktigt meddelande innan du börjar

Tänk på detta innan du börjar använda klassificeringsregler:

* Underklassificeringar stöds inte med CRB (Klassificeringsregelbyggaren).
* Vårt nuvarande klassificeringssystem kan bara exportera upp till 10 miljoner rader åt gången.
* När CRB begär en export hämtas både klassificerade och oklassificerade värden, där oklassificerade värden når fram i slutet av exporten. Det innebär att ni med tiden kan fylla upp till 10 miljoner klassificerade värden - utan att någonsin gå till de oklassificerade värdena.
* Eftersom arkitekturen har konfigurerats på ett sätt som gör att CRB kan hämta från n-antalet servrar kan detta leda till inkonsekvenser vad gäller vilka servrar som plockas upp och i vilken ordning. Därför är det mycket svårt att komma åt oklassificerade värden.

Detta är en **tillfällig lösning** för dem som har fler än 10 miljoner klassificerade värden för en dimension: Du måste exportera oklassificerade värden via FTP, i 10 miljoner batchar och manuellt klassificera dem.

## Komma igång med klassificeringsregler {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Nedan följer några steg för att implementera klassificeringsregler:

| Steg | Där utförd | Beskrivning |
|--- |--- |--- |
| Steg 1 (Förutsättning): [Konfigurera klassificeringsschemat](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > &lt;Trafikklassificeringar eller Konverteringsklassificeringar> | Välj en variabel och definiera de klassificeringar som ska användas för variabeln. <br>Variabler måste ha minst en klassificeringskolumn som skapats innan de kan användas i regler.<br>När klassificeringarna är aktiverade kan du använda importverktyget och regelbyggaren för att klassificera specifika värden. |
| Steg 2: [Skapa en regeluppsättning](/help/components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Admin] >  [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set] | En regeluppsättning är en grupp klassificeringsregler för en specifik variabel. |
| Steg 3: Konfigurera rapportsviter och variabler. | [!UICONTROL Classification Rule Builder] > &lt;din regeluppsättning> | Använd regeluppsättningen för rapportsviter och variabler. |
| Steg 4: Lägg [till klassificeringsregler i uppsättningen](/help/components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] > &lt;din regeluppsättning> | Matcha ett villkor med en klassificering och ange sedan vilken åtgärd som ska vidtas för regeln.  Läs mer om [hur reglerna behandlas](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Steg 5: [Testa en klassificeringsregeluppsättning](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Du vill testa reglerna för validering genom att redigera dem i utkastläge. I utkastläge kan reglerna inte köras.<br>Det här steget är viktigt när du använder [reguljära uttryck](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Steg 6: Aktivera [giltiga regler](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | När reglerna är giltiga aktiverar du regeluppsättningen.  Du kan skriva över befintliga nycklar om det behövs. Se [hur reglerna behandlas](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Steg 7 (valfritt): Ta [bort oönskade regler](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Ta bort oönskade regler från en uppsättning.<br>Obs!  Klassificerade data som överförts tas inte bort när du tar bort regler.  Se [Ta bort klassificeringsdata](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) om du behöver ta bort klassificerade data. |

>[!NOTE]
>
>Grupper med behörighet att använda klassificeringsverktyget kan använda klassificeringsregler. Se [hur regler behandlas](/help/components/c-classifications2/crb/classification-quickstart-rules.md) för viktig bearbetningsinformation.

**Ytterligare resurser**

**Blogg**: Mer information om den här funktionen finns i bloggen om digital marknadsföring: Regelbaserade [klassificeringar](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Video**: Besök [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) för att se [!UICONTROL Classifications Overview] videon.
