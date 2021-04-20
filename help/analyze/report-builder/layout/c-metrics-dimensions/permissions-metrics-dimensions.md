---
description: Adobe Report Builder har nu samma behörighetsinställningar som i administrationsverktygen för Analytics.
title: Behörigheter för användaråtkomst till dimensioner och mätvärden
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 7%

---


# Behörigheter för användaråtkomst till dimensioner och mätvärden

Adobe Report Builder har nu samma behörighetsinställningar som i administrationsverktygen för Analytics.

Som icke-admin-användare kan du tidigare ha skapat arbetsböcker med förfrågningar som pekar på dimensioner och mått som du inte har tillgång till. Dessa behörigheter används nu.

Om du till exempel uppdaterar en begäran som innehåller dimensioner eller mått som du inte har tillgång till, får du ett felmeddelande om begränsad behörighet:

![](assets/arb_restrc_perm.png)

Följ de här instruktionerna för **varje** Report Builder-arbetsbok som du underhåller:

1. Öppna arbetsboken.
1. Uppdatera alla begäranden.
1. Om du får en fråga om ett behörighetsfel för användaråtkomst klickar du på **[!UICONTROL Open CSV File]** för att få åtkomst till listan över begränsade behörighetsfel.
1. Skapa filen AllRestrictedPermissionErrors.xlsx och kopiera/klistra in listan med begränsade behörighetsfel från CSV-filen i den här filen.
1. Stäng arbetsboken för Report Builder.

När du har bearbetat alla arbetsböcker bör du ha en omfattande lista med begränsade behörighetsfel i AllRestrictedPermissionErrors.xlsx. Skicka den här listan till administratören för Adobe Analytics-användaråtkomst och be honom/henne att ge dig åtkomst till mätvärden och dimensioner.
