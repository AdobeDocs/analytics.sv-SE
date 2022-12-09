---
title: Senaste pekkanal
description: Den senaste marknadsföringskanalen inom besökarens förfallodatum för engagemang.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: 6f7f46b0fee46e572a65f639ea511478c0118f4e
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Senaste pekkanal

Dimensionen&quot;Sista beröringskanalen&quot; rapporterar den senaste marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vilka marknadsföringskanaler som driver trafik till er webbplats, vilket leder till konverteringar, så att ni kan fokusera marknadsföringssatsningarna på de områden som är mest effektiva.

## Fyll den här dimensionen med data

Den här dimensionen refererar direkt till kanalnamn som du har definierat i [Marknadskanalchef](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels-admin.md).

Varje träff som skickas till datainsamlingsservrar i Adobe går igenom rapportsvitens regler för bearbetning av marknadsföringskanaler. Den itererar igenom varje regel i numerisk ordning tills den hittar en matchning där marknadsföringskanalen knyts till träffen. Den sista beröringskanalen behålls med besökaren tills de inte besöker webbplatsen längre än besökarengagemangsperioden (30 dagar som standard).

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Ange önskat dimensionsobjekt som en kanal i Marketing Channel Manager under Rapportsvitens inställningar.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Besökarens träff på webbplatsen måste matcha de villkor som anges i regeln för bearbetning av marknadsföringskanal.

## Dimensioner

Dimensioner innehåller alla kanalnamn i Marketing Channel Manager. Som standard innehåller värdena `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`och `"Referring domains"`. Du kan lägga till eller ta bort kanaler i Marketing Channel Manager, vilket påverkar dimensionens värden.
