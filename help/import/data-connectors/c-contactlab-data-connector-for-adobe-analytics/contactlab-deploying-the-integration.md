---
description: 'null'
title: Distribuera integreringen
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Distribuera integreringen{#deploying-the-integration}

Distribuera den här integreringen är en enkel process som kräver följande åtgärder:

## Slutför Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Steg för att slutföra integreringsguiden i gränssnittet för Data Connectors.

1. Navigera till området Data Connectors (tidigare Genesis) i Adobe Experience Cloud.
1. Starta integreringsguiden för ContactLab.
1. Välj önskad Report Suite och ge integreringen ett namn.
1. Konfigurera följande objekt:

   | Objekt | Beskrivning |
   |---|---|
   | E-postadress | Den primära kontaktens e-postadress |
   | Beskrivning | (Valfritt) Beskrivning av integreringsinställningarna |

1. Konfigurera följande **[!UICONTROL Variable Mappings]** objekt:

   | Objekt | Beskrivning |
   |---|---|
   | Länk-ID | Välj en eVar för att samla in länk-ID:n i realtid. |
   | Meddelande-ID | Välj en eVar för att samla in meddelande-ID:n i realtid. |
   | Mottagar-ID | Välj en eVar för att samla in mottagar-ID:n i realtid. |
   | studsar | Välj en numerisk händelse om du vill ta emot dagliga studsar från ContactLab. |
   | Skickat | Välj en numerisk händelse som ska tas emot dagligen från ContactLab. |
   | Klickat | Välj en numerisk händelse om du vill få totalt antal klick per dag från ContactLab. |
   | Öppnad | Välj en numerisk händelse om du vill få totalt antal öppningar per dag från ContactLab. |
   | Avbeställ | Välj en numerisk händelse om du vill ta emot dagliga prenumerationer från ContactLab. |

1. Aktivera dataåtkomst och konfigurera datainsamling.
   1. Byt namn på klassificeringarna efter behov.
   1. **[!UICONTROL Partner segments]** är standardsegment för återmarknadsföring som ingår i er integrering.
   1. Under **[!UICONTROL Your Segments]** väljer du de anpassade segment som du vill inkludera i den här integreringen. Du kan skapa ytterligare anpassade segment på administratörspanelen.
   1. Under **[!UICONTROL Access Requests]** markerar du kryssrutan för att tillåta att produktinformation exporteras till ContactLab i dagliga marknadsföringssegment.
   1. Byt namn på beräknade värden efter behov.
   1. Konfigurera om du ska samla in ID:n genom att manuellt uppdatera din Analytics-samlingskod eller genom att använda den automatiserade lösningen. Om du väljer **[!UICONTROL Automated Solution]** det här alternativet måste du inkludera de parametrar som används i e-postlänkar för att skicka ID:n.
1. Granska alla konfigurationsobjekt och klicka på **[!UICONTROL Activate Now]**.

## Verifiera integreringen{#verifying-the-integration}

Visa integrationsinställningarna för ContactLab i Adobe Experience Cloud

1. Visa integreringsaktivitetsloggen.
   1. Navigera till **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]** i Adobe Experience Cloud.

      ![](assets/integration_activity_log.png)

   1. Sök efter poster som **[!UICONTROL Classification Data imported successfully]**, **[!UICONTROL Metrics Data imported successfully]** och **[!UICONTROL Metric Data exported successfully]**. Dessa poster ska visas inom 1 dag efter slutförd distribution.
1. Visa dina rapportdata i Adobe Analytics.
   1. Navigera till **[!UICONTROL Custom Conversion]** > **[!UICONTROL Custom Conversion 1-10]** > **[!UICONTROL Message ID Reports]**.

      ![](assets/reporting.png)

   1. Leta efter ContactLab-rapportering. Dessa data ska visas inom 24-48 timmar efter att distributionen lyckades.
