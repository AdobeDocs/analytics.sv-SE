---
description: Kombinera både tidsstämplade och tidsstämplade data i en enda rapportserie.
title: Tidsstämplar (valfritt)
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Tidsstämplar (valfritt)

Kombinera både tidsstämplade och tidsstämplade data i en enda rapportserie.

Tidsstämplar Valfritt gör att du kan:

* Blanda tidsstämplade och tidsstämplade data i samma globala rapportserie.
* Skicka tidsstämplade data från en mobilapp till en global rapportserie.
* Uppgradera program så att de kan använda offline-spårning utan att behöva skapa en ny rapportserie.

>[!WARNING]
>
>Om du använder Tidsstämplar som valfria ska du inte ange [s.visitorID](/help/implement/vars/config-vars/visitorid.md) för data som redan är tidsstämplade. Detta kan leda till inordnade data och negativt påverka tidsberäkningar (t.ex. tidsåtgång), attribuering (eVarnas beständighet), antal besök/besök och kundvägsrapporter.

>[!NOTE]
>
>Tidsstämpelaktiverade sessionsdata sparas i upp till 92 dagar. Det innebär att ett besök/en session kommer att hållas öppet i 92 dagar medan en ytterligare träff - som inte är 30 minuter efter föregående träff (i träfftid) - fortfarande kan tas med i samma besök/session. Alla &quot;gamla&quot; träffar som tas emot i fel ordning ger &quot;okända&quot; resultat eftersom ett antal faktorer (segmentering, allokering, utgångsdatum osv.) påverka huruvida dessa träffar kommer att ingå i rapporteringen eller inte.

## Nya rapportsviter {#section_095A7CFBD280494593B9BEC1592B73A6}

* Om det skapas från en mall används som standard tidsstämplar som valfria i en ny rapportserie.

  (Du kan skapa en ny rapportserie från en mall på **Admin > Rapportsviter > Skapa nytt > Rapportsviten**.)
* Om du kopierar från en befintlig rapportserie ärver den nya rapportsviten tidsstämpelinställningen från originalet, inklusive:

   * **Tidsstämplar är inte tillåtna** (inställning för s.visitorID stöds)
   * **Tidsstämplar krävs** (inställningen s.visitorID stöds inte)
   * **Tidsstämplar är valfria** (inställningen s.visitorID stöds men inte i tidsstämplade träffar)

## Ändra befintliga rapportsviter till tidsstämplar (valfritt) {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Gå till **Admin > Rapportsviter > Redigera inställningar > Allmänt > Tidsstämpelkonfiguration**.
1. Markera rutan **Konvertera markerade rapportsviter till tidsstämplar (valfritt)**.

   Detta ändrar rapportsviten till Tidsstämplar (valfritt).

>[!NOTE]
>
>Om en rapportsvit var inställd på **Tidsstämplar (valfritt)** kan du ändra den till en annan inställning genom att kontakta Adobe kundtjänst.
