---
description: Dataflöden är en export av klickströmsdata som tas emot av Adobe som erbjuder både standardflöden och anpassade dataflöden.
keywords: ftp;sftp
title: Datafeeds
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
source-git-commit: 0916ef4ddc2ca65f01721f4d79d7af825dcf50e3
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Datafeeds

Dataflöden är en export av klickströmsdata som tas emot av Adobe som erbjuder både standarddata och anpassade data [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md).

Om du har köpt Adobe Data warehouse, [!UICONTROL Standard Data Feeds] kan ni skapa egna Analytics-dataflöden. De kan skickas till vilket FTP-konto som helst (antingen ett som har konfigurerats av Adobe eller ett externt FTP). Adobe Engineering Services erbjuder skräddarsydda [!UICONTROL Data Feeds] som kan skickas på praktiskt taget alla sätt.

>[!NOTE]
>
>Följande information är relaterad till måltyperna FTP och SFTP. FTP och SFTP är äldre måltyper. När du konfigurerar en datafeed bör du använda en säkrare måltyp i molnet.


[!UICONTROL Data Feed] FTP-konton tillåter 10 GB (som standard). Alla andra FTP-standardkonton är som standard 50 MB. I de fall där klienterna använder FTP-kontot för korrekt avsedd användning kan vissa användare med hög trafik snabbt fylla i dessa konton. När ett FTP-konto är fullt kan inga ytterligare filer skickas till dem. Därför skickas alla filer till det FTP-kontot ( [!UICONTROL Data Feeds], data warehouse-förfrågningar o.s.v.) levereras inte. Detta är en anledning till att det är viktigt att hantera ditt FTP-konto i Adobe genom att ta bort filer som har tagits emot och laddats ned.

När ett FTP-konto är fullt bör du hämta och ta bort de aktuella filerna och meddela Adobe att utrymmet har tagits bort. Adobe kan sedan skicka om filer som inte har levererats. Vissa verktyg, till exempel data warehouse, låter användarna skicka om dessa filer. Det är inte säkert att Adobe måste delta. Om ditt FTP-konto verkar ha fyllts i ofta kan du kontakta Adobe kundtjänst, som kan föreslå leveransalternativ som kan öka kontots utrymme och filnummerkvot.
