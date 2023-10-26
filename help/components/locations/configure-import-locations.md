---
description: Konfigurera molnimportkontot och platsen där klassificeringsdata kan överföras
keywords: Analysis Workspace
title: Konfigurera platser för molnimport
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: c43d7bbdad0ad0265e038ee273c74bec136f1c72
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---

# Konfigurera platser för molnimport

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Innan du kan importera Adobe Analytics-klassificeringsdata från ett molnmål måste du lägga till och konfigurera kontot och platsen inom det kontot där du vill att klassificeringsdata ska samlas in.

Den här processen består av att lägga till och konfigurera kontot (till exempel Amazon S3 Role ARN, Google Cloud Platform o.s.v.) och platsen inom kontot (till exempel en mapp i kontot).

Så här konfigurerar du en molnimportplats:

1. Du måste lägga till ett konto innan du kan lägga till en plats. Om du inte redan har det lägger du till ett konto enligt beskrivningen i [Konfigurera molnimportkonton](/help/components/locations/configure-import-accounts.md).
1. I Adobe Analytics: [!UICONTROL **Komponenter**] > [!UICONTROL **Platser**].
1. På [!UICONTROL Locations] väljer du [!UICONTROL **Platser**] -fliken.
1. Välj [!UICONTROL **Lägg till plats**]. <!-- add screenshot? -->

   Dialogrutan Plats visas.
1. Ange följande information: |Fält | Funktion | |—|—| | [!UICONTROL **Namn**] | Namnet på platsen.  | | [!UICONTROL **Beskrivning**] | Ange en kort beskrivning av kontot så att det kan särskiljas från andra konton av samma kontotyp. | | [!UICONTROL **Platskonto**] | Välj det platskonto som du skapade i [Lägg till ett konto](#add-an-account). |

1. I [!UICONTROL **Platsegenskaper**] anger du information som är specifik för kontotypen för ditt platskonto.

   För konfigurationsinstruktioner expanderar du det avsnitt nedan som motsvarar kontotypen som du valde i dialogrutan [!UICONTROL **Platskonton**] fält.

   +++Amazon S3 Roll ARN

   Ange följande information för att konfigurera en ARN-plats för en Amazon S3-roll:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Buckennamn**] | Den bucket på ditt Amazon S3-konto där du vill att Adobe Analytics-data ska skickas. |
   | [!UICONTROL **Nyckelprefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Ange följande information för att konfigurera en plats för Google Cloud-plattformen:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Buckennamn**] | Den bucket på ditt GCP-konto där du vill att Adobe Analytics-data ska skickas. Se till att du har gett Adobe tillåtelse att överföra filer till denna bucket till säkerhetsobjektet. |
   | [!UICONTROL **Nyckelprefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Ange följande information för att konfigurera en Azure SAS-plats:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Behållarnamn**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. |
   | [!UICONTROL **Nyckelprefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Ange följande information för att konfigurera en Azure RBAC-plats:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Behållarnamn**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. Se till att du ger behörighet att överföra filer till Azure-programmet som du skapade tidigare. |
   | [!UICONTROL **Nyckelprefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel, `folder_name/` |
   | [!UICONTROL **Kontonamn**] | Azure-lagringskontot. |

   {style="table-layout:auto"}

+++

1. Välj [!UICONTROL **Spara**].

   Nu kan du importera data till kontot och platsen som du konfigurerade.
