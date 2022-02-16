---
description: Power BI best practices.
title: God praxis
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 2%

---

# God praxis

## Bevara referenser i Power BI-visualiseringar {#section_7ED14FE64D974681A57EB91EF1B47CB6}

När du har skapat en begäran har den alltid samma referens i Power BI. Om du tar bort en begäran kommer referensen att användas av en ny begäran som du skapar för samma dimension.

Om du tar bort en begäran i arbetsboken bör du kontrollera att det inte finns någon visualisering som pekar på den begäran i Power BI, eftersom visualiseringen annars inte fungerar.

* Om det är möjligt, ta inte bort begäranden som du skapat i Report Builder
* Se till att du även tar bort motsvarande visualisering i Power BI om du gör borttagningsbegäranden på Report Builder.
* Om du inte är säker: ta bort begäranden som du inte längre behöver, publicera igen och gå till Power BI för att se vilka visualiseringar som har brutits
