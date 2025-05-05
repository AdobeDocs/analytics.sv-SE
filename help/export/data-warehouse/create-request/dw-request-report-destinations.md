---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera ett rapportmål för en Data Warehouse-begäran
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: d213befd0fd8d530d95b8d3ac3c4f3b808558244
workflow-type: tm+mt
source-wordcount: '1967'
ht-degree: 0%

---

# Konfigurera ett rapportmål för en Data Warehouse-begäran

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar ett rapportmål för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Tänk på följande när du konfigurerar ett rapportmål:
>
>* Vi rekommenderar att du använder ett molnkonto eller ett e-postmeddelande för rapportdestinationen. [Äldre FTP- och SFTP-konton](#legacy-destinations) är tillgängliga, men rekommenderas inte.
>
>* Alla molnkonton som du tidigare konfigurerat är tillgängliga för Data Warehouse. Du kan konfigurera molnkonton på något av följande sätt:
>
>   * När [datafeeds](/help/export/analytics-data-feed/create-feed.md) konfigureras
>   
>   * När [Adobe Analytics importerar klassificeringsdata](/help/components/locations/locations-manager.md) (konton kan användas, men det går inte att konfigurera platser för dessa konton.)
>   
>   * Från platshanteraren i [Komponenter > Platser](/help/components/locations/configure-import-accounts.md).
>
>* Molnkonton är kopplade till ditt Adobe Analytics-användarkonto. Andra användare kan inte använda eller visa molnkonton som du konfigurerar.
>
>* Du kan redigera alla platser som du skapar från platshanteraren i [Komponenter > Platser](/help/components/locations/configure-import-accounts.md)

Så här konfigurerar du målet dit Data Warehouse-rapporter skickas:

1. Om du inte redan har gjort det börjar du skapa en begäran i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Markera fliken [!UICONTROL **Rapportmål**] på sidan Ny Data Warehouse.

   ![Fliken Rapportmål](assets/dw-report-destination.png)

1. (Villkorligt) Om ett molnkonto (och ett mål för det kontot) redan har konfigurerats i Adobe Analytics kan du använda det som rapportmål:

   >[!NOTE]
   >
   >Konton är bara tillgängliga för dig om du har konfigurerat dem eller om de delats med en organisation som du är en del av.
   >
   >Om du är systemadministratör är alternativet [!UICONTROL **Visa alla mål**] tillgängligt. Aktivera det här alternativet om du vill ha åtkomst till alla konton och platser som har skapats av någon användare i organisationen.

   1. Välj kontot i den nedrullningsbara menyn [!UICONTROL **Konto**].

      Alla molnkonton som du har konfigurerat i något av följande områden i Adobe Analytics kan användas:

      * Vid import av Adobe Analytics-klassificeringsdata, enligt beskrivningen i [Schema](/help/components/classifications/sets/manage/schema.md).

        Eventuella platser som har konfigurerats för import av klassificeringsdata kan dock inte användas. Lägg i stället till ett nytt mål enligt beskrivningen nedan.

      * När konton och platser konfigureras i området Platser, enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md).

   1. Välj det mål som är associerat med kontot i listrutan [!UICONTROL **Välj mål**]. <!-- Is this correct? -->

