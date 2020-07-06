---
description: Ni kan visa och analysera dataavvikelser i sitt sammanhang, inom Analysis Workspace.
title: Översikt över avvikelseidentifiering
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 12%

---


# Översikt över avvikelseidentifiering

Ni kan visa och analysera dataavvikelser i sitt sammanhang inom Analysis Workspace.

[Analysidentifiering på YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

[Bidragsanalys på YouTube](https://www.youtube.com/watch?v=MbpeJIADtGk&amp;index=64&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (3:20)

>[!IMPORTANT]
>
>Analysidentifiering har tagits bort från funktionerna Rapporter och Analytics och är nu endast tillgängligt via Analysis Workspace. Tänk på att kunder som använder Adobe Analytics Select och Adobe Analytics Foundation bara har tillgång till avvikelseidentifiering på dagsnivå i Workspace. Mer information finns i Behörigheter för avvikelseidentifiering och [bidragsanalys](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A).

Analysidentifiering är en statistisk metod för att fastställa hur ett givet mätresultat har ändrats i förhållande till tidigare data.

Anomaly Detection gör det möjligt att skilja &quot;sanna signaler&quot; från &quot;brus&quot; och sedan identifiera potentiella faktorer som bidragit till dessa signaler eller avvikelser. Med andra ord kan du identifiera vilka statistiska fluktuationer som är viktiga och vilka som inte gör det. Sedan kan du identifiera roten till en sann avvikelse. Dessutom kan du få tillförlitliga KPI-prognoser.

Exempel på avvikelser du kan undersöka är:

* Drastiska droppar i genomsnittligt ordervärde
* Inträffar i order med låg intäkt
* Taggar eller droppar i testregistreringar
* Droppar i landningssidvyer
* Inslag i videobufferthändelser
* Taggar i låga videobithastigheter

Both Anomaly Detection and [Contribution Analysis](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) are core workflows in Analysis Workspace. Du kan köra Contribute Analysis mot alla dagliga avvikelser och bädda in resultatet i ditt Analysis Workspace-projekt.

Analysis Workspace, avvikelalidentifieringsalgoritm

* Stöd för kornighet varje timme, vecka och månad utöver den befintliga kornigheten.
* Kännedom om säsongsvaraktighet (t.ex. &quot;Black Friday&quot;) och semester.
