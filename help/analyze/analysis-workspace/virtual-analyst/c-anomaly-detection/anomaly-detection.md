---
description: Du kan visa och analysera dataavvikelser i sitt sammanhang på arbetsytan för analyser.
title: Översikt över avvikelseidentifiering
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Översikt över avvikelseidentifiering

Du kan visa och analysera dataavvikelser i sitt sammanhang i Analysis Workspace.

[Analysidentifiering på YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&index=63&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

[Bidragsanalys på YouTube](https://www.youtube.com/watch?v=MbpeJIADtGk&index=64&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (3:20)

>[!IMPORTANT] Analysidentifiering har tagits bort från funktionerna Rapporter och analys och är nu bara tillgängligt via Analysis Workspace. Observera att kunder som använder Adobe Analytics Select och Adobe Analytics Foundation bara har tillgång till&quot;daglig granularitetsidentifiering&quot; i Workspace. Mer information finns i Behörigheter för avvikelseidentifiering och [bidragsanalys](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A).

Analysidentifiering är en statistisk metod för att fastställa hur ett givet mätresultat har ändrats i förhållande till tidigare data.

Anomaly Detection gör det möjligt att skilja &quot;sanna signaler&quot; från &quot;brus&quot; och sedan identifiera potentiella faktorer som bidragit till dessa signaler eller avvikelser. Med andra ord kan du identifiera vilka statistiska fluktuationer som är viktiga och vilka som inte gör det. Sedan kan du identifiera roten till en sann avvikelse. Dessutom kan du få tillförlitliga KPI-prognoser.

Exempel på avvikelser du kan undersöka är:

* Drastiska droppar i genomsnittligt ordervärde
* Inträffar i order med låg intäkt
* Taggar eller droppar i testregistreringar
* Droppar i landningssidvyer
* Inslag i videobufferthändelser
* Taggar i låga videobithastigheter

Både avvikelseidentifiering och [bidragsanalys](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_main.html) är centrala arbetsflöden i Analysis Workspace. Du kan köra Contribute Analysis mot alla dagliga avvikelser och bädda in resultatet i Analysis Workspace-projektet.

Analysarbetsytans avvikelseavkänningsalgoritm innehåller

* Stöd för kornighet varje timme, vecka och månad utöver den befintliga kornigheten.
* Kännedom om säsongsvaraktighet (t.ex. &quot;Black Friday&quot;) och semester.
