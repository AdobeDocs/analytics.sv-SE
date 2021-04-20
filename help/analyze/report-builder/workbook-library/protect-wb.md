---
description: Du kan skydda alla begäranden i en arbetsbok mot att lägga till och redigera begäranden genom att låsa arbetsboken. Detta gör att arbetsböcker kan redigeras offline genom att alla rapportförfrågningar pausas för effektivare redigering.
title: Låsa/låsa upp arbetsböcker
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 1%

---


# Låsa/låsa upp arbetsböcker

Du kan skydda alla begäranden i en arbetsbok mot att lägga till och redigera begäranden genom att låsa arbetsboken. Detta gör att arbetsböcker kan redigeras offline genom att alla rapportförfrågningar pausas för effektivare redigering.

Om du låser en arbetsbok som analytiker kan du skydda din arbetsbok mot obehörig åtkomst från andra användare i organisationen. Samtidigt kan dessa användare fortfarande uppdatera förfrågningarna i arbetsboken.

Om du vill skydda en arbetsbok mot redigering klickar du på **[!UICONTROL Locked]** i verktygsfältet Report Builder ( ![](assets/locked_icon.png)

).

Om du vill ta bort skyddet för en arbetsbok klickar du på **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

).

Du kan låsa upp en låst arbetsbok om du har någon av följande behörigheter:

* Du är administratör, eller
* Du är den person som ursprungligen låste arbetsboken. I det här fallet behöver du inte vara administratör.

>[!NOTE]
>
>Du kan inte lägga till en begäran i en skyddad arbetsbok om du inte har behörighet att låsa upp arbetsboken.

När en arbetsbok är låst för redigering av begäranden,

* Användare kan inte skapa/lägga till begäranden.
* Användare kan inte redigera begäranden via begärandeguiden.
* Användare kan inte redigera begäranden med funktionen Redigera flera begäranden.
* Användarna kan inte klippa ut, kopiera eller klistra in begäranden. Användarna kan dock fortfarande använda den inbyggda snabbmenyn Klipp ut/Kopiera/Klistra in för att klippa ut/kopiera/klistra in innehållet i förfrågningarna.
* Användarna kan uppdatera begäranden, antingen individuellt eller som en del av en grupp.
* Om indatavärden från celler (datumintervall, segment, filter) används i begäran, kan användarna ändra dessa värden i cellerna och därmed redigera förfrågningarna indirekt genom att uppdatera dem.

Om du försöker redigera en skyddad arbetsbok (via snabbmenyn, **[!UICONTROL Request Manager]** eller **[!UICONTROL Edit Multiple Requests]**) kan du göra det eller inte:

* Om du inte har behörighet att låsa upp begäranden visas följande uppmaning:

   ![](assets/locked_workbook_error.png)

* Om du har de behörigheter som krävs visas ingen fråga och du kan redigera begäran.

## Arbetsflöde {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Låt oss anta att arbetsbok A har en begäran som är låst och som skapades av användare A.

**Exempel 1: Administratörsanvändare (eller Användare A)**

1. Användaren loggar in på Report Builder och öppnar arbetsbok A.
1. Arbetsbok A är för närvarande låst, så knappen&quot;Skapa begäran&quot; är inaktiverad i verktygsfältet tillsammans med alla andra knappar vars funktion är inaktiverad genom låsning.
1. Om användaren försöker använda någon av de inaktiverade knapparna visas ett meddelande om att arbetsboken är låst.
1. Användaren kan låsa upp arbetsboken, vilket möjliggör fullständig redigeringsfunktionalitet.
1. När arbetsboken har låsts upp förblir den olåst tills den uttryckligen har låsts igen.

**Exempel 2: Användare som inte är administratör (användare B)**

1. Användaren loggar in på Report Builder och öppnar arbetsbok A.
1. Användaren kan inte lägga till/redigera begäran.
1. Användaren kan inte låsa upp arbetsboken.

