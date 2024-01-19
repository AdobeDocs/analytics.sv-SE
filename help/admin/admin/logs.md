---
description: Logga filer som hjälper dig att se när användare loggar in, deras användning, åtkomst, rapportsviter och administratörsändringar.
title: Loggar
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 2%

---

# Loggar

Logga filer som hjälper dig att se när användare loggar in, deras användning, åtkomst, rapportsviter och administratörsändringar.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Logs]**

## Administratörslogg {#section_8ADE8A7204A8401C968ABC20AECA381D}

Administratörsloggen rapporterar alla ändringar som gjorts av administratörer i administrationsverktygen. Loggen tillhandahåller en gateway till användardefinierade rapporter från någon av de tre loggarna. Du kan söka efter händelser som matchar de valda villkoren i ett visst datumintervall.

## Logg för användning och åtkomst {#section_6FBAF92D9EA244809C45A78A2F0A7232}

The [!UICONTROL Usage and Access Log] Med kan du utvärdera rapportanvändning på användarkontonivå. Den spårar till exempel åtgärder som är öppna, skapa, uppdatera, dela upp och ta bort i Analysis Workspace. Detta ger bättre synlighet för vem som använder Workspace och hur ofta.

| Element | Beskrivning |
|---|---|
| Datumintervall | Ange ett datumintervallfilter. Du kan ange ett datum manuellt i formatet ÅÅÅÅ-MM-DD eller klicka på kalenderikonen för att välja ett datum. |
| Inloggning | Filtrera loggen efter användarnamn. |
| IP | Filtrera loggen med en IP-adress. |
| Report Suite | Filtrera loggen med ett specifikt rapportpaket-ID. |
| Händelsetyp | Filtrera loggen efter en händelsetyp. Välj en händelsetyp i listrutan. Se den fullständiga listan över händelsetyper nedan. |
| Händelse | Filtrera loggen med ett ord eller en fras i händelsebeskrivningen. |
| Ladda ned rapport | Exporterar innehållet i [!UICONTROL Usage & Access Log] till en tabbavgränsad fil. |

### Händelsetyper

| Händelsetyp | Beskrivning |
| --- | --- |
| Ingen kategori | Det kan vara vilken händelsetyp som helst. |
| Inloggningen misslyckades | Användarinloggningsprocessen misslyckades. |
| Inloggningen har slutförts | Användaren har loggat in. |
| Administratörsåtgärd | En administratörsåtgärd inträffade, som att redigera en rapportserie, ändra företagsinställningar, skapa en användare, avbryta en rapportbegäran osv. |
| Ändring av säkerhetsinställning | En säkerhetsinställning har ändrats. |
| Aviseringen har skickats | En varning skickades. |
| Användaråtgärd | Användarinformationen har redigerats. |
| Verktyget visas | Ett verktyg visades. |
| Omniture Action | En åtgärd utfördes av Adobe. |
| Lösenordsåterställning | Ett lösenord har återställts. |
| Bokmärken | Ett bokmärke hanterades. |
| Kontrollpaneler | En instrumentpanel hanterades. |
| Larm | En avisering hanterades. |
| Kalenderhändelser | En kalenderhändelse hanterades. |
| Målgrupper | Ett mål hanterades. |
| Rapportinställningar | En rapportinställning hanterades. |
| Schemalagda rapporter | En schemalagd rapport hanterades. |
| Exkludera efter IP | IP-inställningen ändrades. |
| Namnge sidor | Föråldrat. |
| Klassificeringar | En klassificering hanterades. |
| Datakällor | En datakälla hanterades. |
| Arbetsyteprojekt | Ett Workspace-projekt har visats eller redigerats. |
| Segment | Ett segment skapades/redigerades. |
| Beräknade mått | Ett beräknat mått skapades/redigerades. |
| Datumintervall | Ett datumintervall skapades/redigerades. |
| Virtual Report Suite | En virtuell rapportsvit skapades/redigerades. |
| Bidragsanalys | Ett avgiftsanalysjobb kördes. |
| API-metod | Ett API-anrop gjordes. |


## Ändringslogg för Report Suite {#section_3864966639414BBEA871F4D0352F56B6}

Ändringsloggen för Report Suite visar ändringar som gjorts i rapportsviterna utanför Admin.

Verktyg som kan ändra en rapportserie utanför [!UICONTROL Admin Tools] inkludera:

* Klassificeringar som överförts i en webbläsare (klassificeringar som överförts via FTP inkluderas inte i ändringsloggen)
* Ändringar som gjorts i tidigare versioner.
* Ändringar som gjorts av en kontorepresentant eller kundtjänst med hjälp av interna verktyg

| Element | Beskrivning |
|---|---|
| Datumintervall | Ange ett datumintervallfilter. Du kan ange ett datum manuellt i formatet ÅÅÅÅ-MM-DD eller klicka på kalenderikonen för att välja ett datum. |
| Företag | Filtrera loggen efter företagsnamn. |
| Inloggning | Filtrera loggen efter användarnamn. |
| IP | Filtrera loggen med en IP-adress. |
| Händelse | Filtrera loggen med ett ord eller en fras i händelsebeskrivningen. |
| Ladda ned rapport | Exporterar innehållet i [!UICONTROL Usage & Access Log] till en tabbavgränsad fil. |
