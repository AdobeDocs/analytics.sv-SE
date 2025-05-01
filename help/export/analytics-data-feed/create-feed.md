---
title: Skapa en datafeed
description: Lär dig hur du skapar en datafeed och om filinformationen som ska skickas till Adobe.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: b53ef727adc563e05403c50d80bbd0c48bb8a054
workflow-type: tm+mt
source-wordcount: '4125'
ht-degree: 0%

---

# Skapa en datafeed

När du skapar en datafeed får du följande från Adobe:

* Information om målet dit du vill skicka rådatafiler
* De data som du vill inkludera i varje fil

Innan du skapar en datafeed är det viktigt att du har en grundläggande förståelse för dataflöden och att du ser till att alla krav uppfylls. Mer information finns i [Översikt över dataflöden](data-feed-overview.md).

## Skapa och konfigurera en datafeed

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Markera ikonen med nio kvadrater i det övre högra hörnet och välj sedan [!UICONTROL **Analytics**].
1. Gå till [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**] i det övre navigeringsfältet.
1. Välj [!UICONTROL **Lägg till**].

   ![Lägg till datafeed](assets/datafeed-add.png)

   En sida visas med tre huvudkategorier: [!UICONTROL **Feed-information**], [!UICONTROL **Mål**] och [!UICONTROL **Data-kolumndefinitioner**].
1. Fyll i följande fält i avsnittet [!UICONTROL **Feed Information**]:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Namn**] | Dataflödets namn. Måste vara unikt i den valda rapportsviten och får innehålla upp till 255 tecken. |
   | [!UICONTROL **Rapportsviten**] | Rapportsviten som dataflödet baseras på. Om flera dataflöden skapas för samma rapportserie måste de ha olika kolumndefinitioner. Endast källrapportsviter stöder dataflöden. Virtuella rapportsviter stöds inte. |
   | [!UICONTROL **Skicka e-post när det är klart**] | E-postadressen som ska meddelas när en feed har bearbetats. E-postadressen måste vara korrekt formaterad. |
   | [!UICONTROL **Feed-intervall**] | Välj **Dagligen** för bakåtfyllnad eller historiska data. Dagliga matningar innehåller data för en hel dag, från midnatt till midnatt i rapportsvitens tidszon. Välj **Varje timme** om du vill fortsätta med data (Daily är även tillgängligt för att fortsätta feeds om du vill). Timmatningar innehåller en timmes data. |
   | [!UICONTROL **Fördröjd bearbetning**] | Vänta en viss tid innan du bearbetar en datafeedfil. En fördröjning kan vara användbar för att ge mobila implementeringar möjlighet att komma online och skicka data på offlineenheter. Den kan också användas för att hantera serverprocesser i organisationen när tidigare bearbetade filer hanteras. I de flesta fall behövs ingen fördröjning. En feed kan fördröjas med upp till 120 minuter. |
   | [!UICONTROL **Start- och slutdatum**] | Startdatumet anger det datum då du vill att dataflödet ska börja. Om du omedelbart vill börja bearbeta dataflöden för historiska data anger du det här datumet till ett tidigare datum när data samlas in. Start- och slutdatumen baseras på rapportsvitens tidszon. |
   | [!UICONTROL **Kontinuerlig feed**] | Den här kryssrutan tar bort slutdatumet, vilket gör att en feed kan köras på obestämd tid. När en feed har avslutat bearbetningen av historiska data väntar en feed på data för att slutföra insamlingen under en given timme eller dag. När den aktuella timmen eller dagen är slut börjar bearbetningen efter den angivna fördröjningen. |

