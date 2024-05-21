---
description: Konfigurera molnimportkontot och platsen där klassificeringsdata kan överföras
keywords: Analysis Workspace
title: Konfigurera molnimport- och exportkonton
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: 66c846dd64ee3ed8f421c834ab82b53b1f0f00a5
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 0%

---

# Konfigurera molnimport- och exportkonton

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Du kan konfigurera ett molnkonto som används för något eller alla av följande syften:

* Exportera filer med [Dataflöden](/help/export/analytics-data-feed/create-feed.md)
* Exportera rapporter med [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importera scheman med [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md)

Du måste konfigurera Adobe Analytics med den information som krävs för att komma åt ditt molnkonto. Den här processen består av att lägga till och konfigurera kontot (till exempel Amazon S3 Role ARN, Google Cloud Platform o.s.v.) enligt beskrivningen i den här artikeln, och sedan lägga till och konfigurera platsen inom det kontot (till exempel en mapp inom kontot) enligt beskrivningen i [Konfigurera platser för molnimport och -export](/help/components/locations/configure-import-locations.md).

Mer information om hur du hanterar befintliga konton, inklusive visning, redigering och borttagning av konton, finns i [Platshanteraren](/help/components/locations/locations-manager.md).

Så här konfigurerar du ett molnimport- eller exportkonto:

1. I Adobe Analytics: [!UICONTROL **Komponenter**] > [!UICONTROL **Platser**].
1. På [!UICONTROL Locations] väljer du [!UICONTROL **Platskonton**] -fliken.
1. Välj [!UICONTROL **Lägg till konto**].

   Dialogrutan Lägg till konto visas.

1. Ange följande information: |Fält | Funktion | |—|—| | [!UICONTROL **Platskontonamn**] | Namnet på platskontot. Det här namnet visas när du skapar en plats | | [!UICONTROL **Beskrivning av platskonto**] | Ange en kort beskrivning av kontot för att hjälpa till att skilja det från andra konton av samma kontotyp. | | [!UICONTROL **Kontotyp**] | Välj typ av molnkonto. Vi rekommenderar att du har ett enda konto för varje kontotyp, med flera platser efter behov inom det kontot. |
1. I [!UICONTROL **Kontoegenskaper**] anger du information som är specifik för den kontotyp som du har valt.

   Utöka det avsnitt nedan som motsvarar [!UICONTROL **Kontotyp**] som du valde. (Ytterligare äldre kontotyper är också tillgängliga, men rekommenderas inte.)

   **Kontotyper**

   +++Amazon S3 Roll ARN

   Om du vill konfigurera ett Amazon S3 Role ARN-konto anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Roll-ARN**] | Du måste ange en roll-ARN (Amazon Resource Name) som Adobe kan använda för att få åtkomst till Amazon S3-kontot. För att göra detta skapar du en IAM-behörighetsprincip för källkontot, kopplar principen till en användare och skapar sedan en roll för målkontot. Mer information finns i [den här AWS-dokumentationen](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Om du vill konfigurera ett Google Cloud Platform-konto anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Projekt-ID**] | Ditt projekt-ID för Google Cloud. Se [Google Cloud-dokumentation om hur du får ett projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Om du vill konfigurera ett Azure SAS-konto anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI för nyckelvalv**] | <p>Sökvägen till SAS-token i Azure Key Vault.  Om du vill konfigurera Azure SAS måste du lagra en SAS-token som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI:n har skapats lägger du till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade. Mer information finns i [Microsoft Azure-dokumentation om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn som du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på **Key Vault** inställningssida. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Om du vill konfigurera ett Azure RBAC-konto anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   **Äldre kontotyper**

   De här äldre kontotyperna är bara tillgängliga när du exporterar data med [Dataflöden](/help/export/analytics-data-feed/create-feed.md) och [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Dessa alternativ är inte tillgängliga vid import av data med [Klassificeringsuppsättningar](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   Data från dataflöden kan levereras till en FTP-plats som är värd för Adobe eller kunder. Kräver FTP-värd, användarnamn och lösenord. Använd sökvägsfältet för att placera feed-filer i en mapp. Mappar måste redan finnas. Flöden genererar ett fel om den angivna sökvägen inte finns.

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Värd**] | Ange önskad mål-URL för FTP. Till exempel: `ftp://ftp.omniture.com`. |
   | [!UICONTROL **Bana**] | Kan lämnas tomt. |
   | [!UICONTROL **Användarnamn**] | Ange användarnamnet för att logga in på FTP-platsen. |
   | [!UICONTROL **Lösenord och bekräfta lösenord**] | Ange lösenordet för att logga in på FTP-platsen. |

   {style="table-layout:auto"}

+++

   +++SFTP

   SFTP-stöd för dataflöden finns tillgängligt. Kräver att en SFTP-värd, ett användarnamn och målplatsen innehåller en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar flödet.

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

1. Fortsätt med [Konfigurera platser för molnimport och -export](/help/components/locations/configure-import-locations.md).
