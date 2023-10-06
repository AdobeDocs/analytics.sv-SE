---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera ett rapportmål för en Data Warehouse-begäran
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: f1264344a380944946ffa7b427db7bbc3ea96b1f
workflow-type: tm+mt
source-wordcount: '2252'
ht-degree: 0%

---

# Konfigurera ett rapportmål för en Data Warehouse-begäran

>[!AVAILABILITY]
>
>Vissa av de Data Warehouse som beskrivs i den här artikeln (och andra artiklar i den här Datan Warehouse) är endast tillgängliga i den begränsade testfasen av releasen och är kanske inte tillgängliga i din miljö ännu.
>
>Information om vilka funktioner som ännu inte är tillgängliga för alla kunder, samt information om tidslinjen för releasen av dessa funktioner, finns i [versionsinformation](/help/release-notes/latest.md).
>
>Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar ett rapportmål för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Tänk på följande när du konfigurerar ett rapportmål:
>
>* Vi rekommenderar att du använder ett molnkonto eller ett e-postmeddelande för rapportdestinationen. Äldre FTP- och SFTP-konton är tillgängliga, men rekommenderas inte.
>
>* Molnkonton är kopplade till ditt Adobe Analytics-användarkonto. Andra användare kan inte använda eller visa molnkonton som du konfigurerar.
>
>* Alla molnkonton som du tidigare använt [konfigurerad för dataflöden](/help/export/analytics-data-feed/create-feed.md) är tillgängliga för Data Warehouse.
>
>* Molnkonton som är konfigurerade för [importera Adobe Analytics klassificeringsdata](/help/components/locations/locations-manager.md) från ett molnmål kan användas när du konfigurerar ett rapportmål. Eventuella platser som har konfigurerats för import av klassificeringsdata kan dock inte användas.

Så här konfigurerar du målet dit Data Warehouse-rapporter skickas:

1. Börja skapa en begäran i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. På sidan Ny Data Warehouse väljer du [!UICONTROL **Rapportdestination**] -fliken.

   ![Målflik för rapport](assets/dw-report-destination.png)

1. (Villkorligt) Om du tidigare har konfigurerat ett konto (och ett mål för det kontot) som du vill använda som rapportmål:

   1. Välj konto på [!UICONTROL **Välj konto**] listruta.

      Alla molnkonton som du har konfigurerat för [importera Adobe Analytics klassificeringsdata](/help/components/locations/locations-manager.md) från ett molnmål visas här och kan användas. Eventuella platser som har konfigurerats för import av klassificeringsdata kan dock inte användas. Lägg i stället till ett nytt mål enligt beskrivningen nedan.

   1. Välj det mål som är associerat med kontot på menyn [!UICONTROL **Välj mål**] listruta. <!-- Is this correct? -->

