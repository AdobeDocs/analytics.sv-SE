---
description: Visar djupet för varje besök på webbplatsen, i procent och totalt. Rapporten visar med andra ord hur många sidor den genomsnittliga besökaren på webbplatsen har innan han/hon lämnar den.
title: Banlängd
topic: Reports
uuid: f1c29e78-279a-46a5-b758-d4f0da629239
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Banlängd

Visar djupet för varje besök på webbplatsen, i procent och totalt. Rapporten visar med andra ord hur många sidor den genomsnittliga besökaren på webbplatsen har innan han/hon lämnar den.

Anpassade länkar (s.tl-anrop) läggs inte till i sökvägslängden för sidor. De räknas emellertid i sökvägslängd för avsteg (trafikvariabler).

Flera instanser av samma värde (laddas om) ökar inte sökvägens längd. Exempel:

**[!UICONTROL Page A]** > **[!UICONTROL Page B]** > **[!UICONTROL Custom link]** > **[!UICONTROL Page B]** = Banlängd 2. (Observera att den anpassade länken och inläsningen av sida B inte räknas mot banans längd.)

**[!UICONTROL Prop A]** > **[!UICONTROL Custom Link pass Prop B]** > **[!UICONTROL Prop C]** = Bana längd på 3. (Observera att den anpassade länken för Prop B inte räknas in i banans längd.)
