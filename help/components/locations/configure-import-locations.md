---
description: Konfigurera molnimportkontot och platsen där klassificeringsdata kan överföras
keywords: Analysis Workspace
title: Konfigurera platser för molnimport och -export
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: de1aaf1cc4f59567582c7802117226e859e52b08
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 0%

---

# Konfigurera platser för molnimport och -export

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Du kan konfigurera ett molnkonto (och en plats för det kontot). En enda plats kan användas för något av följande ändamål (en enda plats kan inte kopplas till flera syften, t.ex. datafeeds och Data Warhouse, eller Datas Warehouse- och Klassificeringsuppsättningar):

* Exportera filer med [Dataflöden](/help/export/analytics-data-feed/create-feed.md)
* Exportera rapporter med [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importera scheman med [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md)

Du måste konfigurera Adobe Analytics med den information som krävs för att komma åt ditt molnkonto. Den här processen består av att lägga till och konfigurera kontot (som Amazon S3 Role ARN, Google Cloud Platform o.s.v.) enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md)och sedan lägga till och konfigurera platsen inom det kontot (enligt beskrivningen i den här artikeln).

Så här konfigurerar du en ny import- eller exportplats i molnet eller redigerar en befintlig plats:

1. I Adobe Analytics: [!UICONTROL **Komponenter**] > [!UICONTROL **Platser**].
1. På [!UICONTROL Locations] väljer du [!UICONTROL **Platser**] -fliken.
1. Om du vill skapa en ny plats väljer du [!UICONTROL **Lägg till plats**]. (Om du inte redan har lagt till ett konto lägger du till ett enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md).)

   eller

   Om du vill redigera en befintlig plats väljer du menyn med tre punkter på panelen [!UICONTROL **Platsnamn**] kolumn för platsen som du vill redigera och markera [!UICONTROL **Redigera**].
Dialogrutan Plats visas.

