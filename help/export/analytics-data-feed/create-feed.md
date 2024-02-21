---
title: Skapa en datafeed
description: Lär dig hur du skapar en datafeed.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 9fbe0f8a7933e5ff047a270523ea53d9489b223c
workflow-type: tm+mt
source-wordcount: '3344'
ht-degree: 0%

---

# Skapa en datafeed

När du skapar en datafeed kan du ge Adobe:

* Information om målet dit du vill skicka rådatafiler

* De data som du vill inkludera i varje fil

>[!NOTE]
>
>Innan du skapar en datafeed är det viktigt att du har en grundläggande förståelse för dataflöden och att du uppfyller alla nödvändiga krav. Mer information finns i [Översikt över dataflöden](data-feed-overview.md).

## Skapa och konfigurera en datafeed

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Markera ikonen med nio kvadrater i det övre högra hörnet och välj sedan [!UICONTROL **Analyser**].
1. I det övre navigeringsfältet går du till [!UICONTROL **Administratör**] > [!UICONTROL **Dataflöden**].
1. Välj [!UICONTROL **Lägg till**].

   ![Lägg till datafeed](assets/datafeed-add.png)

   En sida visas med tre huvudkategorier: [!UICONTROL **Feedinformation**], [!UICONTROL **Mål**] och [!UICONTROL **Datakolumdefinitioner**].
1. I [!UICONTROL **Feedinformation**] fyller du i följande fält:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Namn**] | Dataflödets namn. Måste vara unikt i den valda rapportsviten och får innehålla upp till 255 tecken. |
   | [!UICONTROL **Rapportsvit**] | Rapportsviten som dataflödet baseras på. Om flera dataflöden skapas för samma rapportserie måste de ha olika kolumndefinitioner. Endast källrapportsviter stöder dataflöden. Virtuella rapportsviter stöds inte. |
   | [!UICONTROL **E-post när slutförd**] | E-postadressen som ska meddelas när en feed har bearbetats. E-postadressen måste vara korrekt formaterad. |
   | [!UICONTROL **Feedintervall**] | Välj **Dagligen** för bakåtfyllnad eller historiska data. Dagliga matningar innehåller data för en hel dag, från midnatt till midnatt i rapportsvitens tidszon.  Välj **Varje timme** för att fortsätta med data (Daily finns också tillgängligt för att fortsätta feeds om du vill). Timmatningar innehåller en timmes data. |
   | [!UICONTROL **Fördröjd bearbetning**] | Vänta en viss tid innan du bearbetar en datafeedfil. En fördröjning kan vara användbar för att ge mobila implementeringar möjlighet att komma online och skicka data på offlineenheter. Den kan också användas för att hantera serverprocesser i organisationen när tidigare bearbetade filer hanteras. I de flesta fall behövs ingen fördröjning. En feed kan fördröjas med upp till 120 minuter. |
   | [!UICONTROL **Start- och slutdatum**] | Startdatumet anger det datum då du vill att dataflödet ska börja. Om du omedelbart vill börja bearbeta dataflöden för historiska data anger du det här datumet till ett tidigare datum när data samlas in. Start- och slutdatumen baseras på rapportsvitens tidszon. |
   | [!UICONTROL **Kontinuerlig feed**] | Den här kryssrutan tar bort slutdatumet, vilket gör att en feed kan köras på obestämd tid. När en feed har avslutat bearbetningen av historiska data väntar en feed på data för att slutföra insamlingen under en given timme eller dag. När den aktuella timmen eller dagen är slut börjar bearbetningen efter den angivna fördröjningen. |

