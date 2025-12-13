---
title: Senaste beröringskanal
description: Den senaste marknadsföringskanalen inom besökarens förfallodatum för engagemang.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: 31c3f83f1142a4ba92a390e35ca8dcae66dfa660
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Senaste beröringskanal

Den sista beröringskanalen [dimension](overview.md) rapporterar den senaste marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vilka marknadsföringskanaler som driver trafik till er webbplats, vilket leder till konverteringar, så att ni kan fokusera marknadsföringssatsningarna på de områden som är mest effektiva.

## Fyll den här dimensionen med data

Den här dimensionen refererar direkt till kanalnamn som du har definierat i [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Varje träff som skickas till Adobe datainsamlingsservrar går igenom reglerna för bearbetning av marknadsföringskanaler i rapportsviten. Den itererar igenom varje regel i numerisk ordning tills den hittar en matchning där marknadsföringskanalen knyts till träffen. Den sista beröringskanalen behålls med besökaren tills de inte besöker webbplatsen längre än besökarengagemangsperioden (30 dagar som standard).

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Ange önskat dimensionsobjekt som en kanal i Marketing Channel Manager under Rapportsvitens inställningar.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Besökarens träff på webbplatsen måste matcha de villkor som anges i regeln för bearbetning av marknadsföringskanal.

>[!TIP]
>
>Om du använder den här dimensionen med mätvärden som använder [deltagarattribuering](/help/analyze/analysis-workspace/attribution/models.md) kan krediteringen tilldelas `None` när andra attribueringsmodeller inte gör det. Deltagandestatistik kräver en marknadsföringskanal [instans](../metrics/instances.md) i rapporteringsfönstret för att få kredit. Om marknadsföringskanalen ursprungligen ställdes in utanför rapporteringsfönstret och bara det bestående värdet finns inuti rapporteringsfönstret, är det `None` som attribuerar medverkandemåttskrediten. Andra attribueringsmodeller tilldelar kredit till det beständiga värdet. Om du vill undvika attribuering till `None` i det här scenariot bör du använda en attribueringsmodell som inte ingår.

## Dimension-objekt

Dimension-objekt innehåller alla kanalnamn i Marketing Channel Manager. Som standard innehåller värdena `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` och `"Referring domains"`. Du kan lägga till eller ta bort kanaler i Marketing Channel Manager, vilket påverkar dimensionens värden.
