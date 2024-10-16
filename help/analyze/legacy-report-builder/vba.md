---
title: Så här använder du Visual Basic-makron i Report Builder
description: Lär dig hur du utökar funktionerna i Excel-arbetsböcker och Report Builder med hjälp av VBA-makron.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---

# Visual Basic-makron i Report Builder

VBA-makron (Visual Basic) innehåller funktioner som hjälper dig att uppdatera Excel-arbetsböcker. Visual Basic har tillgång till arbetsboken, Excel och Windows.

Du måste köra den senaste versionen av Report Builder och logga in innan du kör VBA-makron.

>[!IMPORTANT]
>
>Av säkerhetsskäl kan du inte schemalägga en arbetsbok som innehåller ett makro.

Adobe stöder tre Report Builder API-metoder.

## `RefreshAllReportBuilderRequests()`

Makrot `RefreshAllReportBuilderRequests()` uppdaterar alla Report Builder-begäranden i den aktiva arbetsboken. Det börjar med att anropa Report Builder COM-tillägget via dess produkt-ID och sedan anropar API-kommandot `RefreshAllRequests()`:

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

Makrot `RefreshAllReportBuilderRequestsInActiveWorksheet()` uppdaterar alla Report Builder-begäranden i det aktiva kalkylbladet. API-anropet `RefreshWorksheetRequests()` tar ett kalkylbladsobjekt som argument. Du kan använda det här anropet för alla kalkylblad som innehåller förfrågningar från Report Builder:

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

Makrot `RefreshAllReportBuilderRequestsInCellsRange()` uppdaterar alla Report Builder-begäranden vars cellutdata överlappar det angivna cellområdet. Cellintervallet som används i det här exemplet pekar på intervallet `B1:B54` för arbetsbladet Data i den aktiva arbetsboken. Intervalluttrycket stöder alla Excel-intervalluttryck som stöds:

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
