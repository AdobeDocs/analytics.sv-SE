---
title: Visual Basic-makron i Report Builder
description: Utöka funktionaliteten i Excel-arbetsböcker och Report Builder med hjälp av VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Visual Basic-makron i Report Builder

Med VBA-makron, som även kallas Visual Basic-makron, kan du hantera arbetsböcker på ett sätt som bara Microsoft Excel inte kan. Visual Basic har tillgång till arbetsboken, Excel och till och med Windows.

Adobe stöder tre Report Builder API-metoder. Kontrollera att den senaste versionen av Report Builder är installerad och logga in innan du kör några makron.

>[!IMPORTANT]
>
>Av säkerhetsskäl kan du inte schemalägga en arbetsbok som innehåller ett makro.

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` alla Report Builder-begäranden i den aktiva arbetsboken uppdateras. Det börjar med att ringa Report Builder COM-tillägget via produkt-ID:t och sedan anropar `RefreshAllRequests()` API-kommando:

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` makrot uppdaterar alla Report Builder-begäranden i det aktiva kalkylbladet. The `RefreshWorksheetRequests()` API-anrop tar ett kalkylbladsobjekt som argument. Du kan använda det här anropet för alla kalkylblad som innehåller förfrågningar från Report Builder:

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

The `RefreshAllReportBuilderRequestsInCellsRange()` makrot uppdaterar alla Report Builder-begäranden vars cellutdata korsar det angivna cellintervallet. Cellområdet som används i det här exemplet pekar på området `B1:B54` av arbetsbladet&quot;Data&quot; i den aktiva arbetsboken. Intervalluttrycket stöder alla Excel-intervalluttryck som stöds:

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
