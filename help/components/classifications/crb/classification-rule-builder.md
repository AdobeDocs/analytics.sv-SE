---
description: I stället för att underhålla och överföra klassificeringar varje gång spårningskoderna ändras kan du skapa automatiska, regelbaserade klassificeringar och använda dem i flera rapportsviter. Regler behandlas med jämna mellanrum, beroende på hur mycket av klassificeringen som den relaterade trafiken är.
title: Arbetsflöde för klassificeringsregelbyggaren
feature: Classifications
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Översikt över klassificeringsregelbyggaren (äldre)

I stället för att underhålla och överföra klassificeringar varje gång spårningskoderna ändras kan du skapa automatiska, regelbaserade klassificeringar och använda dem i flera rapportsviter. Regler behandlas med jämna mellanrum, beroende på hur mycket av klassificeringen som den relaterade trafiken är.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Klassificeringsregelbyggaren](https://video.tv.adobe.com/v/25884?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

## Viktigt meddelande innan du börjar

Tänk på följande när du använder klassificeringsregler:

* Du kan exportera upp till 10 miljoner rader åt gången.
* När CRB begär en export hämtas både klassificerade och oklassificerade värden, där oklassificerade värden når fram i slutet av exporten. Det innebär att ni med tiden kan fylla upp till 10 miljoner klassificerade värden - utan att någonsin gå till de oklassificerade värdena.
* Eftersom arkitekturen har konfigurerats på ett sätt som gör att CRB kan hämta från n-antalet servrar kan detta leda till inkonsekvenser vad gäller vilka servrar som plockas upp och i vilken ordning. Därför är det mycket svårt att komma åt oklassificerade värden.

Detta är **tillfällig** för dem som har fler än 10 miljoner klassificerade värden för en dimension: Du måste exportera oklassificerade värden via FTP, i 10 miljoner grupper och manuellt klassificera dem.

## Komma igång med klassificeringsregler {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Nedan följer några steg för att implementera klassificeringsregler:

| Steg | Där utförd | Beskrivning |
|--- |--- |--- |
| Steg 1 (Krav): Konfigurera klassificeringsschemat. | [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > [!UICONTROL Traffic Classifications] eller [!UICONTROL Conversion Classifications] | Välj en variabel och definiera de klassificeringar som ska användas för variabeln. <br>Variabler måste ha minst en klassificeringskolumn som skapats innan de kan användas i regler.<br>När klassificeringar har aktiverats kan du använda importverktyget och regelbyggaren för att klassificera specifika värden. |
| Steg 2: [Skapa en regeluppsättning](classification-rule-set.md). | [!UICONTROL Admin] > [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set] | En regeluppsättning är en grupp klassificeringsregler för en specifik variabel. |
| Steg 3: Konfigurera rapportsviter och variabler. | [!UICONTROL Classification Rule Builder] > &lt;din regeluppsättning> | Använd regeluppsättningen för rapportsviter och variabler. |
| Steg 4: [Lägg till klassificeringsregler i uppsättningen](classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] > &lt;din regeluppsättning> | Matcha ett villkor med en klassificering och ange sedan vilken åtgärd som ska vidtas för regeln.  Lär dig mer om informationen i [Hur regler bearbetas](classification-quickstart-rules.md). |
| Steg 5: [Testa en klassificeringsregeluppsättning](classification-quickstart-rules.md) | [!DNL Testing Page] | Du vill testa reglerna för validering genom att redigera dem i utkastläge. I utkastläge kan reglerna inte köras.<br>Det här steget är viktigt när du använder [reguljära uttryck](classification-quickstart-rules.md). |
| Steg 6: [Aktivera giltiga regler](classification-rule-definitions.md). | [!DNL Rules Page] | När reglerna är giltiga aktiverar du regeluppsättningen.  Du kan skriva över befintliga nycklar om det behövs. Se [Hur regler bearbetas](classification-quickstart-rules.md). |
| Steg 7 (valfritt): [Ta bort oönskade regler](classification-rule-definitions.md). | [!DNL Rules Page] | Ta bort oönskade regler från en uppsättning.<br>Obs! Om du tar bort regler tas inte klassificerade data som överförts bort. Se [Ta bort klassificeringsdata](/help/components/classifications/importer/t-delete-classification-data.md) om du behöver ta bort klassificerade data. |

>[!NOTE]
>
>Grupper med behörighet att använda klassificeringsverktyget kan använda klassificeringsregler. Se [Hur regler bearbetas](classification-quickstart-rules.md) för viktig bearbetningsinformation.

**Ytterligare resurser**

**Blogg**: Mer information om den här funktionen finns i bloggen om digital marknadsföring: [Regelbaserade klassificeringar](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Video**: Visa videon [Klassificeringsöversikt](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/classifications/overview-of-classifications.html?lang=sv-SE).
