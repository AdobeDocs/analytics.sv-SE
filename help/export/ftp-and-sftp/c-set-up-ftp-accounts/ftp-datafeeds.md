---
description: Dataflöden är en export av klickströmsdata som tas emot av Adobe och som erbjuder både standardflöden och anpassade dataflöden.
keywords: ftp;sftp
title: Dataflöden
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: fc14751c810019c5257a23a8a598b16f42ed10ee

---


# Dataflöden

Dataflöden är en export av klickströmsdata som tas emot av Adobe och som erbjuder både standardflöden och anpassade [dataflöden](/help/export/analytics-data-feed/data-feed-overview.md).

Om du har köpt Adobe Data Warehouse kan [!UICONTROL Standard Data Feeds] du skapa egna Analytics-dataflöden. De kan skickas till vilket FTP-konto som helst (antingen ett som har konfigurerats av Adobe eller ett externt FTP). Adobe Engineering Services erbjuder skräddarsydda tjänster [!UICONTROL Data Feeds] som kan skickas med praktiskt taget alla medel.

[!UICONTROL Data Feed]FTP-konton tillåter 10 GB (som standard). Alla andra FTP-standardkonton är som standard 50 MB. I de fall där klienterna använder FTP-kontot för korrekt avsedd användning kan vissa användare med hög trafik snabbt fylla i dessa konton. När ett FTP-konto är fullt kan inga ytterligare filer skickas till dem. Därför levereras inga filer som levereras till det FTP-kontot ( [!UICONTROL Data Feeds], datalagerbegäranden o.s.v.). Detta är en anledning till att det är viktigt att hantera ditt Adobe FTP-konto genom att ta bort filer som har tagits emot och laddats ned.

När ett FTP-konto är fullt bör du hämta och ta bort de aktuella filerna och meddela Adobe att utrymmet har tagits bort. Adobe kan sedan skicka om filer som inte har levererats. Vissa verktyg, till exempel datalager, låter användarna skicka om filerna. Att skicka vidare kräver kanske inte att Adobe deltar. Om ditt FTP-konto verkar ha fyllts i ofta kontaktar du Adobes kundtjänst, som kan föreslå leveransalternativ som kan öka kontots utrymme och filnummerkvot.
