---
title: Kundlojalitet
description: Kategorier baserade på antalet tidigare inköp som en besökare har gjort.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# Kundlojalitet

Kundlojalitet [dimension](overview.md) rapporterar antalet besökare på webbplatsen som har gjort 0 tidigare inköp, 1 tidigare inköp, 2 tidigare inköp eller 3+ tidigare inköp. Den här dimensionen är värdefull för att förstå hur webbplatsen påverkar köpbeteendet. Du kan också använda den här dimensionen i ett segment för att fokusera på besökare som återvänder till ett köp, så att du kan uppmuntra liknande beteende för nya besökare.

## Fyll den här dimensionen med data

Adobe fyller automatiskt i dimensionen baserat på [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) i implementeringen. Om du implementerar `purchase` den här dimensionen fungerar alltid på din webbplats.

## Dimensioner

Dimensionen innehåller följande:

* **Inte en kund**: Vid träffen har besökaren aldrig gjort något inköp förut.
* **Nya kunder**: Vid träffen gjorde besökaren ett enda köp tidigare.
* **Returnera kunder**: Vid träffen gjorde besökaren två köp tidigare.
* **Lojala kunder**: Vid träffen gjorde besökaren tre eller fler köp tidigare.

När en besökare gör ett köp (utlöser `purchase` -händelsen), som inträffar och alla efterföljande träffar flyttas till nästa&quot;bucket&quot;. Om en besökare till exempel köper en produkt från er webbplats för första gången går de från&quot;Inte en kund&quot; till&quot;Nya kunder&quot;, där beställningen&quot;Nya kunder&quot; läggs till. Dimensionsartikeln &quot;Inte en kund&quot; kan inte ha order kopplade till sig.
