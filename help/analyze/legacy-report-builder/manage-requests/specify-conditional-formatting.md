---
description: Lär dig hur du använder villkorsstyrd formatering i arbetsboksceller.
title: Om villkorsstyrd formatering för arbetsböcker
uuid: 13ac12f1-3498-4bf9-a6d0-c5d84e0125dc
feature: Report Builder
role: User, Admin
exl-id: 5a5f2415-8269-4c8a-9193-784537b29edf
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Ange villkorlig formatering

{{legacy-arb}}

När du har skapat rapporter med inbäddade begäranden kan du använda villkorsstyrd formatering i arbetsboksceller.

Klicka på **[!UICONTROL Format]** i verktygsfältet Report Builder.

Med villkorsstyrd formatering kan du identifiera celler som innehåller resultat eller värden som du vill övervaka. Du kan t.ex. använda röd skuggning eller färgmarkering för en viss cell om intäkterna ligger under förväntningarna och blå skuggning om intäkterna överskrider de förväntade intäkterna. Om en ändring av datumintervall för begäranden tar bort villkor som gör att villkorsstyrd formatering tillämpas på cellvärden, inaktiveras tillfälligt de format som markerar det villkoret. När de villkorsstyrda formaten som du anger inte ändrar något eftersom villkoren inte uppfylls, fortsätter de villkorsstyrda formaten att gälla för celler tills du tar bort dem.

Av säkerhetsskäl inaktiveras makron om du skriver arbetsbokens makron med hjälp av Excel-språket Visual Basic for Applications (VBA).

>[!NOTE]
>
>Villkorsstyrd formatering är en Excel-funktion. Mer information om hur du skapar formateringsregler finns i dokumentationen för Excel.
