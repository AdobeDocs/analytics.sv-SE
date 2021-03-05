---
description: Distribuera den dynamiska signaldataanslutningen för användning i Adobe Analytics.
title: Distribuera integreringen
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 4%

---


# Distribuera integreringen{#deploying-the-integration}

Att implementera den här integreringen är en enkel process som består av att slutföra guiden för integrering av Adobe och verifiera integreringen.

## Slutför guiden för integrering av Adobe{#completing-the-adobe-integration-wizard}

Steg för att slutföra integreringsguiden i gränssnittet för Data Connectors.

1. Navigera till området Dataanslutningar (tidigare Genesis) i Adobe Experience Cloud.
1. Starta integreringsguiden för dynamisk signal.
1. Välj önskad Report Suite och ge integreringen ett namn.
1. Konfigurera följande objekt:

   | Objekt | Beskrivning |
   |---|---|
   | E-postadress | Den primära kontaktens e-postadress. |
   | Beskrivning | (Valfritt) Beskrivning av den här integrationsinställningen. |
   | Community-ID | Du kan få detta ID från din representant för Dynamic Signal. |

1. Konfigurera följande **[!UICONTROL Variable Mappings]**-objekt:

   | Objekt | Beskrivning |
   |---|---|
   | Spårningskod | Välj en tillgänglig variabel i din rapportserie. |

1. Granska klassificeringarna som ska skapas för den här integreringen.
1. Markera kryssrutan för att skapa kontrollpanelen för integrering av dynamisk signal (valfri, men rekommenderas).
1. Granska alla konfigurationsobjekt och klicka på **[!UICONTROL Activate Now]**.
1. **Viktigt**: När du har slutfört guiden måste du meddela din representant för dynamiska signaler så att de kan aktivera integreringen på VoiceStorm-plattformen.

## Verifiera integreringen{#verifying-the-integration}

Steg för att visa konfigurationen av integreringen av Dynamic Signal VoiceStorm i Adobe Experience Cloud

1. Visa integrationsinställningarna för dynamiska signaler i aktivitetsloggen för integrering.
   1. I Adobe Experience Cloud går du till **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**.

      ![](assets/integration_activity_log.png)

   1. Sök efter poster som **[!UICONTROL Classification Data imported successfully]**. Dessa poster ska visas inom 24 timmar efter att distributionen lyckades.
1. Granska dina Dynamic Signal-rapporter i Adobe Analytics med den Dashboard som automatiskt skapades för dig med hjälp av guiden för integrering av Adobe (steg 7). Du kan också navigera till Dynamic Signal-rapporten i menystrukturen för Adobe Analytics - se följande skärmbilder.

   **Obs**: Dessa data ska visas inom 24-48 timmar efter att distributionen lyckades.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
