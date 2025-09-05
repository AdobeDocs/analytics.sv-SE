---
title: Första beröringskanalen
description: Den första marknadsföringskanalen inom besökarens förfallodatum för engagemang.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Första beröringskanalen

Den första beröringskanalen [dimension](overview.md) rapporterar den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vilka marknadsföringskanaler som driver den inledande trafiken till er webbplats, så att ni kan fokusera marknadsföringssatsningarna på de områden som är mest effektiva.

## Fyll den här dimensionen med data

Den här dimensionen refererar direkt till kanalnamn som du har definierat i [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Varje träff som skickas till Adobe datainsamlingsservrar går igenom reglerna för bearbetning av marknadsföringskanaler i rapportsviten. Den itererar igenom varje regel i numerisk ordning tills den hittar en matchning där marknadsföringskanalen knyts till träffen. Den första beröringskanalen stannar kvar hos besökaren tills de inte besöker webbplatsen längre än besökarengagemangsperioden (30 dagar som standard).

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Ange önskat dimensionsobjekt som en kanal i Marketing Channel Manager under Rapportsvitens inställningar.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Besökarens träff på webbplatsen måste matcha de villkor som anges i regeln för bearbetning av marknadsföringskanal, _och_ måste vara det första värdet i marknadsföringskanalen för att göra det under besökarens interaktionsperiod.

Om en efterföljande träff matchar kriterier under en annan marknadsföringskanal skrivs denna dimension inte över med den nya marknadsföringskanalen.

## Dimension-objekt

Dimension-objekt innehåller alla kanalnamn i Marketing Channel Manager. Som standard innehåller värdena `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` och `"Referring domains"`. Du kan lägga till eller ta bort kanaler i Marketing Channel Manager, vilket påverkar dimensionens värden.
