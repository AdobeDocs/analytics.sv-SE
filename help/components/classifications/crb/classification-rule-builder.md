---
description: I stället för att underhålla och överföra klassificeringar varje gång spårningskoderna ändras kan du skapa automatiska, regelbaserade klassificeringar och använda dem i flera rapportsviter. Regler behandlas med jämna mellanrum, beroende på hur mycket av klassificeringen som den relaterade trafiken är.
subtopic: Classifications
title: Arbetsflöde för Classification Rule Builder
feature: Administratörsverktyg
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 2%

---

# Arbetsflöde för Classification Rule Builder

I stället för att underhålla och överföra klassificeringar varje gång spårningskoderna ändras kan du skapa automatiska, regelbaserade klassificeringar och använda dem i flera rapportsviter. Regler behandlas med jämna mellanrum, beroende på hur mycket av klassificeringen som den relaterade trafiken är.

## Viktigt meddelande innan du börjar

Tänk på detta innan du börjar använda klassificeringsregler:

* Underklassificeringar stöds inte med CRB (Klassificeringsregelbyggaren).
* Vårt nuvarande klassificeringssystem kan bara exportera upp till 10 miljoner rader åt gången.
* När CRB begär en export hämtas både klassificerade och oklassificerade värden, där oklassificerade värden når fram i slutet av exporten. Det innebär att ni med tiden kan fylla upp till 10 miljoner klassificerade värden - utan att någonsin gå till de oklassificerade värdena.
* Eftersom arkitekturen har konfigurerats på ett sätt som gör att CRB kan hämta från n-antalet servrar kan detta leda till inkonsekvenser vad gäller vilka servrar som plockas upp och i vilken ordning. Därför är det mycket svårt att komma åt oklassificerade värden.

Detta är **lösningen** för dem som har fler än 10 miljoner klassificerade värden för en dimension: Du måste exportera oklassificerade värden via FTP, i 10 miljoner batchar och manuellt klassificera dem.

## Komma igång med klassificeringsregler {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Nedan följer några steg för att implementera klassificeringsregler:

| Steg | Där utförd | Beskrivning |
|--- |--- |--- |
| Steg 1 (Förutsättning): [Konfigurera ditt klassificeringsschema](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html). | [!UICONTROL Admin] >  [!UICONTROL Report Suites] >  [!UICONTROL Edit Settings] >  &lt;traffic Classifications=&quot;&quot; or=&quot;&quot; Conversion=&quot;&quot; Classifications=&quot;&quot;> | Välj en variabel och definiera de klassificeringar som ska användas för variabeln. <br>Variabler måste ha minst en klassificeringskolumn som skapats innan de kan användas i regler.<br>När klassificeringarna är aktiverade kan du använda importverktyget och regelbyggaren för att klassificera specifika värden. |
| Steg 2: [Skapa en regeluppsättning](/help/components/classifications/crb/classification-rule-set.md). | [!UICONTROL Admin] >  [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set] | En regeluppsättning är en grupp klassificeringsregler för en specifik variabel. |
| Steg 3: Konfigurera rapportsviter och variabler. | [!UICONTROL Classification Rule Builder] >   &lt;your rule=&quot;&quot; set=&quot;&quot;> | Använd regeluppsättningen för rapportsviter och variabler. |
| Steg 4: [Lägg till klassificeringsregler i uppsättningen](/help/components/classifications/crb/classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] >   &lt;your rule=&quot;&quot; set=&quot;&quot;> | Matcha ett villkor med en klassificering och ange sedan vilken åtgärd som ska vidtas för regeln.  Läs mer i [Hur regler bearbetas](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Steg 5: [Testa en klassificeringsregeluppsättning](/help/components/classifications/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Du vill testa reglerna för validering genom att redigera dem i utkastläge. I utkastläge kan reglerna inte köras.<br>Det här steget är viktigt när du använder  [reguljära uttryck](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Steg 6: [Aktivera giltiga regler](/help/components/classifications/crb/classification-rule-definitions.md). | [!DNL Rules Page] | När reglerna är giltiga aktiverar du regeluppsättningen.  Du kan skriva över befintliga nycklar om det behövs. Se [Hur regler behandlas](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Steg 7 (valfritt): [Ta bort oönskade regler](/help/components/classifications/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Ta bort oönskade regler från en uppsättning.<br>Obs! Klassificerade data som överförts tas inte bort när du tar bort regler.  Se [Ta bort klassificeringsdata](/help/components/classifications/importer/t-delete-classification-data.md) om du behöver ta bort klassificerade data. |

>[!NOTE]
>
>Grupper med behörighet att använda klassificeringsverktyget kan använda klassificeringsregler. Se [Hur regler bearbetas](/help/components/classifications/crb/classification-quickstart-rules.md) för viktig bearbetningsinformation.

**Ytterligare material**

**Blogg**: Mer information om den här funktionen finns i bloggen om digital marknadsföring:  [Regelbaserade klassificeringar](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Video**: Visa videon  [Klassificeringsöversikt ](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/components/classifications/overview-of-classifications.html) .
