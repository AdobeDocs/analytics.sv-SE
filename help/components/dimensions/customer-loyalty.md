---
title: Kundlojalitet
description: Kategorier baserade på antalet tidigare inköp som en besökare har gjort.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---


# Kundlojalitet

Dimensionen Kundlojalitet visar antalet besökare på er webbplats som har gjort 0 tidigare inköp, 1 tidigare inköp, 2 tidigare inköp eller 3+ tidigare inköp. Den här dimensionen är värdefull för att förstå hur webbplatsen påverkar köpbeteendet. Du kan också använda den här dimensionen i ett segment för att fokusera på besökare som återvänder till ett köp, så att du kan uppmuntra liknande beteende för nya besökare.

## Fyll den här dimensionen med data

Adobe fyller automatiskt i den här dimensionen baserat på [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) händelsen i implementeringen. Om du implementerar `purchase` händelsen på din webbplats fungerar alltid den här dimensionen.

## Dimensionsvärden

Dimensionsvärdena omfattar följande:

* **Inte en kund**: Vid träffen har besökaren aldrig gjort något inköp förut.
* **Nya kunder**: Vid träffen gjorde besökaren ett enstaka köp tidigare.
* **Returkunder**: Vid träffen gjorde besökaren två inköp tidigare.
* **Lojala kunder**: Vid träffen gjorde besökaren tre eller fler köp tidigare.

När en besökare gör ett köp (utlöser `purchase` händelsen) flyttas träffen och alla efterföljande träffar in i nästa&quot;bucket&quot;. Om en besökare till exempel köper en produkt från er webbplats för första gången går de från&quot;Inte en kund&quot; till&quot;Nya kunder&quot;, där beställningen&quot;Nya kunder&quot; läggs till. Dimensionsvärdet &quot;Inte en kund&quot; kan inte ha några order kopplade till sig.
