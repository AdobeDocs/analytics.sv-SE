---
description: Distribuering av den här integreringen är en enkel process som kräver följande åtgärder.
subtopic: Qualtrics
title: Distribuera integreringen
feature: Data Connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
exl-id: 8637f13d-a07e-412e-9ad7-8a0836301dd6
source-git-commit: 85d199e71fb65e9026156b146201da2e5be37111
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 5%

---

# Distribuera integreringen{#deploying-the-integration}

Distribuering av den här integreringen är en enkel process som kräver följande åtgärder.

## Guiden Integrering av Adobe slutförs{#completing-the-adobe-integration-wizard}

För att aktivera integreringen måste du slutföra integreringsguiden för Qualtrics i gränssnittet för Data Connectors

1. Navigera till dataanslutningar och starta Qualtrics-integreringsguiden.
1. Välj den rapportsvit som du vill använda för den här integreringen och ange ett namn.

   Slutför integrationsguiden och ange den information som beskrivs i följande steg. 1. **Steg 1 av guiden**

   | E-postadress | Den primära e-postadressen till kontakten. |
   |---|---|
   | Beskrivning | (Valfritt) Beskrivning av den här integrationsinställningen. |
   | Organisations-ID för Qualtrics | [Söka efter Qualtrics organisations-ID](../qualtrics-overview/qualtrics-org-id.md) |
   | Adobe SiteCatalyst Token | [Generera Qualtrics Adobe Analytics-token](../qualtrics-overview/qualtrics-token.md) |

1. **Guidesteg 2 - Variabelmappningar**

   | Svarslista för frågor | Välj en tillgänglig listvariabel från rapportsviten. (Du kan behöva aktivera en ny listVar i Report Suite Manager.) |
   |---|---|
   | Svars-ID för frågor | Välj en tillgänglig eVar eller ett erbjudande i din rapportsserie. (Du kan behöva aktivera en ny listVar i Report Suite Manager.) |
   | Spårningsserver | Ange spårningsserverinställningen (domän) som du använder för att spåra Adobe Analytics-data. Använd spårningsservern `trackingServerSecure` om den skiljer sig från standardinställningen för spårningsserver. |
   | Qualtrics Survey Submissions | Välj en tillgänglig händelse i rapportsviten (du kan behöva aktivera en ny händelse inifrån Report Suite Manager). |

1. **Steg 3** i guiden: Inget krävs, endast information.

   Stegresultat 1. **Guidesteg 4 - Exportinställningar**

   | eVar | Välj upp till fem av dina eVars-filer som ska exporteras till Qualtrics |
   |---|---|
   | Händelser | Välj upp till fem av dina anpassade händelser att visa för export till Qualtrics |
   | Props | Välj upp till fem av dina utkast som ska exporteras till Qualtrics |
   | Åtkomstbegäranden | Markera kryssrutan för de standardvärden och -mått som du vill exportera till Qualtrics. `visitor_id` krävs för att exporten ska fungera korrekt. |

1. **Steg 5** i guiden: Granska konfigurationen och klicka sedan på  **[!UICONTROL Activate Now]**.

## Aktivera integreringen i Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

När du har slutfört integreringsguiden måste du aktivera integreringen för varje Qualtrics-undersökning som du vill ansluta.

1. Logga in på Qualtrics Research Suite.
1. På fliken **[!UICONTROL My Surveys]** klickar du på knappen **[!UICONTROL Edit]** för undersökningen som du vill integrera.
1. Klicka på menyn **[!UICONTROL Advanced Options]** och välj **[!UICONTROL Adobe Analytics]**. (Om du inte ser det här alternativet ber du administratören om de behörigheter som krävs).

   ![](assets/advanced_options.png)

1. Markera Adobe Analytics-konfigurationen och klicka sedan på **[!UICONTROL Save]**. Om det inte finns några konfigurationer tillgängliga har du troligen inte slutfört guiden för integrering av Adobe ännu.
   1. Kryssrutan **[!UICONTROL Include Partial Responses]** kan användas för att ange att du vill hämta in data till Adobe Analytics när varje delenkätsskärm är klar. Om detta inte är markerat överförs data endast för fullständigt slutförda undersökningar.
   1. Kryssrutan **[!UICONTROL Send Timestamp With Beacon]** bör endast användas vid integrering med en Report Suite som är konfigurerad att ta emot tidsstämplade data (inte vanlig).

   ![](assets/integration_config.png)

## Verifiera integreringen{#verifying-the-integration}

När alla distributionssteg har slutförts kan du validera att integreringen har överfört data.

1. **Aktivitetslogg** för integrering: I användargränssnittet för Data Connectors kan du visa  **[!UICONTROL Support]** fliken för Qualtrics-integrering. Under rubriken **[!UICONTROL Integration Activity Log]** ska du se poster med godkända klassificeringsdata som importerats.

   >[!NOTE]
   >
   >Dessa poster ska visas inom 1 timme efter distributionen.

   ![](assets/verify-1.png)

1. **Rapporteringsdata**: Visa Qualtrics-undersökningsrapporter med användargränssnittet i marketing reports and analytics genom att navigera i Qualtrics-undersökningsrapporten (under  **[!UICONTROL List Variables]**).

   >[!NOTE]
   >
   >Dessa data bör visas inom 24-48 timmar efter framgångsrik driftsättning, förutsatt att den integrerade undersökningen aktivt tar emot svar.

   ![](assets/verify-2.png) ![](assets/verify-3.png)
