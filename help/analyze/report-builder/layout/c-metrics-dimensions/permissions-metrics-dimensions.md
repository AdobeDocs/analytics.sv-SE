---
description: Adobe Report Builder har nu samma behörighetsinställningar som i administrationsverktygen för Analytics.
title: Behörigheter för användaråtkomst till dimensioner och mätvärden
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 6%

---

# Behörigheter för användaråtkomst till dimensioner och mätvärden

Adobe Report Builder har behörighetsinställningar som liknar dem i administrationsverktygen för Analytics.

Som icke-admin-användare kan du tidigare ha skapat arbetsböcker med förfrågningar som pekar på dimensioner och mått som du inte har tillgång till. Dessa behörigheter används nu.

Om du till exempel uppdaterar en begäran som innehåller dimensioner eller mått som du inte har tillgång till, får du ett felmeddelande om begränsad behörighet. Felmeddelandet anger att en begäran inte är tillgänglig för ditt användarkonto på grund av administratörsbehörighet.

![Skärmbild som visar felmeddelandet Begränsad behörighet.](assets/arb_restrc_perm.png)

Följ dessa instruktioner för att **var** Report Builder som du underhåller:

1. Öppna arbetsboken.
1. Uppdatera alla begäranden.
1. Om du får en fråga om ett behörighetsfel för användaråtkomst klickar du på **[!UICONTROL Open CSV File]** för att få åtkomst till listan över begränsade behörighetsfel.
1. Skapa filen AllRestrictedPermissionErrors.xlsx och kopiera/klistra in listan med begränsade behörighetsfel från CSV-filen i den här filen.
1. Stäng arbetsboken för Report Builder.

När du har bearbetat alla arbetsböcker bör du ha en omfattande lista med begränsade behörighetsfel i AllRestrictedPermissionErrors.xlsx. Skicka den här listan till administratören för Adobe Analytics-användaråtkomst och be honom/henne att ge dig åtkomst till mätvärden och dimensioner.
