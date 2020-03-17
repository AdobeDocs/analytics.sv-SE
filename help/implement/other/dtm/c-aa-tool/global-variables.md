---
description: Fältbeskrivningar och information om variabler när Dynamic Tag Management används för att distribuera Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Globala variabler
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Globala variabler

Fältbeskrivningar och information om variabler när Dynamic Tag Management används för att distribuera Adobe Analytics.

Dessa variabler utlöses på alla beacons för sidinläsningsregler. Du kan uppnå samma effekt genom att använda en [sidinläsningsregel](/help/implement/other/dtm/c-rules/t-rules-page-conditions.md) som är inställd på att köras på alla sidor. These variables might not fire in [Direct-Call](/help/implement/other/dtm/c-rules/t-rules-direct-conditions.md) and [Event-Based](/help/implement/other/dtm/c-rules/t-rules-event-conditions.md) rules.

## Globala variabler - fältbeskrivningar {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Global Variables]**

| Element | Beskrivning |
|--- |--- |
| Server | Den fördefinierade variabeln fyller i serverdimensionen i Adobe Analytics. Se [Server](../../../vars/page-vars/server.md). |
| eVars | [eVar-variabler](../../../vars/page-vars/evar.md) används för att skapa anpassade konverteringsrapporter. |
| Props | [Propvariabler](../../../vars/page-vars/prop.md) används för att skapa anpassade trafikrapporter. |
| Dynamiskt variabelprefix | Ett specialprefix till början av värdet. Standardprefixet är &quot;D=&quot;. Se [Dynamiska variabler](../../../vars/page-vars/dynamic-variables.md) |
