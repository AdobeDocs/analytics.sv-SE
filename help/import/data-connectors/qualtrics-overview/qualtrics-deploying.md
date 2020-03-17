---
description: Distribuering av den här integreringen är en enkel process som kräver följande åtgärder.
subtopic: Qualtrics
title: Distribuera integreringen
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Distribuera integreringen{#deploying-the-integration}

Distribuering av den här integreringen är en enkel process som kräver följande åtgärder.

## Slutför Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

För att aktivera integreringen måste du slutföra integreringsguiden för Qualtrics i gränssnittet för Data Connectors

1. Navigera till dataanslutningar och starta Qualtrics-integreringsguiden.
1. Välj den rapportsvit som du vill använda för den här integreringen och ange ett namn.

   Slutför integrationsguiden och ange den information som beskrivs i följande steg. 1. Steg 1 av **guiden**

   | E-postadress | Den primära e-postadressen till kontakten. |
   |---|---|
   | Beskrivning | (Valfritt) Beskrivning av den här integrationsinställningen. |
   | Organisations-ID för Qualtrics | [Söker efter ditt Qualtrics Organization ID](../qualtrics-overview/qualtrics-org-id.md) |
   | Adobe SiteCatalyst-token | [Generera din Qualtrics Adobe Analytics-token](../qualtrics-overview/qualtrics-token.md) |

1. **Guidesteg 2 - Variabelmappningar**| Svarslista för frågor| Välj en tillgänglig listvariabel från rapportsviten. (Du kan behöva aktivera en ny listVar i Report Suite Manager.)  ||—|—|| Svars-ID för frågor| Välj en tillgänglig eVar eller en prop från rapportsviten. (Du kan behöva aktivera en ny listVar i Report Suite Manager.)  || Spårningsserver|Ange spårningsserverinställningen (domän) som du använder för att spåra Adobe Analytics-data. Använd spårningsservern `trackingServerSecure` om den skiljer sig från standardinställningen för spårningsserver.  || Kvartalsenkäter| Välj en tillgänglig händelse i rapportsviten (du kan behöva aktivera en ny händelse i Report Suite Manager).  |

1. **Steg 3** i guiden: Inget krävs, endast information.

   Stegresultat 1. **Guidesteg 4 - Exportinställningar**

   | eVar | Välj upp till fem av dina eVars-filer som ska exporteras till Qualtrics |
   |---|---|
   | Händelser | Välj upp till fem av dina anpassade händelser att visa för export till Qualtrics |
   | Props | Välj upp till fem av dina utkast som ska exporteras till Qualtrics |
   | Åtkomstbegäranden | Markera kryssrutan för de standardvärden och -mått som du vill exportera till Qualtrics. Du `visitor_id` måste ange att exporten ska fungera. |

1. **Steg 5** i guiden: Granska konfigurationen och klicka sedan på **[!UICONTROL Activate Now]**.

## Aktivera integreringen i Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

När du har slutfört integreringsguiden måste du aktivera integreringen för varje Qualtrics-undersökning som du vill ansluta.

1. Logga in på Qualtrics Research Suite.
1. På **[!UICONTROL My Surveys]** fliken klickar du på **[!UICONTROL Edit]** knappen för undersökningen som du vill integrera.
1. Klicka på **[!UICONTROL Advanced Options]** menyn och välj **[!UICONTROL Adobe Analytics]**. (Om du inte ser det här alternativet ber du administratören om de behörigheter som krävs).

   ![](assets/advanced_options.png)

1. Välj Adobe Analytics Configuration och klicka sedan på **[!UICONTROL Save]**. Om det inte finns några konfigurationer tillgängliga har du troligen inte slutfört Adobe Integration Wizard ännu.
   1. Kryssrutan **[!UICONTROL Include Partial Responses]** kan användas för att ange att du vill hämta in data till Adobe Analytics när varje delenkätsskärm är klar. Om detta inte är markerat överförs data endast för fullständigt slutförda undersökningar.
   1. Kryssrutan ska bara användas när du integrerar med en Report Suite som är konfigurerad för att ta emot tidsstämplade data (inte vanligt). **[!UICONTROL Send Timestamp With Beacon]**
   ![](assets/integration_config.png)

## Verifiera integreringen{#verifying-the-integration}

När alla distributionssteg har slutförts kan du validera att integreringen har överfört data.

1. **Aktivitetslogg** för integrering: I användargränssnittet för Data Connectors kan du visa fliken **[!UICONTROL Support]** för Qualtrics-integrering. Under rubriken **[!UICONTROL Integration Activity Log]** ska du se poster som anger att klassificeringsdata har importerats.

   >[!NOTE]
   >
   >Dessa poster ska visas inom 1 timme efter distributionen.

   ![](assets/verify-1.png)

1. **Rapporteringsdata**: Visa dina Qualtrics-undersökningsrapporter med marknadsföringsrapporter och analysgränssnitt genom att navigera i Qualtrics-undersökningsrapporten (under **[!UICONTROL List Variables]**).

   >[!NOTE]
   >
   >Dessa data bör visas inom 24-48 timmar efter framgångsrik driftsättning, förutsatt att den integrerade undersökningen aktivt tar emot svar.

   ![](assets/verify-2.png) ![](assets/verify-3.png)


