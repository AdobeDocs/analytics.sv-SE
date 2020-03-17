---
description: Import- och exportfilen innehåller sex kolumner för varje numerisk tvåklassificering.
subtopic: Classifications
title: Importera numeriska 2 klassificeringar
topic: Admin tools
uuid: 82a3034c-e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importera numeriska 2 klassificeringar

>[!IMPORTANT]
>
>Möjligheten att importera Numeric 2- och Date-Enabled-klassificeringar har tagits bort från kodbasen. Denna ändring träder i kraft i underhållsutgåvan från juli 2019. Om du har numeriska eller datumaktiverade kolumner i importfilen, ignoreras dessa celler och alla andra data i filen importeras som vanligt. Befintliga klassificeringar kan fortfarande exporteras via standardarbetsflödet för klassificering och kommer att vara tillgängliga i rapporter.

Import- och exportfilen innehåller sex kolumner för varje numerisk tvåklassificering.

I följande definitioner antas att det numeriska 2-klassificeringsnamnet är MyCost.

**~MinKostnad:** Ett beskrivande namn för raden.

**~MyCost^~id~:** ID för redigering av en befintlig rad. När du lägger till en ny rad bör den vara tom. Ett ID tilldelas automatiskt när du exporterar från Klassificeringshanteraren.

**~MyCost^~value~:** Värdet för raden. Om kurskolumnen är fast är detta ett schablonvärde som fördelas över hela perioden. Om hastighetskolumnen är en händelse är detta multiplikatorn för den händelsen. Den här posten får inte innehålla kommatecken.

**~MinKostnad^~period~:** Den tidsperiod som den här raden motsvarar. Detta måste innehålla ett start- och slutdatum, avgränsat med ett streck. Strecket måste omges av blanksteg. Definitionen ska formateras på följande sätt:

ÅÅÅÅ/MM/DD - ÅÅÅÅ/MM/DD

**~MyCost^~rate~:** Den händelse som ska multipliceras med [!UICONTROL Value] kolumnen. Giltiga värden är:

* fast - används för att ange att värdet är ett platt värde som ska fördelas över perioden.
* omsättning
* order
* enhet
* scopen
* granskningar
* instance
* klicka
* utcheckning
* scadd
* rastrera
* händelse 1
* händelse 2
* etc

**~MyCost^~hinge~:** Den händelse som ska användas för att fördela värdet under en uppdelning. Det här värdet är ofta detsamma som [!UICONTROL ~MyCost^~frekvensen~], såvida du inte använder [!UICONTROL fixed]. Giltiga värden för den här kolumnen är identiska med [!UICONTROL ~MyCost^~tariffen~], med tillägget [!UICONTROL none].
