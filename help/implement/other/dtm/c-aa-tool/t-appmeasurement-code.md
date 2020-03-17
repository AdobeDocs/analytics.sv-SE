---
description: Infoga AppMeasurement-kod när dynamisk tagghantering distribueras manuellt i Adobe Analytics.
keywords: Dynamic Tag Management;linked accounts;linking accounts;edit code;appmeasurement;appmeasurement code
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Infoga AppMeasurement-huvudkod
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Infoga AppMeasurement-huvudkod

Infoga AppMeasurement-kod när dynamisk tagghantering distribueras manuellt i Adobe Analytics.

1. Expandera [!DNL Adobe Analytics] avsnittet på **[!UICONTROL General]** verktygssidan och klicka sedan på **[!UICONTROL Open Editor]**.
1. Zippa upp den [!DNL AppMeasurement_JavaScript*.zip] fil du laddat ned i [distribuera Adobe Analytics](/help/implement/other/dtm/t-analytics-deploy.md).

   Om du väljer ett anpassat bibliotek har det redan den senaste kodversionen när du öppnar fönstret. Du behöver inte hämta zip-filen från Admin Console.
1. Öppna [!DNL AppMeasurement.js] i en textredigerare.
1. Kopiera och klistra in innehållet i **[!UICONTROL Edit Code]** fönstret.

   ![](assets/edit-code.png)

1. Adobe rekommenderar att du lägger till följande kod ovanför *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >Om du lägger till den här koden bör du även markera kryssrutan **[!UICONTROL Set report suites using custom code below]** i de övergripande biblioteksinställningarna.

1. Klicka på **[!UICONTROL Save and Close]**.

   Om du använder mediemodulen, integreringsmodulen eller implementeringsplugin-program kan du kopiera dem även till kodavsnittet. Den hanterade koden i Dynamic Tag Management kan konfigureras exakt som JavaScript-filen i en vanlig implementering.

