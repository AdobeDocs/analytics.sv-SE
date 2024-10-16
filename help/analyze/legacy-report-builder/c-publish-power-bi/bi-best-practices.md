---
description: Power BI best practices.
title: God praxis
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 0%

---

# God praxis

## Bevara referenser i Power BI-visualiseringar

När du har skapat en begäran har den alltid samma referens i Power BI. Om du tar bort en begäran kommer referensen att användas av en ny begäran som du skapar för samma dimension.

Om du tar bort en begäran i arbetsboken bör du kontrollera att det inte finns någon visualisering som pekar på den begäran i Power BI, eftersom visualiseringen annars inte fungerar.

* Om det är möjligt, ta inte bort begäranden som du skapat i Report Builder
* Se till att du även tar bort motsvarande visualisering i Power BI om du gör borttagningsbegäranden på Report Builder.
* Om du är osäker: ta bort begäranden som du inte behöver längre, publicera igen och gå till Power BI för att se vilka visualiseringar som har brutits
