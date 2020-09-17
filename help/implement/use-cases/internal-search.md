---
title: Hämta interna söktermer
description: Använd en anpassad variabel för att hämta interna söktermer.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---


# Hämta interna söktermer

Intern sökrapportering är en väsentlig del av många organisationer och är inte en färdig dimension med Adobe Analytics. Med minimala implementeringsansträngningar kan dock interna söktermsrapporter enkelt fångas in.

## Förutsättningar

[Validera en utvecklingsimplementering och publicera till produktion](../launch/validate-publish-prod.md): På den här sidan förutsätts att du har en grundläggande arbetsimplementering och att du ser en begäran om Adobe Analytics-bilder i felsökningsprogrammet för Adobe.

## Skapa en eVar för intern sökning

Följ administratören [för](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) konverteringsvariabler när du vill skapa en ny eVar som är dedikerad till intern sökning. Ge eVar ett namn som är lätt att känna igen (t.ex.&quot;Internt sökord&quot;) och registrera den nya eVar i organisationens [Solution-designdokument](../prepare/solution-design.md).

## Ange internt söknyckelord

De flesta interna sökningar använder frågesträngar för att skicka nyckelordsdata mellan sidor. Använd webbplatsens interna sökning och notera URL:en på sökresultatsidan:

`https://example.com/search.html?q=kittens`

Om webbplatsens interna sökning inte använder URL-adressen söker du efter söktermen på andra platser, till exempel ett datalager eller en cookie-fil. Arbeta med webbplatsens utvecklingsteam om du inte vet var du ska hitta den interna söktermen.

## Tilldela frågesträngsparametern till ett dataelement

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). När du markerar **[!UICONTROL Data Element Type]** markeringen väljer du **[!UICONTROL Query string parameter]** istället för **[!UICONTROL JavaScript Variable]**. Placera den önskade frågesträngsparametern (vanligtvis `q`) i textfältet.

## Mappa dataelementet till eVar

Follow [Map Launch data elements to Analytics variables](../launch/elements-to-variable.md). Se till att du väljer samma eVar som du skapade i inställningarna för rapportsviten.

## Starta Launch-distributionsprocessen

Följ [Distribuera en analysimplementering till en utvecklingsmiljö](../launch/deploy-dev.md). När du har bekräftat att det fungerar i utvecklingsmiljön kan du [validera en implementering och publicera i produktionen](../launch/validate-publish-prod.md).

## Rapportering på arbetsytan

Ge implementeringen lite tid att samla in data, så kan ni börja använda dimensionen i Analysis Workspace.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. Om du inte loggar in automatiskt på Adobe Analytics klickar du på 9-rutnätikonen i det övre högra hörnet och väljer **[!UICONTROL Analytics]**.
3. Klicka på **[!UICONTROL Workspace]** fliken och skapa ett nytt projekt.
4. Leta reda på namnet på eVar som du skapade under Dimensioner och dra det till arbetsytan.
