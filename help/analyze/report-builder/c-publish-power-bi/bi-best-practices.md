---
description: Power BI best practices.
title: God praxis
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 0%

---

# God praxis

## Bevara referenser i Power BI-visualiseringar {#section_7ED14FE64D974681A57EB91EF1B47CB6}

När du har skapat en begäran har den alltid samma referens i Power BI. Om du tar bort en begäran kommer referensen att användas av en ny begäran som du skapar för samma dimension.

Om du tar bort en begäran i arbetsboken bör du kontrollera att det inte finns någon visualisering som pekar på den begäran i Power BI, eftersom visualiseringen annars inte fungerar.

* Om det är möjligt, ta inte bort begäranden som du skapat i Report Builder
* Se till att du även tar bort motsvarande visualisering i Power BI om du gör borttagningsbegäranden på Report Builder.
* Om du är osäker: ta bort begäranden som du inte behöver längre, publicera igen och gå till Power BI för att se vilka visualiseringar som har brutits
