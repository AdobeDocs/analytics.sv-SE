---
title: Felsökning av klassificeringsimporterare
description: Vanliga överföringsproblem vid användning av klassificeringsimporteraren.
feature: Classifications
exl-id: de3e9eca-9264-4711-b73a-4a1a3dd16715
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 0%

---

# Felsökning av klassificeringsimporterare

{{classification-importer-deprecation}}

De vanligaste problemen vid överföring av klassificeringsdata till Adobe.

## Felaktigt filformat eller filtillägg

Klassificeringar kräver en viss filtyp och ett visst format för att kunna överföras. Om den sparas felaktigt genereras ett fel och inga rader bearbetas. Felet som returnerades är ofta *&quot;Den första kolumnen måste vara nyckeln&quot;*, men kan vara valfritt antal fel. Kontrollera följande:

* **Överför ett kalkylblad (.xlsx) i stället för en .tab- eller .txt-fil**: Du kan få felmeddelandet *&quot;Den första kolumnen måste vara nyckeln&quot;* när du överför klassificeringsfiler i ett felaktigt format. Klassificeringsimporteraren kan inte hantera .xls- eller .xlsx-filer. I dialogrutan Spara som i Excel anger du rätt typ av Spara som:
   * Använd filformatet `Text (Tab delimited) (*.txt)` i Windows
   * Använd filformatet `Windows Formatted Text` i Mac.
* **Om du ändrar filnamnstillägget efter att ha sparat det som en arbetsbok**: Om du försöker byta namn på ett filnamnstillägg direkt genereras en ogiltig arbetsbok. Använd bara Excel-funktionen Spara som eller redigera klassificeringar i en textredigerare som Anteckningar++.
* **Använder versaltillägg**: Versaltillägg (till exempel `fileupload.TXT`) fungerar inte. Byt namn på filen till ett filtillägg med gemener (`fileupload.txt`).
* **Teckenkodning som inte matchar**: Kontrollera att kodningen för den sparade klassificeringsöverföringen matchar den ursprungliga kodningen när mallen hämtades. Om du överför en UTF-16-fil när den ursprungligen kodades i UTF-8, ger överföringar oväntade resultat. Adobe rekommenderar att du överför filer med UTF-8 utan byteordningsmärken.

## Ogiltigt filinnehåll

Om överföringsfilen är korrekt formaterad försöker den att importera så många giltiga rader som möjligt. Några vanliga problem med klassificeringsdata:

* **Rader som redan är klassificerade**: Om du försöker överföra rader som redan är klassificerade med samma värde returnerar importeraren rader som inte hade någon effekt. Det här resultatet förväntas eftersom klassificeringar inte omklassificerar ett nyckelvärde med samma klassificering. Det är ett meddelande i stället för ett fel. Du behöver inte oroa dig för om du inte ändrar alla rader i en exportfil. Adobe rekommenderar att du bara överför ändrade rader.
* **Rubriken matchar inte variabeln som överförs**: Om du hämtar en klassificeringsmall för spårningskoddimensionen och försöker överföra den till en eVar-klassificering misslyckas den. Använd bara exportfiler för de specifika variabler som de exporterades från.
* **En nyckel eller ett klassificeringsvärde innehåller värdet 0**: Klassificeringar kan inte skilja värdet 0 från en tom cell, så det kan inte klassificera det här värdet. Mer information finns i [Vanliga frågor om klassificeringsimporteraren](importer-faq.md).
* **Klassificeringsfilen innehåller kommatecken eller specialtecken**: Se [Vanliga frågor om klassificeringsimporteraren &#x200B;](importer-faq.md) för information om hur du kan undvika värden.
* **Extra flikar i den överförda filen**: När du redigerar klassificeringsfiler kan en extra flik ibland oavsiktligt komma in. Varje rad kräver ett identiskt antal flikar för att bearbetas korrekt. Om du vill kontrollera om det finns extra flikar i filen markerar du all text i en textbehandlare och kontrollerar att det inte finns några rader med extra utrymme i slutet.
* **Det finns dubblettnyckelvärden i filen**: Varje nyckelvärde kan bara ha en klassificering per kolumn. Om du försöker klassificera samma värde flera gånger genereras ett fel.
* **Underklassificeringar finns och är felaktigt konfigurerade**: Om det finns underklassificeringar kontrollerar du följande:
   * Alla underklassificeringsvärden har ett överordnat klassificeringsvärde
   * Inga två underklassificeringar refererar till samma överordnade klassificeringsvärde
* **Kolumnmatchningsfel**: Felmeddelandet *&quot;Nyckeln på raden innehåller för många kolumner&quot;* om det finns ett ogiltigt antal kolumner på en rad. Du har till exempel tre kolumner i din klassificeringsöverföring och variabeln har bara en klassificering. Validera överföringsfilen för att kontrollera att antalet kolumner inte är större än antalet klassificeringar som har konfigurerats för variabeln.

## Felsöka FTP-import

Följande är vanliga orsaker till varför FTP-klassificeringar inte behandlar överförda filer:

* **Saknad .fin-fil**: Skapa ett tomt textdokument på skrivbordet och byt namn på filnamnstillägget från .txt till .fin. Namnet på den här .fin-filen måste matcha namnet på klassificeringsfilen i fråga. Om FTP-filnamnet till exempel är `fileupload.tab` ger du din .fin-fil namnet `fileupload.fin`. När .fin-filen har överförts försvinner båda filerna.
* **Överför .fin-fil före klassificeringsfilen**: Ibland skapas en .fin-fil innan klassificeringsfilen har överförts till FTP-platsen. Bearbetningen kan misslyckas när filer överförs i fel ordning. Ta bort båda filerna, lägg till klassificeringsfilen först och sedan .fin-filen när klassificeringsfilen har överförts helt.
* **Filstorleken är för stor**: Adobe rekommenderar att klassificeringsfilernas storlek hålls så liten som möjligt för att säkerställa snabb bearbetning.
* **Befintliga filer som redan bearbetar**: Om flera filer överförs för samma variabel och rapportserie avbryts bearbetningen av den gamla filen till förmån för den nya. Om du överför klassificeringar med flera filer väntar du på bekräftelse på att befintliga filer har bearbetats innan du överför nya.
* **Överförda filer som inte har placerats i rotkatalogen**: Filer som har överförts till Adobe FTP-plats måste placeras i rotkatalogen. Om klassificeringsimportfiler placeras i undermappar hämtas eller bearbetas de inte.

Om du fortfarande har problem med att överföra en klassificeringsfil kontaktar du Adobe kundtjänst.
