---
product: analytics
audience: end-user
user-guide-title: Exporthandbok för Analytics
breadcrumb-title: Användarhandbok om export
user-guide-description: Lär dig hur du använder dataflöden och Data Warehouse för att hämta data.
source-git-commit: bb068d39f756c4cce06349d0bd969212e19cb33e
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 6%

---


# Adobe Analytics Export Guide {#export}

+ [Exportguide för analyser](home.md)
+ [Versionsinformation för analyser](https://experienceleague.adobe.com/en/docs/analytics/release-notes/latest)
+ Datafeed i Analytics {#analytics-data-feed}
   + [Översikt över dataflöden](analytics-data-feed/data-feed-overview.md)
   + [Skapa en datafeed](analytics-data-feed/create-feed.md)
   + [Hantera dataflöden](analytics-data-feed/df-manage-feeds.md)
   + [Hantera datafeedjobb](analytics-data-feed/df-manage-jobs.md)
   + Innehåll i datafeed {#data-feed-contents}
      + [Översikt över innehåll i datafeed](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [Beräkna mått](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [Referens för datakolumn](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [Sökning efter sidhändelse](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [Dynamiska sökningar](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [Merchandising eVar lookup](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [Specialtecken](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [Sena träffar](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [Vanliga frågor om datafeeds](analytics-data-feed/df-faq.md)
   + [Bästa praxis för dataflöden](analytics-data-feed/data-feeds-best-practices.md)
   + [Felsöka dataflöden](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Data Warehouse - översikt](data-warehouse/data-warehouse.md)
   + [Lägg till Data Warehouse-användargrupp](data-warehouse/t-dw-group.md)
   + Skapa en Data Warehouse-förfrågan {#dw-create-request}
      + [Skapa en Data Warehouse-förfrågan](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [Allmänna inställningar](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [Bygg din rapport](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [Rapportdestination](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [Rapportalternativ](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [Schemaläggningsalternativ](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [E-postmeddelande](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [Begär leveranstid](data-warehouse/delivery-time.md)
   + [Datafil för tabell](data-warehouse/t-tableau.md)
   + [Sortera efter mått](data-warehouse/sorting-by-metric.md)
   + [Hantera Data Warehouse-förfrågningar](data-warehouse/data-warehouse-requests-manage.md)
   + [Komponenter som stöds i Data Warehouse](data-warehouse/component-support.md)
   + [Data Warehouse bästa praxis](data-warehouse/data-warehouse-bp.md)
+ FTP och SFTP {#ftp-and-sftp}
   + [Använd FTP och SFTP med Adobe Experience Cloud](ftp-and-sftp/ftp-overview.md)
   + Konfigurera FTP-konton som är värdbaserade för Adobe {#set-up-ftp-accounts}
      + [Konfigurera FTP-konton - översikt](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [Klassificeringar](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [Datakällor](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [Dataflöden](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Rapporter från Data Warehouse](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Rapporter från Report Builder](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [Ingenjörstjänster har kontakt med FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [FTP-begränsningar och datalagring](ftp-and-sftp/ftp-limits.md)
   + [Ta bort FTP-data och FTP-konton](ftp-and-sftp/ftp-delete.md)
   + [Återställ borttagna FTP-data och FTP-konton](ftp-and-sftp/ftp-restore.md)
   + [Uppgradera Adobe FTP-servrar](ftp-and-sftp/ftp-upgrade.md)
   + [Använd passivt FTP-läge](ftp-and-sftp/ftp-passive.md)
   + [FTP-bearbetningstider](ftp-and-sftp/ftp-processing.md)
   + Secure File Transfer Protocol {#secure-file-transfer-protocol}
      + [Uppgradering av SFTP-tjänster - frågor och svar](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [Secure File Transfer Protocol - översikt](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [Anslut till ett Adobe FTP-konto med SFTP](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [Skicka Adobe-data till ett externt FTP-konto med SFTP](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [Skicka Data Warehouse-förfrågningar till SFTP-servrar](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [Anslut till Adobe via SFTP utan lösenord](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Adobe Analytics API](https://developer.adobe.com/analytics-apis/docs/2.0/)