1. Ange följande information: |Fält | Funktion | |—|—| | [!UICONTROL **Namn**] | Namnet på platsen.  | | [!UICONTROL **Beskrivning**] | Ange en kort beskrivning av kontot för att hjälpa till att skilja det från andra konton av samma kontotyp. | | [!UICONTROL **Använd med**] | Välj om du vill använda den här platsen med [!UICONTROL **Dataflöden**], [!UICONTROL **Data Warehouse**], eller [!UICONTROL **Klassificeringsuppsättningar**]. <p>Tänk på följande när du gör en markering:</p><ul><li>En enda plats kan inte användas för flera syften. En plats som till exempel används för datafeeds kan inte också användas för Data Warehouse- eller klassificeringsuppsättningar.</li><li>Om du vill undvika filkonflikter på en plats ska du inte ändra värdet på [!UICONTROL **Använd med**] efter att platsen har använts.</li></ul> | | [!UICONTROL **Platskonto**] | Välj det platskonto där du vill skapa den här platsen. Mer information om hur du skapar ett konto finns i [Lägg till ett konto](#add-an-account). |

1. I [!UICONTROL **Platsegenskaper**] anger du information som är specifik för kontotypen för ditt platskonto.

   För konfigurationsinstruktioner expanderar du det avsnitt nedan som motsvarar kontotypen som du valde i dialogrutan [!UICONTROL **Platskonton**] fält. (Ytterligare äldre kontotyper är också tillgängliga, men rekommenderas inte.)

   **Kontotyper**

   +++Amazon S3 Roll ARN

   Ange följande information om du vill konfigurera en ARN-plats för en Amazon S3-roll:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Buckennamn**] | Den bucket på ditt Amazon S3-konto där du vill att Adobe Analytics-data ska skickas. <p>Se till att användar-ARN som tillhandahålls av Adobe har `S3:PutObject` behörighet för att överföra filer till denna bucket. </p><p>Bucket-namn måste uppfylla specifika namnregler. De måste till exempel innehålla mellan 3 och 63 tecken, får endast bestå av gemener, siffror, punkter (.) och bindestreck (-) och måste börja och sluta med en bokstav eller en siffra. [En fullständig lista över namnregler finns i AWS-dokumentationen](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Nyckelprefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Ange följande information om du vill konfigurera en plats för Google Cloud-plattformen:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Buckennamn**] | Den bucket på ditt GCP-konto där du vill att Adobe Analytics-data ska skickas. Se till att du har gett Adobe tillåtelse att överföra filer till denna bucket till säkerhetsobjektet. |
   | [!UICONTROL **Nyckelprefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Om du vill konfigurera en Azure SAS-plats anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Behållarnamn**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. |
   | [!UICONTROL **Nyckelprefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Om du vill konfigurera en Azure RBAC-plats anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Behållarnamn**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. Se till att du ger behörighet att överföra filer till Azure-programmet som du skapade tidigare. |
   | [!UICONTROL **Nyckelprefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/` |
   | [!UICONTROL **Kontonamn**] | Azure-lagringskontot. |

   {style="table-layout:auto"}

+++

   **Äldre kontotyper**

   De här äldre kontotyperna är bara tillgängliga när du exporterar data med [Dataflöden](/help/export/analytics-data-feed/create-feed.md) och [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Dessa alternativ är inte tillgängliga vid import av data med [Klassificeringsuppsättningar](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   Data från dataflöden kan levereras till en FTP-plats som är värd för Adobe eller kunder. Ange katalogen Använd sökvägsfältet för att placera feed-filer i en mapp.

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Katalogsökväg**] | Ange sökvägen till katalogen på FTP-servern. Mappar måste redan finnas. Flöden genererar ett fel om den angivna sökvägen inte finns. </br>Till exempel: `/folder_name/folder_name`. |

   {style="table-layout:auto"}

+++

   +++SFTP

   Data från dataflödet kan levereras till en SFTP-plats som är värd för Adobe eller kund. Målplatsen måste innehålla en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar flödet.

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Katalogsökväg**] | Ange sökvägen till katalogen på FTP-servern. Mappar måste redan finnas. Flöden genererar ett fel om den angivna sökvägen inte finns. </br>Till exempel: `/folder_name/folder_name`. |

   {style="table-layout:auto"}

+++

   +++S3

   Du kan skicka lagerdata direkt till Amazon S3-butiker. Den här måltypen kräver ett Bucket-namn, ett Access Key ID och en Secret Key. Se [Krav för Amazon S3-bucket](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) i Amazon S3-dokumenten för mer information.

   Användaren som du anger för överföring av datalagerdata måste ha följande [behörigheter](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

   * s3:GetObject
   * s3:PutObject
   * s3:PutObjectAcl

   Följande 16 AWS-standardregioner stöds (med lämplig signaturalgoritm där det behövs):

   * us-east-2
   * us-east-1
   * us-west-1
   * us-west-2
   * ap-soud-1
   * ap-northeast-2
   * ap-southeast-1
   * ap-southeast-2
   * ap-northeast-1
   * ca-central-1
   * eu-central-1
   * eu-west-1
   * eu-west-2
   * eu-west-3
   * eu-nord-1
   * sa-east-1

   >[!NOTE]
   >
   >Regionen cn-North-1 stöds inte.

+++

   +++Azure Blob

   Datalagret stöder Azure Blob-mål. Kräver en behållare, ett konto och en nyckel. Amazon krypterar automatiskt vilande data. När du hämtar data dekrypteras de automatiskt. Se [Skapa ett lagringskonto](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) i Microsoft Azure-dokumenten om du vill ha mer information.

   >[!NOTE]
   >
   >Du måste implementera en egen process för att hantera diskutrymme på datalagermålet. Adobe tar inte bort några data från servern.

+++

1. Välj [!UICONTROL **Spara**].

   Du kan nu importera eller exportera data till eller från kontot och platsen som du konfigurerade.

   Importerade data tas inte bort från molnmålet när de har importerats.

   >[!NOTE]
   >
   >   Om du tidigare använt [FTP för att importera klassificeringar](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) till Adobe Analytics måste du överföra en FIN-fil. Den här FIN-filen behövs inte vid import från molnkonton.