1. (Villkorligt) Om du inte tidigare har konfigurerat ett konto:

   1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Kontotyp**] | Välj typ av molnkonto. Vi rekommenderar att du har ett enda konto för varje kontotyp, med flera platser efter behov inom det kontot. <p>När du har valt en kontotyp visas fält som är specifika för den kontotypen. </p> |
      | [!UICONTROL **Kontonamn**] | Ange ett namn för kontot. Det här namnet visas när du skapar en plats. <!-- true? --> |
      | [!UICONTROL **Kontobeskrivning**] | Ange en kort beskrivning av kontot för att hjälpa till att skilja det från andra konton av samma kontotyp. |

      Utöka det avsnitt nedan som motsvarar [!UICONTROL **Kontotyp**] som du valde.

      Använd någon av följande kontotyper när du konfigurerar ett rapportmål. Expandera kontotypen om du vill ha konfigurationsinstruktioner. (Ytterligare [äldre destinationer](#legacy-destinations) finns också tillgängliga, men rekommenderas inte.)

      +++Amazon S3

      Ange följande information för att konfigurera ett Amazon S3 Role ARN-konto:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Roll-ARN**] | Du måste ange en roll-ARN (Amazon Resource Name) som Adobe kan använda för att få åtkomst till Amazon S3-kontot. För att göra detta skapar du en IAM-behörighetsprincip för källkontot, kopplar principen till en användare och skapar sedan en roll för målkontot. Mer information finns i [den här AWS-dokumentationen](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
      | [!UICONTROL **Användar-ARN**] | Användar-ARN (Amazon Resource Name) tillhandahålls av Adobe. Du måste koppla den här användaren till den princip du skapade. |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Ange följande information för att konfigurera ett Google Cloud Platform-konto:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Projekt-ID**] | Ditt projekt-ID för Google Cloud. Se [Google Cloud-dokumentation om hur du får ett projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Ange följande information för att konfigurera ett Azure SAS-konto:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI för nyckelvalv**] | <p>Sökvägen till SAS-token i Azure Key Vault.  Om du vill konfigurera Azure SAS måste du lagra en SAS-token som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI:n har skapats lägger du till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade. Mer information finns i [Microsoft Azure-dokumentation om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på **Key Vault** inställningssidor. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Hemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Ange följande information för att konfigurera ett Azure RBAC-konto:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Hemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++E-post

      Ange följande information för att konfigurera ett e-postkonto:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Mottagare**] | E-postmeddelanden kan skickas till specifika användare när rapporten skickas. Ange en e-postadress eller en kommaavgränsad lista med e-postadresser. <!-- How does this differ from the Notification email tab? --> |

   1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information: |Fält | Funktion | |—|—| | [!UICONTROL **Namn**] | Namnet på platsen.  | | [!UICONTROL **Beskrivning**] | Ange en kort beskrivning av kontot så att det kan särskiljas från andra konton av samma kontotyp. | | [!UICONTROL **Platskonto**] | Välj det platskonto som du skapade i [Lägg till ett konto](#add-an-account). |

   1. I [!UICONTROL **Platsegenskaper**] anger du information som är specifik för kontotypen för ditt platskonto.

      Utöka det avsnitt nedan som motsvarar [!UICONTROL **Kontotyp**] som du valde tidigare.

      +++Amazon S3

      Ange följande information för att konfigurera en Amazon S3-plats:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Buckennamn**] | Den bucket på ditt Amazon S3-konto där du vill att Adobe Analytics-data ska skickas. Se till att användar-ARN som tillhandahålls av Adobe har åtkomst till att överföra filer till den här bucket. |
      | [!UICONTROL **Nyckelprefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Ange följande information för att konfigurera en plats för Google Cloud-plattformen:

      | Fält |  -funktion |
      |---------|----------|
      | [!UICONTROL **Buckennamn**] | Den bucket på ditt GCP-konto där du vill att Adobe Analytics-data ska skickas. Se till att du har gett Adobe tillåtelse att överföra filer till denna bucket till säkerhetsobjektet. Mer information om att bevilja behörigheter finns i [Lägga till ett huvudnamn i en princip på paketnivå](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) i Google Cloud-dokumentationen. |
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

1. Fortsätt konfigurera din Data Warehouse-förfrågan på [!UICONTROL **Rapportalternativ**] -fliken. Mer information finns i [Konfigurera rapportalternativ för en Data Warehouse-förfrågan](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Äldre destinationer

>[!IMPORTANT]
>
>Destinationerna som beskrivs i det här avsnittet är äldre och rekommenderas inte. Använd i stället ett av följande mål när du skapar ett datalagermål: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS eller Email. Se informationen ovan för mer information om var och en av dessa rekommenderade destinationer.

Följande information innehåller konfigurationsinformation för var och en av de äldre målplatserna:

### FTP

Data dist.lagerdata kan levereras till en FTP-plats som är värd för Adobe eller kund. Kräver FTP-värd, användarnamn och lösenord. Använd sökvägsfältet för att placera feed-filer i en mapp. Mappar måste redan finnas. Flöden genererar ett fel om den angivna sökvägen inte finns.

Använd följande information när du fyller i de tillgängliga fälten:

#### Kontofält

* [!UICONTROL **Kontonamn**]: Namnet på FTP-kontot.

* [!UICONTROL **Kontobeskrivning**]: En beskrivning av FTP-kontot.

* [!UICONTROL **Värdnamn**]: Ange önskad mål-URL för FTP. Exempel, `ftp.company.com`.

  >[!NOTE]
  >
  >  Inkludera inte `ftp://` i början av URL:en.

* [!UICONTROL **Användarnamn**]: Ange användarnamn för att logga in på FTP-platsen.

* [!UICONTROL **Lösenord och bekräfta lösenord**]: Ange lösenordet för att logga in på FTP-platsen.

#### Platsfält

* [!UICONTROL **Platsnamn**]: Namnet på den plats på FTP-kontot där du vill att filer ska skickas.

* [!UICONTROL **Platsbeskrivning**]: En beskrivning av platsen på FTP-kontot.

* [!UICONTROL **Katalogsökväg**]: Sökvägen till platsen på FTP-kontot.

### SFTP

SFTP-stöd för datalager är tillgängligt. Kräver att en SFTP-värd, ett användarnamn och målplatsen innehåller en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar datalagrets mål.

Använd följande information när du fyller i de tillgängliga fälten:

#### Kontofält

* [!UICONTROL **Kontonamn**]: Namnet på FTP-kontot.

* [!UICONTROL **Kontobeskrivning**]: En beskrivning av FTP-kontot.

* [!UICONTROL **Värdnamn**]: Ange önskad mål-URL för SFTP. Exempel, `sftp.company.com`.

  >[!NOTE]
  >
  >  Inkludera inte `sftp://` i början av URL:en.

* [!UICONTROL **Användarnamn**]: Ange användarnamn för att logga in på SFTP-platsen.

* [!UICONTROL **Offentliga nycklar**]: Hämta lämplig offentlig nyckel när du skapar datalagermålet.

#### Platsfält

* [!UICONTROL **Platsnamn**]: Namnet på den plats på SFTP-kontot där du vill att filer ska skickas.

* [!UICONTROL **Platsbeskrivning**]: En beskrivning av platsen på SFTP-kontot.

* [!UICONTROL **Katalogsökväg**]: Sökvägen till platsen på SFTP-kontot.

### S3

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

### Azure Blob

Datalagret stöder Azure Blob-mål. Kräver en behållare, ett konto och en nyckel. Amazon krypterar automatiskt vilande data. När du hämtar data dekrypteras de automatiskt. Se [Skapa ett lagringskonto](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) i Microsoft Azure-dokumenten om du vill ha mer information.

>[!NOTE]
>
>Du måste implementera en egen process för att hantera diskutrymme på datalagermålet. Adobe tar inte bort några data från servern.
