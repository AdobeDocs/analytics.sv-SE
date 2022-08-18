---
title: Skapa eller redigera en datafeed
description: Lär dig hur du skapar eller redigerar en datafeed.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 60335be9a60b467969f5e1796ce465a7d453951f
workflow-type: tm+mt
source-wordcount: '1514'
ht-degree: 0%

---

# Skapa eller redigera en datafeed

Genom att skapa en datafeed kan Adobe veta var rådatafiler ska skickas och vad du vill inkludera i varje fil. På den här sidan visas enskilda inställningar som du kan anpassa när du skapar en datafeed.

Grundläggande kunskap om dataflöden rekommenderas innan du läser den här sidan. Se [Översikt över dataflöden](data-feed-overview.md) för att säkerställa att du uppfyller kraven för att skapa en datafeed.

## Fält för matningsinformation

* **Namn**: Dataflödets namn. Måste vara unikt i den valda rapportsviten och får innehålla upp till 255 tecken.
* **Rapportsvit:** Rapportsviten som dataflödet baseras på. Om flera dataflöden skapas för samma rapportserie måste de ha olika kolumndefinitioner. Endast källrapportsviter stöder dataflöden. virtuella rapportsviter stöds inte.
* **E-post när slutförd**: E-postadressen som ska meddelas när en feed har bearbetats. E-postadressen måste vara korrekt formaterad.
* **Feedintervall**: Timmatningar innehåller en timmes data. Dagliga matningar innehåller en hel dags data. de innehåller data från midnatt till midnatt i rapportsvitens tidszon.
* **Fördröjd bearbetning**: Vänta en viss tid innan du bearbetar en datafeedfil. En fördröjning kan vara användbar för att ge mobila implementeringar möjlighet att komma online och skicka data på offlineenheter. Den kan också användas för att hantera serverprocesser i organisationen när tidigare bearbetade filer hanteras. I de flesta fall behövs ingen fördröjning. En feed kan fördröjas med upp till 120 minuter.
* **Start- och slutdatum**: Startdatumet anger det första datum då du vill ha en datafeed. Ange det här datumet i det förflutna för att omedelbart börja bearbeta dataflöden för historiska data. Bearbetningen av feeds fortsätter tills de når slutdatumet. Start- och slutdatumen baseras på rapportsvitens tidszon.
* **Kontinuerlig feed**: Den här kryssrutan tar bort slutdatumet, vilket gör att en feed kan köras på obestämd tid. När en feed har avslutat bearbetningen av historiska data väntar en feed på data för att slutföra insamlingen under en given timme eller dag. När den aktuella timmen eller dagen är slut börjar bearbetningen efter den angivna fördröjningen.

## Målfält

Vilka fält som är tillgängliga under målfält beror på måltypen.

### Google Cloud Platform

Få åtkomst till GCP-lagringsfack som en säker destination

**Fält**
* *Typ:* Måltyp för Google Cloud-plattformen
* *Projekt-ID:* GCP-projekt-ID där lagringspytsen finns
* *Lagringspytsens namn:* Buckennamn utan punkter får innehålla högst 3-63 tecken. Namn som innehåller punkter kan innehålla upp till 222 tecken, men varje punktavgränsad komponent kan inte vara längre än 63 tecken.
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras

![GCP-information](assets/dest-gcp.png)

**Processen för att skapa tjänstkonto**

Användaren måste skapa ett tjänstkonto för det Google Cloud Platform-mål som har valts.

Endast ett GCP-tjänstkonto tillåts per analysorganisation. När tjänstkontot har skapats för datafeeden fylls alla ytterligare dataflöden i organisationen i förväg med tjänstkontot.

![Information om GCP-tjänstkonto](assets/service-account.png)


### Amazon S3

Amazon S3-bucket-lagring som nås via IAM-roll i en betrodd enhet.

**Fält**

* *Typ:* Måltyp för Amazon S3
* *Bucket:* S3-bucketnamn
* *Betrodd entitet-ARN:* AWS IAM Entity ARN `arn:aws:iam::<12 digit account number>:user/<username>`
* *Roll-ARN:* AWS IAM Role ARN `arn:aws:iam::<12 digit account number>:role/<role name>`
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras
* *Ange region (valfritt):* Listruta över alla tillgängliga AWS-regioner, inklusive KN-regioner

![Information om Amazon S3](assets/dest-s3-secure.png)


**Skapa och markera betrodd enhet**

Användaren kan välja en betrodd enhet bland de alternativ som listas i listrutan eller skapa och hämta en ny genom att klicka på `Create Entity` -knappen.

När du klickat på `Create Entity` kommer användaren att omdirigeras till en autentiseringsprocess. När användaren autentiserar skapas den betrodda enheten och läggs till i alternativen i listrutan.

Listrutan innehåller alla betrodda enheter som har skapats i organisationen av den här användaren.

![Entitetsinformation](assets/entity-creation.png)

Du kan skicka feeds direkt till Amazon S3-bucket via den äldre metoden. Se [Krav för Amazon S3-bucket-namngivning](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) i Amazon S3-dokumenten för mer information.

**Fält - inaktuella**

* *Typ:* Måltyp för ersatt S3-metod
* *Bucket:* Amazon S3 Bucket-namn
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras
* *Åtkomstnyckel:* Åtkomstnyckel-ID för AWS-användare
* *Hemlig nyckel:* Hemlig nyckel för AWS-användare
* *Bekräfta hemlig nyckel:* Ange hemlig nyckel för AWS-användare igen

![S3-info](assets/dest-s3-dpr.png)

