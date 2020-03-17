---
description: Kombinera både tidsstämplade och tidsstämplade data i en enda rapportserie.
title: Tidsstämplar (valfritt)
topic: Admin tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Tidsstämplar (valfritt)

Kombinera både tidsstämplade och tidsstämplade data i en enda rapportserie.

Tidsstämplar Valfritt gör att du kan:

* Blanda tidsstämplade och tidsstämplade data i samma globala rapportserie.
* Skicka tidsstämplade data från en mobilapp till en global rapportserie.
* Uppgradera program så att de kan använda offline-spårning utan att behöva skapa en ny rapportserie.

> [!IMPORTANT] Om du använder Tidsstämplar som valfria ska du inte ange [s.visitorID](/help/implement/vars/config-vars/visitorid.md) för data som redan är tidsstämplade. Detta kan leda till inordnade data och negativt påverka tidsberäkningarna (t.ex. tidsåtgång), attribuering (eVar persistence), antal besök/besök och kundvägsrapporter.

> [!NOTE] Tidsstämpelaktiverade sessionsdata sparas i upp till 92 dagar. Det innebär att ett besök/en session kommer att hållas öppet i 92 dagar medan en ytterligare träff - som inte är 30 minuter efter föregående träff (i träfftid) - fortfarande kan tas med i samma besök/session. Alla &quot;gamla&quot; träffar som tas emot i fel ordning ger &quot;okända&quot; resultat eftersom ett antal faktorer (segmentering, allokering, utgångsdatum osv.) påverka huruvida dessa träffar kommer att ingå i rapporteringen eller inte.

## Nya rapportsviter {#section_095A7CFBD280494593B9BEC1592B73A6}

* Om det skapas från en mall används som standard tidsstämplar som valfria i en ny rapportserie.

   (Du kan skapa en ny rapportserie från en mall på **Admin > Rapportsviter > Skapa nytt > Rapportsviten**.)
* Om du kopierar från en befintlig rapportserie ärver den nya rapportsviten tidsstämpelinställningen från originalet, inklusive:

   * **Tidsstämplar tillåts** inte (inställning för s.visitorID stöds)
   * **Tidsstämplar krävs** (inställningen s.visitorID stöds inte)
   * **Tidsstämplar är valfria** (inställningen s.visitorID stöds men inte för tidsstämplade träffar)

## Ändra befintliga rapportsviter till tidsstämplar (valfritt) {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Gå till **Admin > Report Suites > Edit Settings > General > Timestamp Configuration**.
1. Markera rutan **Konvertera markerade rapportsviter till tidsstämplar (valfritt** ).

   Detta ändrar rapportsviten till Tidsstämplar (valfritt).

> [!NOTE] Om en rapportsvit är inställd på **Tidsstämplar (valfritt**) kan du ändra den till någon annan inställning genom att kontakta Adobe Client Care.

