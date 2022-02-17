---
title: Bearbetningstid för klassificeringsimporterare
description: Förstå tidsramen i Adobe bearbetar klassificeringsfiler och hur man minimerar bearbetningstiden.
feature: Classifications
exl-id: 6b8b87f1-5dbc-46b8-9912-0e3086ff4b2a
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---

# Bearbetningstid för klassificeringsimporterare

Bearbetningstiden för en klassificeringsfil varierar beroende på filens storlek och det totala antalet filer som bearbetas i Adobe. Klassificeringar tar vanligtvis inte längre tid än 72 timmar. Fall av omfattande klassificeringsanvändning i organisationer som använder Adobe Analytics kan dock medföra att filerna tar längre tid än 72 timmar. Adobe har stor användning av klassificeringar under flera månader fram till semestersäsongen.

Om du vill se om en klassificeringsfil är klar gör du följande:

1. Logga in på Adobe Analytics och navigera sedan till **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Välj rapportsviten och datauppsättningen i fråga.
3. Om bearbetningen ännu inte är klar visas något av följande meddelanden:

   * ![Meddelande](assets/icon_notice_notice.gif) Den valda rapporten har en klassificeringsimport som bearbetas.
   * ![Meddelande](assets/icon_notice_notice.gif) Den valda rapporten innehåller klassificeringsdata som ännu inte har spridits till alla servrar.

Om du vill minimera tiden för klassificeringsimporten rekommenderar Adobe starkt att du följer följande riktlinjer:

* **Använd klassificeringsregelverktyget när det är möjligt**: Klassificeringsregelbyggaren behandlar data på ett annat sätt än den traditionella klassificeringsimporten. Om klassificeringsdata följer specifika mönster rekommenderar vi att du använder den här funktionen.
* **Överför endast ändrade rader**: Detta innebär att det går mycket snabbare att bearbeta klassificeringsfiler eftersom de inte sorteras igenom oförändrade rader. Adobe rekommenderar starkt att du bara överför ändrade rader.
* **Planera framåt**: Börja överföra klassificeringsdata så snart som möjligt, särskilt om dessa data används under semestersäsongen.
* **Kombinera klassificeringsfiler där det är möjligt**: Om en enskild variabel har flera klassificeringar överför du en fil med alla tillämpliga klassificeringar. Undvik att överföra flera klassificeringar för samma variabel.
* **Undvik att överföra filer som är större än 500 MB**: Om du hanterar stora mängder klassificeringsdata rekommenderar Adobe att du delar upp filer i 100 MB-500 MB-filer.
* **Undvik att överföra stora mängder filer till FTP**: Om du tänker överföra samma filer till flera rapportsviter via FTP bör du begränsa antalet filer som överförs samtidigt. Adobe rekommenderar att antalet filer multiplicerat med antalet tillämpliga rapportsviter är mindre än 1 000. Om du behöver överföra 100 filer till 100 rapportsviter är det totala antalet filer 10 000. I stället för att ladda upp alla 100 filer samtidigt kan du dela upp dem i 10 grupper om 10 filer i taget.
* **Överför små filer via webbläsarimporteraren**: Om du har en fil som är mindre än 1 MB (färre än 50 000 rader) rekommenderar Adobe att du använder webbläsarimporteraren. Webbläsarimport är nästan alltid snabbare än FTP-import.
