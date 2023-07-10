---
description: Konfigurera molnimportkontot och platsen där klassificeringsdata kan överföras
keywords: Analysis Workspace
title: Konfigurera platser för molnimport
feature: Classifications
source-git-commit: 8d6ee33e867da274334c8adc557105af4942c894
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 1%

---

# Konfigurera platser för molnimport

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Innan du kan importera Adobe Analytics-klassificeringsdata från ett molnmål måste du lägga till och konfigurera platsen där du vill att klassificeringsdata ska samlas in.

Den här processen består av att lägga till och konfigurera kontot (till exempel Amazon S3 Role ARN, Google Cloud Platform o.s.v.) och platsen inom kontot (till exempel en mapp i kontot).

## Lägg till ett konto

Du måste konfigurera Adobe Analytics med den information som krävs för att komma åt ditt molnmålkonto.

1. I Adobe Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Platser**].
1. På [!UICONTROL Locations] väljer du [!UICONTROL **Platsautentiseringsuppgifter**] -fliken.
1. Välj [!UICONTROL **Lägg till konto**]. <!-- add screenshot? -->

   Dialogrutan Lägg till konto visas.
1. Ange följande information: |Fält | Funktion | |—|—| | [!UICONTROL **Platskontonamn**] | Namnet på platskontot. Det här namnet visas när du skapar en plats | | [!UICONTROL **Beskrivning av platskonto**] | Ange en kort beskrivning av kontot så att det kan särskiljas från andra konton av samma kontotyp. | | [!UICONTROL **Kontotyp**] | Välj typ av molnkonto. Vi rekommenderar att du har ett enda konto för varje kontotyp, med flera platser efter behov inom det kontot. |
1. I [!UICONTROL **Kontoegenskaper**] anger du information som är specifik för den kontotyp som du har valt.

   Utöka det avsnitt nedan som motsvarar konfigurationsinstruktionerna [!UICONTROL **Kontotyp**] som du valde.

   +++Amazon S3 Roll ARN

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
   | [!UICONTROL **Program-ID**] | Kopiera detta ID från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Översikt** i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera detta ID från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Översikt** i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI för nyckelvalv**] | <p>Sökvägen till SAS-token i Azure Key Vault.  Om du vill konfigurera Azure SAS måste du lagra en SAS-token som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI:n har skapats lägger du till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade. Mer information finns i [Microsoft Azure-dokumentation om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på **Nyckelvalv** inställningssidor. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Ange följande information för att konfigurera ett Azure RBAC-konto:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Program-ID**] | Kopiera detta ID från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Översikt** i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera detta ID från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Översikt** i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. Välj [!UICONTROL **Spara**].

1. Fortsätt med [Lägg till en plats](#add-a-location).

## Lägg till en plats

1. Du måste lägga till ett konto innan du kan lägga till en plats. [Lägg till ett konto](#add-an-account) om du inte redan gjort det.
1. I Adobe Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Platser**].
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
   | [!UICONTROL **Bucketnamn**] | Den bucket på ditt Amazon S3-konto där du vill att Adobe Analytics-data ska skickas. Se till att användar-ARN som tillhandahålls av Adobe har åtkomst till att överföra filer till den här bucket. |
   | [!UICONTROL **Nyckelprefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Ange följande information för att konfigurera en plats för Google Cloud-plattformen:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Bucketnamn**] | Den bucket på ditt GCP-konto där du vill att Adobe Analytics-data ska skickas. Se till att du har gett Adobe tillåtelse att överföra filer till denna bucket till säkerhetsobjektet. |
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