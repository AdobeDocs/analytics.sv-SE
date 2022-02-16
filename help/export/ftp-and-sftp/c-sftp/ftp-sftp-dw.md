---
description: Adobe stöder export av Data warehouse-begäranden till SFTP-servrar.
keywords: ftp;sftp
title: Skicka Data Warehouse-förfrågningar till SFTP-servrar
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 3%

---

# Skicka Data Warehouse-förfrågningar till SFTP-servrar

Adobe stöder export av Data warehouse-begäranden till SFTP-servrar.

Se till att följande uppgifter är slutförda:

Adobe stöder export av Data warehouse-begäranden till SFTP-servrar, förutsatt att följande uppfylls:

* [!DNL sftp://] -protokollet anges i värdfältet (till exempel [!DNL sftp://ftp.example.com]) och ENDAST port 22 används när en Data warehouse-rapport begärs.

   Du kan också använda [!DNL sftp+norename://] enligt nedan.

* Adobe [!DNL authorized_keys] filen finns i [!DNL .ssh] i rotkatalogen för den användare du loggar in med

* Målet är inte [!DNL ftp.omniture.com]. SFTP-protokoll mellan Adobe interna servrar stöds inte.
* Målet stöder enfaktorsautentisering (PKI). Om det finns en tvåfaktorskontroll misslyckas leveransen av rapporten. Kontrollera att servern inte är konfigurerad att försöka utföra tvåfaktorsautentisering. Adobe Analytics kräver att bara nyckeln och inget annat används för att logga in.
* Adobe stöder SSHv2-kryptering och återgår till SSHv1 (endast RSA-nyckeln).

Så här skickar du [!DNL Data Warehouse] begäran via SFTP:

1. Hämta [!DNL authorized_keys] genom att låta någon av de användare som stöds i organisationen kontakta Kundtjänst.
1. När den här filen har hämtats loggar du in på FTP-webbplatsen med samma inloggningsuppgifter som används för [!DNL Data Warehouse] begäran.
1. Navigera till mappen med namnet i rotkatalogen [!DNL .ssh] (om det inte finns någon) skapar du en) och placerar [!DNL authorized_keys] filen där.

1. Gå till [!DNL Data Warehouse] begäranhanteraren. Konfigurera begäran efter behov och klicka sedan på **[!UICONTROL Advanced Delivery Options]**.

1. I popup-fönstret klickar du på **[!UICONTROL FTP]** anger du sedan ftp-platsen (inklusive [!DNL sftp://] protokoll, som [!DNL sftp://ftp.omniture.com]) via port 22.

   Inklusive [!DNL sftp://] -protokoll tillåts endast när SFTP används. Vanliga FTP-begäranden ska utelämna protokollprefixet (till exempel [!DNL ftp.omniture.com] i stället för [!DNL ftp://ftp.omniture.com]).

1. Ange namnet på mappen som du vill placera filen i fältet Mapp. En mapp krävs.
1. Ange samma användarnamn och lösenord som används i steg 2.
1. Klicka på **[!UICONTROL Send]**.

Kommandot sftp PUT placerar en temporär fil med filtillägget .part i den angivna katalogen. När överföringen är klar får filtillägget ett nytt namn till det slutliga tillägget, där det är klart att användas.

Alternativt kan [!DNL sftp+norename://] kan anges i stället för [!DNL sftp://] om du vill överföra filen direkt med det slutliga namnet, utan ett tillfälligt [!DNL .part] filnamn vid överföring. Detta är lämpligt när SFTP-servern hanterar namnbyte av filer vid automatisk överföring och det inte finns någon risk för att filen bearbetas innan överföringen är klar.
