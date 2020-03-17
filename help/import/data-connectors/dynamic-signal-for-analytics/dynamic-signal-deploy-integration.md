---
description: 'null'
title: Distribuera integreringen
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Distribuera integreringen{#deploying-the-integration}

Att implementera integreringen är en enkel process som består av att slutföra Adobe Integration Wizard och verifiera integreringen.

## Slutför Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Steg för att slutföra integreringsguiden i gränssnittet för Data Connectors.

1. Navigera till området Data Connectors (tidigare Genesis) i Adobe Experience Cloud.
1. Starta integreringsguiden för dynamiska signaler.
1. Välj önskad Report Suite och ge integreringen ett namn.
1. Konfigurera följande objekt:

   | Objekt | Beskrivning |
   |---|---|
   | E-postadress | Den primära kontaktens e-postadress. |
   | Beskrivning | (Valfritt) Beskrivning av den här integrationsinställningen. |
   | Community-ID | Du kan få det här ID:t från din representant för Dynamic Signal. |

1. Konfigurera följande **[!UICONTROL Variable Mappings]** objekt:

   | Objekt | Beskrivning |
   |---|---|
   | Spårningskod | Välj en tillgänglig eVar-variabel från rapportsviten. |

1. Granska klassificeringarna som ska skapas för den här integreringen.
1. Markera kryssrutan för att skapa kontrollpanelen för integrering av dynamisk signal (valfri, men rekommenderas).
1. Granska alla konfigurationsobjekt och klicka på **[!UICONTROL Activate Now]**.
1. **Viktigt**: När du har slutfört guiden måste du meddela din representant för dynamiska signaler så att de kan aktivera integreringen på VoiceStorm-plattformen.

## Verifiera integreringen{#verifying-the-integration}

Steg för att visa konfigurationen av integreringen av Dynamic Signal VoiceStorm i Adobe Experience Cloud

1. Visa integrationsinställningarna för dynamiska signaler i aktivitetsloggen för integrering.
   1. Gå till **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]** i Adobe Experience Cloud.

      ![](assets/integration_activity_log.png)

   1. Leta efter tävlingsbidrag som **[!UICONTROL Classification Data imported successfully]**. Dessa poster ska visas inom 24 timmar efter att distributionen lyckades.
1. Granska de dynamiska signeringsrapporterna i Adobe Analytics med den Dashboard som automatiskt skapades för dig med hjälp av Adobe Integration Wizard (steg 7). Du kan också navigera till Dynamic Signal-rapporten i menystrukturen för Adobe Analytics - se följande skärmbilder.

   **Obs**: Dessa data ska visas inom 24-48 timmar efter att distributionen lyckades.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
