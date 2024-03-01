---
title: Implementera Adobe Analytics med Analytics-tillägget
description: Lär dig implementera Adobe Analytics med hjälp av taggar och Analytics-tillägg
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 3%

---

# Implementera Adobe Analytics med Analytics-tillägget

Under Adobe Analytics livstid har Adobe erbjudit flera olika metoder för att implementera kod på er webbplats för datainsamling. Den rekommenderade metoden för Adobe är igenom [Taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) i Adobe Experience Platform.

Taggar i Adobe Experience Platform är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Adobe erbjuder integreringar med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.

Alla kunder som har ett aktivt Adobe Experience Cloud-kontrakt kan använda taggar. Om du är osäker på om du har åtkomst kan du kontakta någon av Experience Cloud systemadministratörerna i din organisation.

Översikt över implementeringsuppgifterna på hög nivå:



![Så här implementerar du Adobe Analytics med hjälp av arbetsflödet för Analytics-tillägg, vilket beskrivs i det här avsnittet.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Uppgift</b></th><th style="width:35%"><b>Mer information</b></th>
</tr>

<tr>
<td> 1</td>
<td>Se till att du har <b>har definierat en rapportsvit</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Skapa ett datalager</b> för att hantera spårning av data på din webbplats.</td>
<td>
<a href="../prepare/data-layer.md">Skapa ett datalager</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Skapa en taggegenskap</b>. Egenskaper är överliggande behållare som används för att referera till tagghanteringsdata.</td>
<td><a href="../launch/create-analytics-property.md">Skapa en Adobe Analytics-taggegenskap</a></td>
</tr>

<tr>
<td>4</td><td><b>Installera Analytics-tillägget</b> i taggegenskapen. Konfigurera Analytics-tillägget för att skicka data till Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en">Översikt över Adobe Analytics-tillägg</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Distribuera till en utvecklingsmiljö</b>. Ha en miljö där du kan iterera om taggutveckling.</td>
<td><a href="./deploy-dev.md">Distribuera en analysimplementering till en utvecklingsmiljö</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validera och publicera i produktion</b>. Bädda in kod för att inkludera taggegenskapen på webbplatsens sidor. Använd sedan dataelement, regler och så vidare för att anpassa implementeringen.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=en#embed-code">Bädda in kod</a><br/><a href="./validate-publish-prod.md">Validera en utvecklingsimplementering och publicera till produktion</a></td>
</tr>

</table>

## Ytterligare resurser

Taggar kan anpassas mycket. Läs mer om hur du får ut mesta möjliga av Adobe Analytics genom att inkludera rätt data i implementeringen.

- [Dokumentation för taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): Lär dig hur gränssnittet fungerar och vilka tillägg som är tillgängliga.

- [Implementeringsvariabler](../vars/overview.md): Avgör vilka variabler du vill skicka till datainsamlingsservrar.
