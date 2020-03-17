---
description: Ställ in åtgärder som du vill att villkoret ska utlösas.
keywords: Dynamic Tag Management;rule;create rule;new rule;javascript/third party tags;set up actions for condition;add new script;non-sequential javascript;sequential javascript;non-sequential html
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Ställ in åtgärder för villkoret som ska utlösas
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Ställ in åtgärder för villkoret som ska utlösas

Ställ in åtgärder som du vill att villkoret ska utlösas.

När du har ställt in villkoret måste du ställa in de åtgärder som du vill att villkoret ska utlösas. Dessa åtgärder kan omfatta [!DNL Analytics] händelser, taggar från tredje part och egna skript. I det här exemplet beskrivs hur du konfigurerar skript eller tredjepartstaggar.

Förutom integrerade verktyg som [!DNL Adobe Analytics] och Google Analytics kan Dynamic Tag Management utlösa alla typer av JavaScript-skript eller mata in HTML på er webbplats, på utvalda sidor eller i specifika scenarier.

Varje regel kan utlösa så många skript eller HTML-injektioner du vill.

> [!NOTE] Eftersom du kan använda DTM för att mata in egen kod på sidan bör du se till att inte skapa XSS-sårbarheter (XSS) (mer information finns i [OWASP:s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) ). Att använda dataelement i ett skript kräver särskild uppmärksamhet. Anta alltid att dataelementvärden kan komma från en otillförlitlig källa.

**Så här ställer du in åtgärder för villkoret som ska utlösas**

1. Klicka **[!UICONTROL JavaScript / Third Party Tags]** för att lägga till ett nytt skript i regeln.

   ![](assets/scripts-actions.png)

1. Klicka på **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. Namnge skriptet.
1. Ange hur du vill att skriptet ska utlösas och klistra in önskat innehåll i textområdet. ![](assets/scripts-actions3.png)

1. Klicka **[!UICONTROL Save Code]** så läggs skriptet till i kön för regeln. ![](assets/scripts-actions4.png)