1. I [!UICONTROL **Mål**] i [!UICONTROL **Typ**] väljer du målet dit du vill att data ska skickas.

   >[!NOTE]
   >
   >Tänk på följande när du konfigurerar ett rapportmål:
   >
   >* Vi rekommenderar att du använder ett molnkonto för rapportdestinationen. [Äldre FTP- och SFTP-konton](#legacy-destinations) är tillgängliga, men rekommenderas inte.
   >
   >* Molnkonton är kopplade till ditt Adobe Analytics-användarkonto. Andra användare kan inte använda eller visa molnkonton som du konfigurerar.
   >

   ![Listruta för mål för datafeed](assets/datafeed-destinations-dropdown.png)

   Använd någon av följande måltyper när du skapar en datafeed. Expandera måltypen för konfigurationsinstruktioner. (Ytterligare [äldre destinationer](#legacy-destinations) finns också tillgängliga, men rekommenderas inte.)

   +++Amazon S3

   Du kan skicka feeds direkt till Amazon S3-butiker. Den här måltypen kräver endast ditt Amazon S3-konto och platsen (bucket).

   Adobe Analytics använder kontoautentisering för att överföra filer från Adobe Analytics till den angivna platsen i din Amazon S3-instans.

   Så här konfigurerar du en Amazon S3-bucket som mål för en datafeed:

   1. På Adobe Analytics Admin Console i [!UICONTROL **Mål**] avsnitt, markera [!UICONTROL **Amazon S3**].

      ![Amazon S3-mål](assets/datafeed-destination-amazons3.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan Amazon S3 Export Locations (Exportplatser) visas.

   1. (Villkorligt) Om du tidigare har lagt till ett Amazon S3-konto och en plats:

      1. Välj konto på [!UICONTROL **Välj konto**] listruta.

      1. Välj plats på menyn [!UICONTROL **Välj plats**] listruta.

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Amazon S3-plats som du har angett.

   1. (Villkorligt) Om du inte tidigare har lagt till ett Amazon S3-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för kontot. Det kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Roll-ARN**] | Du måste ange en roll-ARN (Amazon Resource Name) som Adobe kan använda för att få åtkomst till Amazon S3-kontot. För att göra detta skapar du en IAM-behörighetsprincip för källkontot, kopplar principen till en användare och skapar sedan en roll för målkontot. Mer information finns i [den här AWS-dokumentationen](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **Användar-ARN**] | Användar-ARN (Amazon Resource Name) tillhandahålls av Adobe. Du måste koppla den här användaren till den princip du skapade. |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Namn**] | Ett namn för kontot. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Bucket**] | Den bucket på ditt Amazon S3-konto där du vill att Adobe Analytics-data ska skickas. <p>Se till att användar-ARN som tillhandahålls av Adobe har `S3:PutObject` behörighet för att överföra filer till denna bucket. Med den här behörigheten kan användaren ARN överföra initiala filer och skriva över filer för efterföljande överföringar.</p> |
         | [!UICONTROL **Prefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/` |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Amazon S3-plats som du har angett.

+++

   +++Azure RBAC

   Du kan skicka feeds direkt till en Azure-behållare med RBAC-autentisering. Den här måltypen kräver ett program-ID, klientorganisations-ID och hemlighet.

   Så här konfigurerar du ett Azure RBAC-konto som mål för en datafeed:

   1. Om du inte redan har det skapar du ett Azure-program som Adobe Analytics kan använda för autentisering och tilldelar sedan åtkomstbehörigheter i åtkomstkontrollen (IAM).

      Mer information finns i [Microsoft Azure-dokumentation om hur du skapar ett Azure Active Directory-program](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. På Adobe Analytics Admin Console i [!UICONTROL **Mål**] avsnitt, markera [!UICONTROL **Azure RBAC**].

      ![Azure RBAC-mål](assets/datafeed-destination-azurerbac.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan med Azure RBAC-exportplatser visas.

   1. (Villkorligt) Om du tidigare har lagt till ett Azure RBAC-konto och en plats:

      1. Välj konto på [!UICONTROL **Välj konto**] listruta.

      1. Välj plats på menyn [!UICONTROL **Välj plats**] listruta.

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure RBAC-plats som du angav.

   1. (Villkorligt) Om du inte tidigare har lagt till ett Azure RBAC-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för Azure RBAC-kontot. Det här namnet visas i dialogrutan [!UICONTROL **Välj konto**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av Azure RBAC-kontot. Beskrivningen visas i [!UICONTROL **Välj konto**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Hemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Namn**] | Ett namn för platsen. Det här namnet visas i dialogrutan [!UICONTROL **Välj plats**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av platsen. Beskrivningen visas i [!UICONTROL **Välj plats**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Konto**] | Azure-lagringskontot. |
         | [!UICONTROL **Behållare**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. Se till att du ger behörighet att överföra filer till Azure-programmet som du skapade tidigare. |
         | [!UICONTROL **Prefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/`<p>Kontrollera att det program-ID som du angav när du konfigurerade Azure RBAC-kontot har tilldelats `Storage Blob Data Contributor` roll för att komma åt behållaren (mappen).</p> <p>Mer information finns i [Inbyggda Azure-roller](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure RBAC-plats som du angav.

+++

   +++Azure SAS

   Du kan skicka feeds direkt till en Azure-behållare med SAS-autentisering. Den här måltypen kräver ett program-ID, klientorganisations-ID, nyckelvalvs-URI, nyckelvalvets hemliga namn och hemlighet.

   Så här konfigurerar du Azure SAS som mål för en datafeed:

   1. Om du inte redan har det skapar du ett Azure-program som Adobe Analytics kan använda för autentisering.

      Mer information finns i [Microsoft Azure-dokumentation om hur du skapar ett Azure Active Directory-program](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. På Adobe Analytics Admin Console i [!UICONTROL **Mål**] avsnitt, markera [!UICONTROL **Azure SAS**].

      ![Azure SAS-mål](assets/datafeed-destination-azuresas.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan med Azure SAS-exportplatser visas.

   1. (Villkorligt) Om du tidigare har lagt till ett Azure SAS-konto och en plats:

      1. Välj konto på [!UICONTROL **Välj konto**] listruta.

      1. Välj plats på menyn [!UICONTROL **Välj plats**] listruta.

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure SAS-plats som du angav.

   1. (Villkorligt) Om du inte tidigare har lagt till ett Azure SAS-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för Azure SAS-kontot. Det här namnet visas i dialogrutan [!UICONTROL **Välj konto**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av Azure SAS-kontot. Beskrivningen visas i [!UICONTROL **Välj konto**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **URI för nyckelvalv**] | <p>Sökvägen till SAS-token i Azure Key Vault.  Om du vill konfigurera Azure SAS måste du lagra en SAS-token som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI har skapats:<ul><li>Lägg till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade.</li><li>Kontrollera att program-ID:t har tilldelats `Key Vault Certificate User` inbyggd roll för att komma åt nyckelvalvs-URI.</br><p>Mer information finns i [Inbyggda Azure-roller](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Mer information finns i [Microsoft Azure-dokumentation om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
         | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på **Key Vault** inställningssidor. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Hemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Namn**] | Ett namn för platsen. Det här namnet visas i dialogrutan [!UICONTROL **Välj plats**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av platsen. Beskrivningen visas i [!UICONTROL **Välj plats**] nedrullningsbart fält och kan vara vilket namn du vill. |
         | [!UICONTROL **Behållare**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. |
         | [!UICONTROL **Prefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/`<p>Kontrollera att det SAS-tokenarkiv som du angav i fältet Nyckelvalvets hemliga namn när du konfigurerar Azure SAS-kontot har `Write` behörighet. Detta gör att SAS-token kan skapa filer i din Azure-behållare. <p>Om du vill att SAS-token även ska skriva över filer måste du se till att SAS-tokenarkivet har `Delete` behörighet.</p><p>Mer information finns i [Lagringsresurser för blob](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) i dokumentationen för Azure Blob Storage.</p> |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure SAS-plats som du angav.

+++

   +++Google Cloud Platform

   Du kan skicka feeds direkt till Google Cloud Platform-buketter (GCP). Den här måltypen kräver endast ditt GCP-kontonamn och platsens (bucket) namn.

   Adobe Analytics använder kontoautentisering för att överföra filer från Adobe Analytics till den angivna platsen i GCP-instansen.

   Så här konfigurerar du en GCP-bucket som mål för en datafeed:

   1. På Adobe Analytics Admin Console i [!UICONTROL **Mål**] avsnitt, markera [!UICONTROL **Google Cloud Platform**].

      ![Google Cloud Platform-mål](assets/datafeed-destination-gcp.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan GCP-exportplatser visas.

   1. (Villkorligt) Om du tidigare har lagt till ett GCP-konto och en plats:

      1. Välj konto på [!UICONTROL **Välj konto**] listruta.

      1. Välj plats på menyn [!UICONTROL **Välj plats**] listruta.

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den GCP-plats som du angav.

   1. (Villkorligt) Om du inte tidigare har lagt till ett GCP-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för kontot. Det kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Projekt-ID**] | Ditt projekt-ID för Google Cloud. Se [Google Cloud-dokumentation om hur du får ett projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **kapitalbelopp**] | Huvudmannen tillhandahålls av Adobe. Du måste ge den här huvudmannen behörighet att ta emot feeds. |
         | [!UICONTROL **Namn**] | Ett namn för kontot. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Bucket**] | Den bucket på ditt GCP-konto där du vill att Adobe Analytics-data ska skickas. <p>Se till att du har beviljat någon av följande behörigheter till säkerhetsobjektet som tillhandahålls av Adobe:<ul><li>`roles/storage.objectCreator`: Använd den här behörigheten om du vill begränsa säkerhetsobjektet till att endast skapa filer i ditt GCP-konto. </br>**Viktigt:** Om du använder den här behörigheten för schemalagd rapportering måste du använda ett unikt filnamn för varje ny schemalagd export. Annars misslyckas rapportgenereringen eftersom huvudkontot inte har åtkomst att skriva över befintliga filer.</li><li>(Rekommenderas) `roles/storage.objectUser`: Använd den här behörigheten om du vill att säkerhetsobjektet ska ha tillgång till visa, lista, uppdatera och ta bort filer i ditt GCP-konto.</br>Med den här behörigheten kan huvudmannen skriva över befintliga filer för efterföljande överföringar, utan att behöva generera unika filnamn automatiskt för varje ny schemalagd export.</li></ul><p>Mer information om att bevilja behörigheter finns i [Lägga till ett huvudnamn i en princip på paketnivå](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) i Google Cloud-dokumentationen.</p> |
         | [!UICONTROL **Prefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/` |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den GCP-plats som du angav.

+++

1. I  [!UICONTROL **Datakolumndefinitioner**] väljer du den senaste [!UICONTROL **Alla Adobe Columns**] i listrutan och fyll sedan i följande fält:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Ta bort escape-tecken**] | När du samlar in data kan vissa tecken (till exempel nya rader) orsaka problem. Markera den här rutan om du vill att dessa tecken ska tas bort från feed-filerna. |
   | [!UICONTROL **Komprimeringsformat**] | Den typ av komprimering som används. **Gzip** skickar filer i `.tar.gz` format. **Postnummer** skickar filer i `.zip` format. |
   | [!UICONTROL **Förpackningstyp**] | Välj **Flera filer** för de flesta dataflöden. Med det här alternativet numreras data till okomprimerade 2 GB-segment. (Om flera filer är markerade och okomprimerade data för rapportfönstret är mindre än 2 GB skickas en fil.) Markera **En fil** ger `hit_data.tsv` i en enda, potentiellt enorm fil. |
   | [!UICONTROL **Manifest**] | Om Adobe ska leverera en [manifestfil](c-df-contents/datafeeds-contents.md#feed-manifest) till målet när inga data samlas in för ett feed-intervall. Om du väljer **Manifest-fil** får du en manifestfil som liknar den här när inga data samlas in:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Kolumnmallar**] | När du skapar många dataflöden rekommenderar Adobe att du skapar en kolumnmall. Om du väljer en kolumnmall inkluderas automatiskt de angivna kolumnerna i mallen. Adobe har också flera mallar som standard. |
   | [!UICONTROL **Tillgängliga kolumner**] | Alla tillgängliga datakolumner i Adobe Analytics. Klicka [!UICONTROL Add all] om du vill ta med alla kolumner i en datafeed. |
   | [!UICONTROL **Inkluderade kolumner**] | De kolumner som ska inkluderas i en datafeed. Klicka [!UICONTROL Remove all] om du vill ta bort alla kolumner från en datafeed. |
   | [!UICONTROL **Hämta CSV**] | Hämtar en CSV-fil som innehåller alla inkluderade kolumner. |

1. Välj [!UICONTROL **Spara**] överst till höger.

   Historisk databehandling påbörjas omedelbart. När data har bearbetats för en dag skickas filen till det mål som du konfigurerade.

   Mer information om hur du får tillgång till dataflödet och får en bättre förståelse för innehållet finns i [Innehåll i datafeed - översikt](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Äldre destinationer

>[!IMPORTANT]
>
>Destinationerna som beskrivs i det här avsnittet är äldre och rekommenderas inte. Använd i stället ett av följande mål när du skapar en datafeed: Amazon S3, Google Cloud Platform, Azure RBAC eller Azure SAS. Se [Skapa och konfigurera en datafeed](#create-and-configure-a-data-feed) för detaljerad information om vart och ett av dessa rekommenderade destinationer.


Följande information innehåller konfigurationsinformation för var och en av de äldre målplatserna:

### FTP

Data från dataflöden kan levereras till en FTP-plats som är värd för Adobe eller kunder. Kräver FTP-värd, användarnamn och lösenord. Använd sökvägsfältet för att placera feed-filer i en mapp. Mappar måste redan finnas. Flöden genererar ett fel om den angivna sökvägen inte finns.

Använd följande information när du fyller i de tillgängliga fälten:

* [!UICONTROL **Värd**]: Ange önskad mål-URL för FTP. Till exempel: `ftp://ftp.omniture.com`.
* [!UICONTROL **Bana**]: Kan lämnas tomt
* [!UICONTROL **Användarnamn**]: Ange användarnamn för att logga in på FTP-platsen.
* [!UICONTROL **Lösenord och bekräfta lösenord**]: Ange lösenordet för att logga in på FTP-platsen.

### SFTP

SFTP-stöd för dataflöden finns tillgängligt. Kräver att en SFTP-värd, ett användarnamn och målplatsen innehåller en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar flödet.

### S3

Du kan skicka feeds direkt till Amazon S3-butiker. Den här måltypen kräver ett Bucket-namn, ett Access Key ID och en Secret Key. Se [Krav för Amazon S3-bucket](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) i Amazon S3-dokumenten för mer information.

Användaren som du anger för överföring av datafeeds måste ha följande [behörigheter](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >För varje överföring till en Amazon S3-bucket [!DNL Analytics] lägger till bucket-ägaren till BucketOwnerFullControl ACL, oavsett om bucket har en princip som kräver det eller inte. Mer information finns i &quot;[Vad är inställningen BucketOwnerFullControl för Amazon S3-dataflöden?](df-faq.md#BucketOwnerFullControl)&quot;

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

Datamatningar stöder Azure Blob-mål. Kräver en behållare, ett konto och en nyckel. Amazon krypterar automatiskt vilande data. När du hämtar data dekrypteras de automatiskt. Se [Skapa ett lagringskonto](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) i Microsoft Azure-dokumenten om du vill ha mer information.

>[!NOTE]
>
>Du måste implementera en egen process för att hantera diskutrymme på matningsmålet. Adobe tar inte bort några data från servern.
