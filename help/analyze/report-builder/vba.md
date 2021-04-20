---
title: Visual Basic-makron i Report Builder
description: Utöka funktionaliteten i Excel-arbetsböcker och Report Builder med hjälp av VBA.
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---


# Visual Basic-makron i Report Builder

Med VBA-makron, som även kallas Visual Basic-makron, kan du hantera arbetsböcker på ett sätt som bara Microsoft Excel inte kan. Visual Basic har tillgång till arbetsboken, Excel och till och med Windows.

Adobe stöder tre Report Builder API-metoder. Kontrollera att den senaste versionen av Report Builder är installerad och logga in innan du kör några makron.

>[!IMPORTANT]
>
>Av säkerhetsskäl kan du inte schemalägga en arbetsbok som innehåller ett makro.

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

Makrot `RefreshAllReportBuilderRequestsInCellsRange()` uppdaterar alla Report Builder-begäranden vars cellutdata överlappar det angivna cellintervallet. Cellintervallet som används i det här exemplet pekar på intervallet `B1:B54` för arbetsbladet&quot;Data&quot; i den aktiva arbetsboken. Intervalluttrycket stöder alla Excel-intervalluttryck som stöds:

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
