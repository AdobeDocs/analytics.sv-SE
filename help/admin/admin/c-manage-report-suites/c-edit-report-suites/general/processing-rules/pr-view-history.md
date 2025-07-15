---
title: Bearbetar regelvyhistorik
description: Se vilka ändringar som har gjorts tidigare i bearbetningsreglerna.
feature: Processing Rules
role: Admin
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Bearbetar regelvyhistorik

Med det här gränssnittet kan du se alla ändringar som någonsin har gjorts i bearbetningsreglerna för den här rapportsviten. Det är värdefullt i fall där du kan behöva återställa ändringar eller felsöka problem som påverkar datakvaliteten.

Varje gång ändringar sparas i bearbetningsreglerna skapas en ögonblicksbild som sparar information om statusen för bearbetningsreglerna vid den tidpunkten.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]** > **[!UICONTROL View history]**

Tabellen innehåller tre kolumner:

* **[!UICONTROL Created]**: Tidsstämpeln när ögonblicksbilden skapades.
* **[!UICONTROL User]**: Användaren som ändrade bearbetningsregler.
* **[!UICONTROL View]**: En länk som tar dig till det som bearbetningsreglerna var vid den tidpunkten.

Välj knappen **[!UICONTROL Copy to current ruleset]** när du visar regelhistoriken om du vill återställa bearbetningsreglerna till det valda datumet. Omversioner tillämpas inte förrän du har valt **[!UICONTROL Save]**.
