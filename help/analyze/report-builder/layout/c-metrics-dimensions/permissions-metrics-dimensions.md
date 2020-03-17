---
description: Adobe Report Builder har nu behörighetsinställningar som liknar dem i administrationsverktygen för Analytics.
title: Behörigheter för användaråtkomst för mått och mätvärden
topic: Report builder
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Behörigheter för användaråtkomst för mått och mätvärden

Adobe Report Builder har nu behörighetsinställningar som liknar dem i administrationsverktygen för Analytics.

Som icke-admin-användare kan du tidigare ha skapat arbetsböcker med förfrågningar som pekar på dimensioner och mått som du inte har tillgång till. Dessa behörigheter används nu.

Om du till exempel uppdaterar en begäran som innehåller dimensioner eller mått som du inte har tillgång till, får du ett felmeddelande om begränsad behörighet:

![](assets/arb_restrc_perm.png)

Följ dessa anvisningar för **varje** Report Builder-arbetsbok som du underhåller:

1. Öppna arbetsboken.
1. Uppdatera alla begäranden.
1. Om du får en fråga om ett behörighetsfel för användaråtkomst klickar du för **[!UICONTROL Open CSV File]** att få åtkomst till listan över begränsade behörighetsfel.
1. Skapa filen AllRestrictedPermissionErrors.xlsx och kopiera/klistra in listan med begränsade behörighetsfel från CSV-filen i den här filen.
1. Stäng Report Builder-arbetsboken.

När du har bearbetat alla arbetsböcker bör du ha en omfattande lista med begränsade behörighetsfel i AllRestrictedPermissionErrors.xlsx. Skicka den här listan till din Adobe Analytics-administratör för användaråtkomst och be honom/henne att ge dig åtkomst till mätvärden och dimensioner.
