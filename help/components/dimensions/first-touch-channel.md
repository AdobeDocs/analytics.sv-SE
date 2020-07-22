---
title: Första beröringskanalen
description: Den första marknadsföringskanalen inom besökarens förfallodatum för engagemang.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---


# Första beröringskanalen

Dimensionen Första beröringskanal rapporterar den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vilka marknadsföringskanaler som driver den inledande trafiken till er webbplats, så att ni kan fokusera marknadsföringssatsningarna på de områden som är mest effektiva.

## Fyll den här dimensionen med data

Denna dimension refererar direkt till kanalnamn som du har definierat i [Marketing Channel Manager](/help/admin/admin/marketing-channels-admin.md).

Varje träff som skickas till Adobes datainsamlingsservrar går igenom rapportsvitens regler för bearbetning av marknadsföringskanaler. Den itererar igenom varje regel i numerisk ordning tills den hittar en matchning där marknadsföringskanalen knyts till träffen. Den första beröringskanalen stannar kvar hos besökaren tills de inte besöker webbplatsen längre än besökarengagemangsperioden (30 dagar som standard).

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Ange önskat dimensionsobjekt som en kanal i Marketing Channel Manager under Rapportsvitens inställningar.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Besökarens träff på er webbplats måste matcha de villkor som anges i regeln för bearbetning av marknadsföringskanaler, _och_ måste vara det första värdet i marknadsföringskanalen för att göra det under besökarens engagemangsperiod.

Om en efterföljande träff matchar kriterier under en annan marknadsföringskanal skrivs denna dimension inte över med den nya marknadsföringskanalen.

## Dimensionsobjekt

Dimensionsobjekten inkluderar alla kanalnamn i Marketing Channel Manager. Som standard innehåller värdena `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`och `"Referring domains"`. Du kan lägga till eller ta bort kanaler i Marketing Channel Manager, vilket påverkar dimensionens värden.