1. I avsnittet [!UICONTROL **Mål**] väljer du i listrutan [!UICONTROL **Typ**] målet dit du vill att data ska skickas.

   >[!NOTE]
   >
   >Tänk på följande när du konfigurerar ett rapportmål:
   >
   >* Vi rekommenderar att du använder ett molnkonto för rapportdestinationen. [Äldre FTP- och SFTP-konton](#legacy-destinations) är tillgängliga, men rekommenderas inte.
   >* Alla molnkonton som du tidigare konfigurerat är tillgängliga för datafeeds. Du kan konfigurera molnkonton på något av följande sätt:
   >
   >   * När molnkonton konfigureras för [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
   >   
   >   * Vid [import av Adobe Analytics-klassificeringsdata](/help/components/locations/locations-manager.md) (Det går inte att använda platser som har konfigurerats för import av klassificeringsdata.)
   >   
   >   * Från Platshanteraren, i [Komponenter > Platser](/help/components/locations/configure-import-accounts.md)
   >
   >* Molnkonton är kopplade till ditt Adobe Analytics-användarkonto. Andra användare kan inte använda eller visa molnkonton som du konfigurerar.
   >
   >* Du kan redigera alla platser som du skapar från platshanteraren i [Komponenter > Platser](/help/components/locations/configure-import-accounts.md)

   ![Listrutan Mål för datafeed](assets/datafeed-destinations-dropdown.png)

   Använd någon av följande måltyper när du skapar en datafeed. Expandera måltypen för konfigurationsinstruktioner. (Ytterligare [äldre mål](#legacy-destinations) är också tillgängliga, men rekommenderas inte.)

   +++Amazon S3

   Du kan skicka feeds direkt till Amazon S3-butiker. Den här måltypen kräver endast ditt Amazon S3-konto och platsen (bucket).

   Adobe Analytics använder kontoautentisering för att överföra filer från Adobe Analytics till den angivna platsen i din Amazon S3-instans.

   Så här konfigurerar du en Amazon S3-bucket som mål för en datafeed:

   1. Börja skapa en datafeed enligt beskrivningen i [Skapa och konfigurera en datafeed](#create-and-configure-a-data-feed).

   1. I avsnittet [!UICONTROL **Mål**] väljer du [!UICONTROL **Amazon S3**] i listrutan [!UICONTROL **Typ**].

      ![Amazon S3-mål](assets/datafeed-destination-amazons3.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan Amazon S3 Export Locations (Exportplatser) visas.

   1. (Villkorligt) Om ett Amazon S3-konto (och en plats för det kontot) redan har konfigurerats i Adobe Analytics kan du använda det som mål för dataflödet:

      >[!NOTE]
      >
      >Konton är bara tillgängliga för dig om du har konfigurerat dem eller om de delats med en organisation som du är en del av.

      1. Välj kontot i listrutan [!UICONTROL **Välj konto**].

         Alla molnkonton som konfigurerats i något av följande områden i Adobe Analytics är tillgängliga att använda:

         * Vid import av Adobe Analytics-klassificeringsdata, enligt beskrivningen i [Schema](/help/components/classifications/sets/manage/schema.md).

           Eventuella platser som har konfigurerats för import av klassificeringsdata kan dock inte användas. Lägg i stället till ett nytt mål enligt beskrivningen nedan.

         * När konton och platser konfigureras i området Platser, enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md).

      1. Välj plats i listrutan [!UICONTROL **Välj plats**].

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

      Målet är nu konfigurerat att skicka data till den Amazon S3-plats som du har angett.

   1. (Villkorligt) Om du inte tidigare har lagt till ett Amazon S3-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för kontot. Det kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Roll-ARN**] | Du måste ange ett ROLL-ARN (Amazon Resource Name) som Adobe kan använda för att få åtkomst till Amazon S3-kontot. För att göra detta skapar du en IAM-behörighetsprincip för källkontot, kopplar principen till en användare och skapar sedan en roll för målkontot. Mer information finns i [den här AWS-dokumentationen](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **ANVÄNDAREN ÄR**] | Användar-ARN (Amazon Resource Name) tillhandahålls av Adobe. Du måste koppla den här användaren till den princip du skapade. |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Namn**] | Ett namn för kontot. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Bucket**] | Den bucket på ditt Amazon S3-konto där du vill att Adobe Analytics-data ska skickas. <p>Se till att användar-ARN som tillhandahölls av Adobe har behörigheten `S3:PutObject` för att kunna överföra filer till den här bucket. Med den här behörigheten kan användaren ARN överföra initiala filer och skriva över filer för efterföljande överföringar.</p><p>Bucket-namn måste uppfylla specifika namnregler. De måste till exempel innehålla mellan 3 och 63 tecken, får endast bestå av gemener, siffror, punkter (.) och bindestreck (-) och måste börja och sluta med en bokstav eller en siffra. [En fullständig lista över namnregler finns i AWS-dokumentationen](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
         | [!UICONTROL **Prefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/` |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Amazon S3-plats som du har angett.

      1. (Villkorligt) Om du behöver hantera målet (kontot och platsen) som du nyss skapade, är det tillgängligt i [Platshanteraren](/help/components/locations/locations-manager.md).

+++

   +++Azure RBAC

   Du kan skicka feeds direkt till en Azure-behållare med RBAC-autentisering. Den här måltypen kräver ett program-ID, klientorganisations-ID och hemlighet.

   Så här konfigurerar du ett Azure RBAC-konto som mål för en datafeed:

   1. Om du inte redan har det skapar du ett Azure-program som Adobe Analytics kan använda för autentisering och tilldelar sedan åtkomstbehörigheter i åtkomstkontrollen (IAM).

      Mer information finns i [Microsoft Azure-dokumentationen om hur du skapar ett Azure Active Directory-program](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. I Adobe Analytics Admin Console väljer du [!UICONTROL **Azure RBAC**] i avsnittet [!UICONTROL **Mål**] på den nedrullningsbara menyn [!UICONTROL **Typ**].

      ![Azure RBAC-mål](assets/datafeed-destination-azurerbac.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan med Azure RBAC-exportplatser visas.

   1. (Villkorligt) Om ett Azure RBAC-konto (och en plats för det kontot) redan har konfigurerats i Adobe Analytics kan du använda det som mål för din datafeed:

      >[!NOTE]
      >
      >Konton är bara tillgängliga för dig om du har konfigurerat dem eller om de delats med en organisation som du är en del av.

      1. Välj kontot i listrutan [!UICONTROL **Välj konto**].

      Alla molnkonton som du har konfigurerat i något av följande områden i Adobe Analytics kan användas:

      * Vid import av Adobe Analytics-klassificeringsdata, enligt beskrivningen i [Schema](/help/components/classifications/sets/manage/schema.md).

        Eventuella platser som har konfigurerats för import av klassificeringsdata kan dock inte användas. Lägg i stället till ett nytt mål enligt beskrivningen nedan.

      * När konton och platser konfigureras i området Platser, enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md).

      1. Välj plats i listrutan [!UICONTROL **Välj plats**].

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure RBAC-plats som du angav.

   1. (Villkorligt) Om du inte tidigare har lagt till ett Azure RBAC-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för Azure RBAC-kontot. Det här namnet visas i listrutan [!UICONTROL **Välj konto**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av Azure RBAC-kontot. Beskrivningen visas i den nedrullningsbara menyn [!UICONTROL **Välj konto**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Hemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på fliken **Certifikat och hemligheter** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Namn**] | Ett namn för platsen. Det här namnet visas i listrutan [!UICONTROL **Välj plats**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av platsen. Den här beskrivningen visas i listrutan [!UICONTROL **Välj plats**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Konto**] | Azure-lagringskontot. |
         | [!UICONTROL **Behållare**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. Se till att du ger behörighet att överföra filer till Azure-programmet som du skapade tidigare. |
         | [!UICONTROL **Prefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/`<p>Kontrollera att det program-ID som du angav när du konfigurerade Azure RBAC-kontot har tilldelats rollen `Storage Blob Data Contributor` för att komma åt behållaren (mappen).</p> <p>Mer information finns i [Inbyggda Azure-roller](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure RBAC-plats som du angav.

      1. (Villkorligt) Om du behöver hantera målet (kontot och platsen) som du nyss skapade, är det tillgängligt i [Platshanteraren](/help/components/locations/locations-manager.md).

+++

   +++Azure SAS

   Du kan skicka feeds direkt till en Azure-behållare genom att använda SAS-autentisering. Den här måltypen kräver ett program-ID, klientorganisations-ID, nyckelvalvs-URI, nyckelvalvets hemliga namn och hemlighet.

   Så här konfigurerar du Azure SAS som mål för en datafeed:

   1. Om du inte redan har det skapar du ett Azure-program som Adobe Analytics kan använda för autentisering.

      Mer information finns i [Microsoft Azure-dokumentationen om hur du skapar ett Azure Active Directory-program](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. I Adobe Analytics Admin Console väljer du [!UICONTROL **Azure SAS**] i avsnittet [!UICONTROL **Mål**].

      ![Azure SAS-mål](assets/datafeed-destination-azuresas.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan med Azure SAS-exportplatser visas.

   1. (Villkorligt) Om ett Azure SAS-konto (och en plats för det kontot) redan har konfigurerats i Adobe Analytics kan du använda det som mål för din datafeed:

      >[!NOTE]
      >
      >Konton är bara tillgängliga för dig om du har konfigurerat dem eller om de delats med en organisation som du är en del av.

      1. Välj kontot i listrutan [!UICONTROL **Välj konto**].

         Alla molnkonton som du har konfigurerat i något av följande områden i Adobe Analytics kan användas:

         * Vid import av Adobe Analytics-klassificeringsdata, enligt beskrivningen i [Schema](/help/components/classifications/sets/manage/schema.md).

           Eventuella platser som har konfigurerats för import av klassificeringsdata kan dock inte användas. Lägg i stället till ett nytt mål enligt beskrivningen nedan.

         * När konton och platser konfigureras i området Platser, enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md).

      1. Välj plats i listrutan [!UICONTROL **Välj plats**].

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure SAS-plats som du angav.

   1. (Villkorligt) Om du inte tidigare har lagt till ett Azure SAS-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för Azure SAS-kontot. Det här namnet visas i listrutan [!UICONTROL **Välj konto**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av Azure SAS-kontot. Beskrivningen visas i den nedrullningsbara menyn [!UICONTROL **Välj konto**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på fliken **Översikt** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Nyckelvalvs-URI**] | <p>Sökvägen till SAS URI i Azure Key Vault. Om du vill konfigurera Azure SAS måste du lagra en SAS URI som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentationen om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI har skapats:<ul><li>Lägg till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade.<p>Mer information finns i [Microsoft Azure-dokumentationen om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>eller</p><p>Om du vill tilldela en åtkomstroll direkt utan att skapa en åtkomstprincip läser du [Microsoft Azure-dokumentationen om hur du tilldelar Azure-roller med Azure-portalen](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Detta lägger till rolltilldelningen för program-ID:t för åtkomst till nyckelvalvs-URI:n. </p></li><li>Kontrollera att program-ID har tilldelats den inbyggda rollen `Key Vault Certificate User` för att komma åt nyckelvalvs-URI.</br><p>Mer information finns i [Inbyggda Azure-roller](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul> |
         | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på inställningssidorna för **nyckelvalv**. Mer information finns i [Microsoft Azure-dokumentationen om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Hemlighet**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på fliken **Certifikat och hemligheter** i ditt program. Mer information finns i [Microsoft Azure-dokumentationen om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Namn**] | Ett namn för platsen. Det här namnet visas i listrutan [!UICONTROL **Välj plats**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av platsen. Den här beskrivningen visas i listrutan [!UICONTROL **Välj plats**] och kan vara vilket namn du vill. |
         | [!UICONTROL **Behållare**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. |
         | [!UICONTROL **Prefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/`<p>Kontrollera att SAS URI-arkivet som du angav i fältet Nyckelvalvets hemliga namn när du konfigurerar Azure SAS-kontot har behörigheten `Write`. Detta gör att SAS URI kan skapa filer i din Azure-behållare. <p>Om du även vill att SAS-URI:n ska skriva över filer måste du se till att SAS URI-arkivet har behörigheten `Delete`.</p><p>Mer information finns i [Blob Storage-resurser](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) i dokumentationen för Azure Blob Storage.</p> |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den Azure SAS-plats som du angav.

      1. (Villkorligt) Om du behöver hantera målet (kontot och platsen) som du nyss skapade, är det tillgängligt i [Platshanteraren](/help/components/locations/locations-manager.md).

+++

   +++Google Cloud Platform

   Du kan skicka feeds direkt till Google Cloud Platform-buketter (GCP). Den här måltypen kräver endast ditt GCP-kontonamn och platsens (bucket) namn.

   Adobe Analytics använder kontoautentisering för att överföra filer från Adobe Analytics till den angivna platsen i GCP-instansen.

   Så här konfigurerar du en GCP-bucket som mål för en datafeed:

   1. I Adobe Analytics Admin Console väljer du [!UICONTROL **Google Cloud-plattform**] i avsnittet [!UICONTROL **Mål**].

      ![Google Cloud-plattformsmål](assets/datafeed-destination-gcp.png)

   1. Välj [!UICONTROL **Välj plats**].

      Sidan GCP-exportplatser visas.

   1. (Villkorligt) Om ett Google Cloud Platform-konto (och en plats för det kontot) redan har konfigurerats i Adobe Analytics kan du använda det som mål för datafeeden:

      >[!NOTE]
      >
      >Konton är bara tillgängliga för dig om du har konfigurerat dem eller om de delats med en organisation som du är en del av.

      1. Välj kontot i listrutan [!UICONTROL **Välj konto**].

         Alla molnkonton som du har konfigurerat i något av följande områden i Adobe Analytics kan användas:

         * Vid import av Adobe Analytics-klassificeringsdata, enligt beskrivningen i [Schema](/help/components/classifications/sets/manage/schema.md).

           Eventuella platser som har konfigurerats för import av klassificeringsdata kan dock inte användas. Lägg i stället till ett nytt mål enligt beskrivningen nedan.

         * När konton och platser konfigureras i området Platser, enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md).

      1. Välj plats i listrutan [!UICONTROL **Välj plats**].

      1. Välj [!UICONTROL **Spara**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den plats för Google Cloud-plattformen som du angav.

   1. (Villkorligt) Om du inte tidigare har lagt till ett GCP-konto:

      1. Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Kontonamn**] | Ett namn för kontot. Det kan vara vilket namn du vill. |
         | [!UICONTROL **Kontobeskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Projekt-ID**] | Ditt projekt-ID för Google Cloud. Se [Google Cloud-dokumentationen om hur du hämtar ett projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information:

         | Fält | Funktion |
         |---------|----------|
         | [!UICONTROL **Principal**] | Huvudmannen tillhandahålls av Adobe. Du måste ge den här huvudmannen behörighet att ta emot feeds. |
         | [!UICONTROL **Namn**] | Ett namn för kontot. |
         | [!UICONTROL **Beskrivning**] | En beskrivning av kontot. |
         | [!UICONTROL **Bucket**] | Den bucket på ditt GCP-konto där du vill att Adobe Analytics-data ska skickas. <p>Kontrollera att du har beviljat någon av följande behörigheter till säkerhetsobjektet som tillhandahålls av Adobe: (Mer information om att bevilja behörigheter finns i [Lägga till ett säkerhetsobjekt i en princip på paketnivå](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) i dokumentationen för Google Cloud.)<ul><li>`roles/storage.objectCreator`: Använd den här behörigheten om du vill begränsa säkerhetsobjektet till att endast skapa filer i ditt GCP-konto. </br>**Viktigt!** Om du använder den här behörigheten för schemalagda rapporter måste du använda ett unikt filnamn för varje ny schemalagd export. Annars misslyckas rapportgenereringen eftersom huvudkontot inte har åtkomst att skriva över befintliga filer.</li><li>(Rekommenderas) `roles/storage.objectUser`: Använd den här behörigheten om du vill att säkerhetsobjektet ska ha åtkomst till att visa, lista, uppdatera och ta bort filer på ditt GCP-konto.</br>Med den här behörigheten kan huvudpersonen skriva över befintliga filer för efterföljande överföringar, utan att behöva generera unika filnamn automatiskt för varje ny schemalagd export.</li></ul><p>Om din organisation använder [begränsningar för organisationsprinciper](https://cloud.google.com/storage/docs/org-policy-constraints) för att endast tillåta Google Cloud-plattformskontot i din tillåtelselista behöver du följande Adobe-ägda Google Cloud-plattformens organisations-ID: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
         | [!UICONTROL **Prefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel: `folder_name/` |

         {style="table-layout:auto"}

      1. Välj [!UICONTROL **Skapa**] > [!UICONTROL **Spara**].

         Målet är nu konfigurerat att skicka data till den GCP-plats som du angav.

      1. (Villkorligt) Om du behöver hantera målet (kontot och platsen) som du nyss skapade, är det tillgängligt i [Platshanteraren](/help/components/locations/locations-manager.md).

+++

1. I avsnittet [!UICONTROL **Datakolumndefinitioner**] väljer du den senaste mallen [!UICONTROL **Alla Adobe-kolumner**] i listrutan och fyller sedan i följande fält:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Ta bort escape-tecken**] | När du samlar in data kan vissa tecken (till exempel nya rader) orsaka problem. Markera den här rutan om du vill att dessa tecken ska tas bort från feed-filerna. |
   | [!UICONTROL **Komprimeringsformat**] | Den typ av komprimering som används. **Gzip** skickar filer i formatet `.tar.gz`. **Zip** skickar filer i formatet `.zip`. |
   | [!UICONTROL **Paketeringstyp**] | Välj [!UICONTROL **Flera filer**] för de flesta dataflöden. Med det här alternativet numreras data till okomprimerade 2 GB-segment. (Om alternativet [!UICONTROL **Flera filer**] har valts och okomprimerade data för rapportfönstret är mindre än 2 GB skickas en fil.) Om du väljer **En fil** skapas `hit_data.tsv` -filen i en enda, potentiellt stor fil. |
   | [!UICONTROL **Manifest**] | Avgör om Adobe ska leverera en [manifestfil](c-df-contents/datafeeds-contents.md#feed-manifest) till målet när inga data samlas in för ett feed-intervall. Om du väljer **Manifestfil** får du en manifestfil som liknar följande när inga data samlas in:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Kolumnmallar**] | När du skapar många dataflöden rekommenderar Adobe att du skapar en kolumnmall. Om du väljer en kolumnmall inkluderas automatiskt de angivna kolumnerna i mallen. I Adobe finns också flera mallar som standard. |
   | [!UICONTROL **Tillgängliga kolumner**] | Alla tillgängliga datakolumner i Adobe Analytics. Klicka på [!UICONTROL Add all] om du vill inkludera alla kolumner i en datafeed. |
   | [!UICONTROL **Inkluderade kolumner**] | De kolumner som ska inkluderas i en datafeed. Klicka på [!UICONTROL Remove all] om du vill ta bort alla kolumner från en datafeed. |
   | [!UICONTROL **Hämta CSV**] | Hämtar en CSV-fil som innehåller alla inkluderade kolumner. |

1. Välj [!UICONTROL **Spara**] längst upp till höger.

   Historisk databehandling påbörjas omedelbart. När data har bearbetats för en dag skickas filen till det mål som du konfigurerade.

   Mer information om hur du får tillgång till dataflödet och får en bättre förståelse för dess innehåll finns i [Innehåll i datafeed - översikt](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Äldre destinationer

>[!IMPORTANT]
>
>Destinationerna som beskrivs i det här avsnittet är äldre och rekommenderas inte. Använd i stället ett av följande mål när du skapar en datafeed: Amazon S3, Google Cloud Platform, Azure RBAC eller Azure SAS. Se [Skapa och konfigurera en datafeed](#create-and-configure-a-data-feed) om du vill ha mer information om vart och ett av dessa rekommenderade mål.


Följande information innehåller konfigurationsinformation för var och en av de äldre målplatserna:

### FTP

Data från dataflöden kan levereras till en FTP-plats hos Adobe eller en kundvärd. Kräver FTP-värd, användarnamn och lösenord. Använd sökvägsfältet för att placera feed-filer i en mapp. Mappar måste redan finnas. Flöden genererar ett fel om den angivna sökvägen inte finns.

Använd följande information när du fyller i de tillgängliga fälten:

* [!UICONTROL **Värd**]: Ange önskad mål-URL för FTP. Exempel: `ftp://ftp.omniture.com`.
* [!UICONTROL **Sökväg**]: Kan lämnas tom
* [!UICONTROL **Användarnamn**]: Ange användarnamnet för att logga in på FTP-platsen.
* [!UICONTROL **Lösenord och bekräfta lösenord**]: Ange lösenordet för att logga in på FTP-platsen.

### SFTP

SFTP-stöd för dataflöden finns tillgängligt. Kräver att en SFTP-värd, ett användarnamn och målplatsen innehåller en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar flödet.

### S3

Du kan skicka feeds direkt till Amazon S3-butiker. Den här måltypen kräver ett Bucket-namn, ett Access Key ID och en Secret Key. Mer information finns i [Namngivningskrav för Amazon S3-bucket](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) i Amazon S3-dokumenten.

Användaren som du anger för överföring av datafeeds måste ha följande [behörigheter](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >För varje överföring till en Amazon S3-bucket lägger [!DNL Analytics] till bucket-ägaren i BucketOwnerFullControl ACL, oavsett om bucket har en princip som kräver det eller inte. Mer information finns i [Vad är inställningen BucketOwnerFullControl för Amazon S3-dataflöden?](df-faq.md#BucketOwnerFullControl)

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

Datamatningar stöder Azure Blob-mål. Kräver en behållare, ett konto och en nyckel. Amazon krypterar automatiskt vilande data. När du hämtar data dekrypteras de automatiskt. Mer information finns i [Skapa ett lagringskonto](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) i Microsoft Azure-dokumenten.

>[!NOTE]
>
>Du måste implementera en egen process för att hantera diskutrymme på matningsmålet. Adobe tar inte bort några data från servern.