1. (Villkorligt) Om du inte har tillgång till ett molnkonto som redan är konfigurerat i Adobe Analytics kan du konfigurera ett:

   1. Välj den nedrullningsbara menyn [!UICONTROL **Konto**] och välj sedan [!UICONTROL **Lägg till konto**].

   1. Ange följande information i dialogrutan Lägg till konto:

      | Fält | Funktion |
      |---------|----------|
      | [!UICONTROL **Platskontonamn**] | Namnet på platskontot. Det här namnet visas när du skapar en plats |
      | [!UICONTROL **Beskrivning av platskonto**] | Ange en kort beskrivning av kontot för att hjälpa till att skilja det från andra konton av samma kontotyp. |
      | [!UICONTROL **Gör kontot tillgängligt för alla användare i organisationen**] | Aktivera det här alternativet om du vill tillåta andra användare i organisationen att använda kontot.<p>Tänk på följande när du delar konton:</p><ul><li>Konton som du delar kan inte tas bort.</li><li>Delade konton kan bara redigeras av kontoägaren.</li><li>Vem som helst kan skapa en plats för det delade kontot.</li></ul> |
      | [!UICONTROL **Kontotyp**] | Välj typ av molnkonto. Vi rekommenderar att du har ett enda konto för varje kontotyp, med flera platser efter behov inom det kontot.<p>Systemadministratörer kan begränsa vilka kontotyper användare kan skapa, enligt beskrivningen i [Konfigurera om användare kan skapa konton](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Kontakta systemadministratören om du inte kan skapa konton enligt beskrivningen i det här avsnittet.</p> |

   1. I avsnittet [!UICONTROL **Kontoegenskaper**] anger du information som är specifik för den kontotyp som du har valt.

      Utöka det avsnitt nedan som motsvarar den [!UICONTROL **kontotyp**] som du har valt för konfigurationsinstruktioner. (Ytterligare äldre kontotyper är också tillgängliga, men rekommenderas inte.)

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
      | [!UICONTROL **Projekt-ID**] | Ditt projekt-ID för Google Cloud. Se [Google Cloud-dokumentationen om hur du hämtar ett projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

      +++

      +++Azure SAS

      Om du vill konfigurera ett Azure SAS-konto anger du följande information:

      | Fält | Funktion |
      |---------|----------|
      | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Nyckelvalvs-URI**] | <p>Sökvägen till SAS-token i Azure Key Vault.  Om du vill konfigurera Azure SAS måste du lagra en SAS-token som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentationen om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI:n har skapats lägger du till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade. Mer information finns i [Microsoft Azure-dokumentationen om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>eller</p><p>Om du vill tilldela en åtkomstroll direkt utan att skapa en åtkomstprincip läser du [Microsoft Azure-dokumentationen om hur du tilldelar Azure-roller med Azure-portalen](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Detta lägger till rolltilldelningen för program-ID:t för åtkomst till nyckelvalvs-URI:n. </p> |
      | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn som du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på inställningssidan för **nyckelvalv**. Mer information finns i [Microsoft Azure-dokumentationen om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Platskontohemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på fliken **Certifikat och hemligheter** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

      +++

      +++Azure RBAC

      Om du vill konfigurera ett Azure RBAC-konto anger du följande information:

      | Fält | Funktion |
      |---------|----------|
      | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Platskontohemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på fliken **Certifikat och hemligheter** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

      +++

      +++E-post

      >[!NOTE]
      >
      >E-postkonton kan bara användas med [datafeeds](/help/export/analytics-data-feed/create-feed.md). (E-postkonton stöds inte med [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) eller [klassificeringsuppsättningar](/help/components/classifications/sets/overview.md)).

      Om du vill konfigurera ett Azure RBAC-konto anger du följande information:

      | Fält | Funktion |
      |---------|----------|
      | [!UICONTROL **Mottagare**] | E-postmeddelanden kan skickas till specifika användare när rapporten skickas. Ange en e-postadress eller en kommaavgränsad lista med e-postadresser. |

      {style="table-layout:auto"}

      +++

1. Fortsätt konfigurera din Data Warehouse-förfrågan på fliken [!UICONTROL **Rapportalternativ**]. Mer information finns i [Konfigurera rapportalternativ för en Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Äldre kontotyper

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

* [!UICONTROL **Värdnamn**]: Ange önskad mål-URL för FTP. Exempel: `ftp.company.com`.

  >[!NOTE]
  >
  >  Ta inte med `ftp://` i början av URL:en.

* [!UICONTROL **Användarnamn**]: Ange användarnamnet för att logga in på FTP-platsen.

* [!UICONTROL **Lösenord och bekräfta lösenord**]: Ange lösenordet för att logga in på FTP-platsen.

#### Platsfält

* [!UICONTROL **Platsnamn**]: Namnet på platsen på FTP-kontot där du vill att filer ska skickas.

* [!UICONTROL **Platsbeskrivning**]: En beskrivning av platsen på FTP-kontot.

* [!UICONTROL **Katalogsökväg**]: Sökvägen till platsen på FTP-kontot.

### SFTP

SFTP-stöd för datalager är tillgängligt. Kräver att en SFTP-värd, ett användarnamn och målplatsen innehåller en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar datalagrets mål.

Använd följande information när du fyller i de tillgängliga fälten:

#### Kontofält

* [!UICONTROL **Kontonamn**]: Namnet på FTP-kontot.

* [!UICONTROL **Kontobeskrivning**]: En beskrivning av FTP-kontot.

* [!UICONTROL **Värdnamn**]: Ange önskad mål-URL för SFTP. Exempel: `sftp.company.com`.

  >[!NOTE]
  >
  >  Ta inte med `sftp://` i början av URL:en.

* [!UICONTROL **Användarnamn**]: Ange användarnamnet för att logga in på SFTP-platsen.

* [!UICONTROL **Använd tillfälliga filtillägg under överföring**]: När det här alternativet är aktiverat används filtillägget `.part` under överföringen. Låt alternativet vara aktiverat om inte SFTP-servern begränsar filnamnen från att ändras när överföringen är klar.

* [!UICONTROL **Offentliga nycklar**]: Hämta lämplig offentlig nyckel när datalagrets mål skapas.

#### Platsfält

* [!UICONTROL **Platsnamn**]: Namnet på platsen på SFTP-kontot där du vill att filer ska skickas.

* [!UICONTROL **Platsbeskrivning**]: En beskrivning av platsen på SFTP-kontot.

* [!UICONTROL **Katalogsökväg**]: Sökvägen till platsen på SFTP-kontot.

Mer information om SFTP-konfiguration finns i [Skicka Data Warehouse-begäranden till SFTP-servrar](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

Du kan skicka lagerdata direkt till Amazon S3-butiker. Den här måltypen kräver ett Bucket-namn, ett Access Key ID och en Secret Key. Mer information finns i [Namngivningskrav för Amazon S3-bucket](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) i Amazon S3-dokumenten.

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

Datalagret stöder Azure Blob-mål. Kräver en behållare, ett konto och en nyckel. Amazon krypterar automatiskt vilande data. När du hämtar data dekrypteras de automatiskt. Mer information finns i [Skapa ett lagringskonto](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) i Microsoft Azure-dokumenten.

>[!NOTE]
>
>Du måste implementera en egen process för att hantera diskutrymme på datalagermålet. Adobe tar inte bort några data från servern.
