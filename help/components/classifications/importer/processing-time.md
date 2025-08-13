---
title: Bearbetningstid för klassificeringsimporterare
description: Förstå tidsramen för Adobe behandlar klassificeringsfiler och hur man minimerar behandlingstiden.
feature: Classifications
exl-id: 6b8b87f1-5dbc-46b8-9912-0e3086ff4b2a
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Bearbetningstid för klassificeringsimporterare

{{classification-importer-deprecation}}

Bearbetningstiden för en klassificeringsfil varierar med filens storlek och det totala antalet filer som bearbetas av Adobe. Klassificeringar tar vanligtvis inte längre tid än 24 timmar. Fall av omfattande klassificering i organisationer som använder Adobe Analytics kan dock ta längre tid än 24 timmar. Adobe ser en stor användning av klassificeringar under flera månader fram till semestersäsongen.

Om du vill se om en klassificeringsfil är klar gör du följande:

1. Logga in på Adobe Analytics och gå sedan till **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Välj rapportsviten och datauppsättningen i fråga.
3. Om bearbetningen ännu inte är klar visas något av följande meddelanden:

   * ![Obs!](assets/icon_notice_notice.gif) Den valda rapporten har en klassificeringsimport som bearbetas.
   * ![Obs!](assets/icon_notice_notice.gif) Den valda rapporten har klassificeringsdata som ännu inte har spridits till alla servrar.

Om du vill minimera tiden för klassificeringsimporten rekommenderar Adobe starkt att du följer följande riktlinjer:

* **Använd klassificeringsregelbyggaren när det är möjligt**: Klassningsregelbyggaren behandlar data på ett annat sätt än den traditionella klassificeringsimporteraren. Om klassificeringsdata följer specifika mönster rekommenderar vi att du använder den här funktionen.
* **Överför endast ändrade rader**: Den här metoden minskar avsevärt den tid det tar att bearbeta klassificeringsfiler, eftersom den inte sorteras igenom oförändrade rader. Adobe rekommenderar att du bara överför ändrade rader.
* **Planera i förväg**: Börja överföra klassificeringsdata så snart som möjligt, särskilt om dessa data används under semestersäsongen.
* **Kombinera klassificeringsfiler där det är möjligt**: Om en enskild variabel har flera klassificeringar överför du en enda fil med alla tillämpliga klassificeringar. Undvik att överföra flera klassificeringar för samma variabel.
* **Undvik att överföra filer över 500 MB**: Om du har att göra med stora mängder klassificeringsdata bör du dela upp filer i 100 MB-500 MB-filer i Adobe.
* **Undvik att överföra stora mängder filer till FTP**: Om du planerar att överföra samma filer till flera rapportsviter via FTP bör du begränsa antalet filer som överförs samtidigt. Adobe rekommenderar att antalet filer multiplicerat med antalet tillämpliga rapportsviter är mindre än 1 000. Om du behöver överföra 100 filer till 100 rapportsviter är det totala antalet filer 10 000. I stället för att ladda upp alla 100 filer samtidigt kan du dela upp dem i 10 grupper om 10 filer i taget.
* **Överför små filer via webbläsarimporteraren**: Om du har en fil som är mindre än 1 MB (färre än 50 000 rader) rekommenderar Adobe att du använder webbläsarimporteraren. Webbläsarimport är nästan alltid snabbare än FTP-import.
