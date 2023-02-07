---
description: Administratörer ansvarar för att övervaka hälsotillståndet för datamordlistor. Detta inkluderar huruvida komponenter samlar in data, är godkända, innehåller beskrivningar och är fria från dubbletter.
title: Övervaka dataordlistans hälsa
feature: Components
role: Admin
hide: true
hidefromtoc: true
source-git-commit: b0a3ee6785bdc2f3e9a55e42591b4846984934b6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Övervaka dataordlistans hälsa

{{release-limited-testing}}

Analysadministratörer ansvarar för att upprätthålla en felfri datamordlista.

## Egenskaper för en frisk datamordlista

En felfri datamordlista är en ordlista där alla komponenter:

* Används och samlar in data

* Innehåller användbara beskrivningar så att användarna vet hur de bäst använder dem

* Är fria från onödiga dubbletter

* Godkänns av administratören

## Kontrollera hälsotillståndet för din datamordlista

Så här identifierar du hälsoproblem i din Data Dictionary:

1. Öppna ett Analysis Workspace-projekt.

1. Välj ikonen Datamordlista till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i&quot;Åtkomst till dataordlistan&quot; i [Översikt över dataordlistan](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![Administratörsvy för datamordlista](assets/data-dictionary-admin.png)

1. Kontrollera att rätt Report Suite är markerat i listrutan.

1. På [!UICONTROL **Ordlistehälsa**] flik, välja [!UICONTROL **Visa**] bredvid något av följande alternativ:

   * [!UICONTROL **komponenter saknar beskrivningar**]

   * [!UICONTROL **komponenter har dubbletter**]

   * [!UICONTROL **komponenter saknar dataanslutning**]

   Beroende på vad du väljer tillämpas det aktuella filtret på dataordlistan, och endast de relevanta komponenterna visas.

1. Redigera någon av komponenterna för att förbättra hälsan i datamallen. Mer information om hur du redigerar en komponent i Data Dictionary finns i [Redigera komponentposter i Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).