Användaren som du anger för överföring av datafeeds måste ha följande [behörigheter](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

För varje överföring till en Amazon S3-bucket [!DNL Analytics] lägger till bucket-ägaren till BucketOwnerFullControl ACL, oavsett om bucket har en princip som kräver det eller inte. Mer information finns i &quot;[Vad är inställningen BucketOwnerFullControl för Amazon S3-dataflöden?](df-faq.md#BucketOwnerFullControl)&quot;

**AWS-regioner som stöds**:
* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-Southern-1
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
* cn-nord-1
* cn-northwest-1


### Azure Blob

Säker Azure Blob-destination med rollbaserad åtkomstkontroll (RBAC) eller SAS (Shared Access Signature). När du väljer åtkomstkontrollen uppdateras innehållet på panelen så att motsvarande fält visas.

**Fält - RBAC**
* *Typ:* Måltyp för Azure-blob
* *Åtkomstkontroll:* Möjlighet att använda RBAC eller SAS
* *Klient-ID för Active Directory:* Organisations-ID för Azure-konto
* *Program-ID:* Program-ID från Active Directory Adapter
* *Klienthemlighet:* Azure Client Secret
* *Lagringskontonamn:* Namn på konto som innehåller dataobjekt
* *Behållarnamn:* Behållare som tillhör ett visst lagringskonto.
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras

![Azure RBAC-information](assets/dest-azure-rbac.png)

**Fält - SAS**
* *Typ:* Måltyp för Azure-blob
* *Åtkomstkontroll:* Möjlighet att använda RBAC eller SAS
* *Klient-ID för Active Directory:* ID för Azure Active Directory-instans
* *Program-ID:* Program-ID från Active Directory Adapter
* *Klienthemlighet:* Azure Client Secret
* *Key Vault URI:* Plats för Azure Key Vault
* *Nyckelvalvets hemliga namn:* Hemligt namn för åtkomst till säkert nyckelvalv
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras

![Azure SAS-information](assets/dest-azure-sas.png)

**Fält - inaktuella**
* *Typ:* Måltyp för Azure-blob
* *Behållare:* Azure-behållarens namn
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras
* *Konto:* Azure-kontohemlighet
* *Key Vault URI:* Plats för Azure Key Vault
* *Nyckelvalvets hemliga namn:* Hemligt namn för åtkomst till säkert nyckelvalv

Du måste implementera en egen process för att hantera diskutrymme på matningsmålet. Adobe tar inte bort några data från servern.
Se [Skapa ett lagringskonto](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) i Microsoft Azure-dokumenten för mer information.

![Azure-inaktuell information](assets/dest-azure-dpr.png)

>[!NOTE]
>
>Du måste implementera en egen process för att hantera diskutrymme på matningsmålet. Adobe tar inte bort några data från servern.

### FTP - inaktuellt

**Fält**
* *Typ:* FTP-måltyp
* *Värd:* Slutpunkt för åtkomst till värd
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras
* *Användarnamn:* Användarnamn för värd
* *Lösenord:* Lösenord för värd
* *Bekräfta lösenord:* Ange och verifiera lösenordet för värden igen

![FTP-information](assets/dest-ftp-dpr.png)

### SFTP - inaktuellt

SFTP-stöd för dataflöden finns tillgängligt. Kräver att en SFTP-värd, ett användarnamn och målplatsen innehåller en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar flödet.

**Fält**
* *Typ:* SFTP-måltyp
* *Värd:* Slutpunkt för åtkomst till värd
* *Sökväg (valfritt):* &amp; *Lägg till Report Suite-ID till sökväg:* Plats för resurser som ska hämtas eller lagras
* *Offentlig RSA-nyckel:* eller *Offentlig DSA-nyckel:* Offentlig nyckel för att få åtkomst till värden

![SFTP-information](assets/dest-sftp-dpr.png)

## Datakolumdefinitioner

Alla kolumner är tillgängliga, oavsett om de har data. En datafeed måste innehålla minst en kolumn.

* **Ta bort escape-tecken**: När du samlar in data kan vissa tecken (till exempel nya rader) orsaka problem. Markera den här rutan om du vill att dessa tecken ska tas bort från feed-filerna.
* **Komprimeringsformat**: Den typ av komprimering som används. Gzip skickar filer i `.tar.gz` format. Zip skriver ut filer i `.zip` format.
* **Förpackningstyp**: En fil ger `hit_data.tsv` i en enda, potentiellt enorm fil. Flera filer sidnumrerar data i 2 GB-segment (okomprimerade). Om flera filer är markerade och okomprimerade data för rapportfönstret är mindre än 2 GB, skickas en fil. Adobe rekommenderar att du använder flera filer för de flesta dataflöden.
* **Manifest**: Om Adobe ska leverera en [manifestfil](c-df-contents/datafeeds-contents.md#feed-manifest) till målet när inga data samlas in för ett feed-intervall. Om du väljer Manifest File får du en manifestfil som liknar följande när inga data samlas in:

```text
   Datafeed-Manifest-Version: 1.0
    Lookup-Files: 0
    Data-Files: 0
    Total-Records: 0
```

* **Kolumnmallar**: När du skapar många dataflöden rekommenderar Adobe att du skapar en kolumnmall. Om du väljer en kolumnmall inkluderas automatiskt de angivna kolumnerna i mallen. Adobe har också flera mallar som standard.
* **Tillgängliga kolumner**: Alla tillgängliga datakolumner i Adobe Analytics. Klicka [!UICONTROL Add all] om du vill ta med alla kolumner i en datafeed.
* **Inkluderade kolumner**: De kolumner som ska inkluderas i en datafeed. Klicka [!UICONTROL Remove all] om du vill ta bort alla kolumner från en datafeed.
* **Hämta CSV**: Hämtar en CSV-fil som innehåller alla inkluderade kolumner.
