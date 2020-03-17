---
description: Villkoren avgör när en händelsebaserad regel aktiveras.
keywords: Dynamic Tag Management;rule;create rule;new rule;event-based rule;delay link activation;apply event handler directly to element;bubbling;event bubbling
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Skapa villkor för händelsebaserade regler
uuid: a847391c-5aec-4d64-8a35-388587731598
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Skapa villkor för händelsebaserade regler

Villkoren avgör när en händelsebaserad regel aktiveras.

1. Välj vilken typ av interaktion du vill spåra, till exempel musklick, eller skicka ett formulär.

   ![](assets/condition-event-based.png)

   Mer information finns i [Händelsetyper](https://marketing.adobe.com/resources/help/en_US/dtm/event_types.html) i produktdokumentationen för Adobe Tag Management.

1. Aktivera följande alternativ efter behov:

   | Element | Beskrivning |
   |--- |--- |
   | Fördröj länkaktivering | Aktivera om händelsen aktiverar en länk och du vill att länken ska fördröjas tills händelsen får tid att utlösas. |
   | Tillämpa händelsehanterare direkt på elementet | Tillämpar händelsehanteraren på det specifika element som är mål. Den här inställningen är kopplad till bubblings- och lagerkonceptet i en webbläsare. |

   Om du till exempel klickar på en bild inuti en ankartagg som `<a href="abc.html"><img src="xyz.png"/></a>`kanske du förväntar dig att klickningen kopplas till ankartaggen, eftersom taggen finns i bubbelströmmen. När du inspekterar klickningen i utvecklingsverktygen kan det dock hända att klickningen bara påverkar `<img>` taggen. Om du vill vara säker på att händelsen hanteras korrekt associerar du klickningen med `<img>` -taggen och är inte beroende av webbläsaren för att bubbla upp klickningen till ett överordnat element. En händelse som en klickning kan eventuellt bubbla upp till `<body>`. Det är viktigt att förstå var händelsen verkligen är bunden och inrikta den specifikt för att se till att regeln utlöses korrekt.

   *Bubbling* innebär att händelsen först fångas in och hanteras av elementet längst in och sedan sprids till yttre element.

1. Ange namnet på taggen som du vill spåra och ytterligare egenskaper som taggen har som du vill matcha.

   ![](assets/condition-event-based2.png)

   Mer information om hur du hittar rätt elementtagg finns i [Använda CSS-väljaren](https://marketing.adobe.com/resources/help/en_US/dtm/css-selector.html) i produktdokumentationen för dynamisk tagghantering.

1. Välj och ange eventuella ytterligare villkor eller villkorstyper som du vill binda till regeln.

   ![](assets/condition-event-based3.png)

1. Ange din inställning för händelsebubbling.

   Händelsebubbling är ett sätt att sprida händelser i HTML DOM.

   | Om du.. | Markera det här alternativet |
   |--- |--- |
   | Vill ha relaterade interaktioner på underordnade element för regelväljaren som du identifierade för att utlösa regeln. | Tillåt att händelser för underordnade element bubblar. |
   | Vill förhindra bubbling när det underordnade elementet redan utlöser sin egen händelse. | Tillåt inte om det underordnade elementet redan utlöser en händelse. |
   | Vill inte att händelserna för regelväljaren som du identifierade ska gå utanför själva elementet i händelsehierarkin. | Tillåt inte att händelser bubblar uppåt till föräldrar. |
