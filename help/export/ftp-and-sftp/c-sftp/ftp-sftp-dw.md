---
description: Adobe stöder export av datalagerbegäranden till SFTP-servrar.
keywords: ftp;sftp
title: Skicka datalagerbegäranden till SFTP-servrar
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Skicka datalagerbegäranden till SFTP-servrar

Adobe stöder export av datalagerbegäranden till SFTP-servrar.

Se till att följande uppgifter är slutförda:

Adobe stöder export av datalagerbegäranden till SFTP-servrar, förutsatt att följande uppfylls:

* [!DNL sftp://] -protokollet anges i värdfältet (till exempel [!DNL sftp://ftp.example.com]) och ENDAST port 22 används när en datalagerrapport begärs.

   Du kan också använda [!DNL sftp+norename://] alternativet enligt beskrivningen nedan.

* Adobes [!DNL authorized_keys] fil finns i [!DNL .ssh] katalogen i rotkatalogen för den användare du loggar in med

* Målet är inte till [!DNL ftp.omniture.com]. SFTP-protokoll mellan Adobes interna servrar stöds inte.
* Målet stöder enfaktorsautentisering (PKI). Om det finns en tvåfaktorskontroll misslyckas leveransen av rapporten. Kontrollera att servern inte är konfigurerad att försöka utföra tvåfaktorsautentisering. Adobe Analytics kräver att bara nyckeln och ingenting annat används för att logga in.
* Adobe stöder SSHv2-kryptering och återgår till SSHv1 (endast RSA-nyckeln).

Så här skickar du en [!DNL Data Warehouse] begäran via SFTP:

1. Få fram [!DNL authorized_keys] filen genom att be någon av era användare kontakta Kundtjänst.
1. När den här filen har hämtats loggar du in på FTP-platsen med samma autentiseringsuppgifter som används för [!DNL Data Warehouse] begäran.
1. I rotkatalogen navigerar du till mappen med namnet [!DNL .ssh] (om det inte finns någon) och placerar [!DNL authorized_keys] filen där.

1. Gå till begärandehanteraren [!DNL Data Warehouse] . Konfigurera begäran efter behov och klicka sedan på **[!UICONTROL Advanced Delivery Options]**.

1. I popup-fönstret klickar du på **[!UICONTROL FTP]** och anger sedan ftp-platsen (inklusive [!DNL sftp://] protokollet, till exempel [!DNL sftp://ftp.omniture.com]) via port 22.

   Inkludering av [!DNL sftp://] protokollet tillåts endast när SFTP används. Vanliga FTP-begäranden ska utelämna protokollprefixet (till exempel, [!DNL ftp.omniture.com] i stället för [!DNL ftp://ftp.omniture.com]).

1. Ange namnet på mappen som du vill placera filen i fältet Mapp. En mapp krävs.
1. Ange samma användarnamn och lösenord som används i steg 2.
1. Klicka på **[!UICONTROL Send]**.

Kommandot sftp PUT placerar en temporär fil med tillägget .part i den angivna katalogen. När överföringen är klar får filtillägget ett nytt namn till det slutliga tillägget, där det är klart att användas.

Du kan också [!DNL sftp+norename://] ange det i stället för [!DNL sftp://] att överföra filen direkt med det slutgiltiga namnet, utan ett temporärt [!DNL .part] filnamn under överföringen. Detta är lämpligt när SFTP-servern hanterar namnbyte av filer vid automatisk överföring och det inte finns någon risk för att filen bearbetas innan överföringen är klar.
