---
title: Implementera Adobe Analytics med Adobe Experience Platform Edge Network Server API
description: Använd API:t för Adobe Experience Platform Edge Network Server för att skicka data till Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Implementera Adobe Analytics med Adobe Experience Platform Edge Network Server API

Du använder vanligtvis Experience Platform Edge Network Server API för att samla in data på serversidan i stället för på klientsidan och när du samlar in data från enheter som IoT-enheter, digitalboxar och datorprogram. Sedan skickar du dessa data till Edge-nätverket och till tjänster som Adobe Analytics.

Överväg också Edge Network Server API när du kräver att känsliga data samlas in säkert och autentiseras i nätverket. Se [Autentisering](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html) för mer information.

Översikt över implementeringsuppgifterna på hög nivå:

![Adobe Analytics med hjälp av arbetsflödet för Analytics-tillägget](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Uppgift</b></th><th style="width:35%"><b>Mer information</b></th>
</tr>

<tr>
<td>1</td>
<td>Se till att du har <b>har definierat en rapportsvit</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Konfigurera scheman</b>. För att standardisera datainsamlingen för användning i olika program som utnyttjar Adobe Experience Platform har Adobe skapat den öppna och offentligt dokumenterade standarden Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html">Översikt över schemaanvändargränssnittet</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Konfigurera ett datastream</b>. En datastream representerar konfigurationen på serversidan när API:erna från Adobe Experience Platform Edge Network API används.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html">Konfigurera ett datastream<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implementera och testa datainsamling</b> med API:erna för insamling av data från en händelse och en grupphändelsedatainsamling.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html">Datainsamling för en händelse</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">Datainsamling för batchhändelse</a>
</tr>

<td>5</td>
<td><b>Lägg till en Adobe Analytics-tjänst</b> till din datastream. Tjänsten styr om och hur data skickas till Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.htmls">Interagera med Adobe Analytics</a></td>
</tr>


</table>

Se [API-dokumentation för Edge Network Server](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html)och ett exempel [integrering med Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html) för mer information.

