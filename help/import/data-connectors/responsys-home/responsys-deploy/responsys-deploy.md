---
description: Distribuera dataanslutningen för Responsys för användning i Adobe Analytics.
title: Distribuera integreringen
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---


# Distribuera integreringen{#deploying-the-integration}

Distribuera den här integreringen är en enkel process som kräver följande åtgärder:

## Slutför guiden för integrering av Adobe{#completing-the-adobe-integration-wizard}

Steg för att slutföra integreringsguiden i gränssnittet för Data Connectors.

1. Navigera till området Dataanslutningar (tidigare Genesis) i Adobe Experience Cloud.
1. Starta guiden för integrering av svarssystem.
1. Välj önskad Report Suite och ge integreringen ett namn.
1. Konfigurera följande objekt:

   | Objekt | Beskrivning |
   |---|---|
   | E-postadress | Den primära kontaktens e-postadress |
   | Beskrivning | (Valfritt) Beskrivning av integreringsinställningarna |
   | Konto-ID | Kontakt med supportteamet på support@responsys.com |

1. Konfigurera följande **[!UICONTROL Variable Mappings]**-objekt:

   | Objekt | Beskrivning |
   |---|---|
   | Meddelande-ID | Välj en eVar för att samla in meddelande-ID:n i realtid. |
   | Mottagar-ID | Välj en eVar för att samla in mottagar-ID:n i realtid. |
   | Summa studsar | Välj en numerisk händelse om du vill ta emot dagliga studsar från svar. |
   | E-post skickad | Välj en numerisk händelse som ska tas emot dagligen från svar. |
   | Klickat | Välj en numerisk händelse om du vill få dagliga, totala klickningar från Responsys. |
   | Öppnad | Välj en numerisk händelse om du vill få dagligt totalt antal öppningar från svar. |
   | Avbeställ | Välj en numerisk händelse om du vill få dagliga avbrott i prenumerationen på svar. |
   | Levererat | Välj en numerisk händelse för att ta emot dagliga leveranser från Responsys. |

1. Aktivera dataåtkomst och konfigurera datainsamling.
   1. Byt namn på klassificeringarna efter behov.
   1. **[!UICONTROL Partner segments]** är standardsegment för återmarknadsföring som ingår i er integrering.
   1. Markera kryssrutan under **[!UICONTROL Access Requests]** för att tillåta att produktinformation exporteras till responssystem i dagliga remarknadsföringssegment.
   1. Konfigurera om du ska samla in ID:n genom att manuellt uppdatera din Analytics-samlingskod eller genom att använda den automatiserade lösningen. Om du väljer **[!UICONTROL Automated Solution]** måste du inkludera parametrarna som används i e-postlänkar för att skicka ID:n.
1. Granska alla konfigurationsobjekt och klicka på **[!UICONTROL Activate Now]**.

## Konfigurera i svarssystemet{#configuring-within-the-responsys-system}

För att aktivera integreringen kontaktar du support för responssystem.

När du har slutfört integreringsguiden måste du aktivera integreringen i Responsys.

Kontakta supportteamet på support@responsys.com om du vill göra det.
