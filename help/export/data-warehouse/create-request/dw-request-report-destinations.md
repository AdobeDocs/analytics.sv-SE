---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera ett rapportmål för en Data Warehouse-begäran
feature: Data Warehouse
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 0%

---

# Konfigurera ett rapportmål för en Data Warehouse-begäran

{{release-limited-testing}}

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
      | [!UICONTROL **Kontotyp**] | Välj typ av molnkonto. Vi rekommenderar att du har ett enda konto för varje kontotyp, med flera platser efter behov inom det kontot. <p>När du har valt en kontotyp visas fält som är specifika för den kontotypen. Om du vill ha konfigurationsinstruktioner för varje kontotyp expanderar du det avsnitt nedan som motsvarar det du väljer. </p> |
      | [!UICONTROL **Kontonamn**] | Ange ett namn för kontot. Det här namnet visas när du skapar en plats. <!-- true? --> |
      | [!UICONTROL **Kontobeskrivning**] | Ange en kort beskrivning av kontot för att hjälpa till att skilja det från andra konton av samma kontotyp. |

      Utöka det avsnitt nedan som motsvarar [!UICONTROL **Kontotyp**] som du valde.

      Använd någon av följande kontotyper när du konfigurerar ett rapportmål. Expandera kontotypen om du vill ha konfigurationsinstruktioner. (Ytterligare äldre destinationer <!-- add link --> finns också tillgängliga, men rekommenderas inte.)

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

      Om du vill ha konfigurationsinstruktioner expanderar du det avsnitt nedan som motsvarar kontotypen som du valde tidigare.

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