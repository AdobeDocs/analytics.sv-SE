---
description: Kombinera både tidsstämplade och tidsstämplade data i en enda rapportserie.
title: Konfiguration av tidsstämplar
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Konfiguration av tidsstämplar

Administratörssidan [!UICONTROL Timestamps configuration] gör att du kan aktivera **[!UICONTROL Timestamps optional]** för en eller flera rapportsviter. Med den här inställningen kan du kombinera både tidsstämplade och tidsstämplade data i en enda rapportserie.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Timestamps optional]**

## Aktuell tidsstämpelinställning

I det här avsnittet visas din aktuella tidsstämpelkonfiguration för den valda rapportsviten. Det kan vara ett av tre möjliga värden:

* **Tidsstämplar tillåts inte (inställning `visitorID` stöds)**
* **Tidsstämplar krävs (inställningen `visitorID` stöds inte)**
* **Tidsstämplar är valfria (inställning `visitorID` stöds men inte för tidsstämplade träffar)**

Under den här texten finns en kryssruta med namnet **[!UICONTROL Convert selected report suites to Timestamps optional]**. Markera den här kryssrutan och välj sedan **[!UICONTROL Save]** Aktiverar [!UICONTROL Timestamps optional] för de valda rapportsviterna.

## Tidsstämplar tillåts inte

När du skickar data till en rapportserie med den här tidsstämpelkonfigurationen är tidsstämpeln när Adobe bearbetningsservrar tar emot träffen. Om du försöker ange variabeln [`timestamp`](/help/implement/vars/page-vars/timestamp.md) tas träffen bort permanent.

## Tidsstämplar krävs

När du skickar data till en rapportserie med den här tidsstämpelkonfigurationen måste alla träffar innehålla variabeln [`timestamp`](/help/implement/vars/page-vars/timestamp.md). Om en träff saknar en `timestamp`-implementeringsvariabel tas träffen bort permanent.

Tidsstämpelaktiverade sessionsdata sparas i upp till 92 dagar. Med andra ord&quot;hålls ett besök öppet&quot; i 92 dagar, vilket innebär att ytterligare träffar kan tas med i samma besök/session. Du kan lägga till data i befintliga sessioner, men Adobe rekommenderar att du lägger till träffar efter besökare. Träffar som tas emot i fel ordning per besökare kan ge oväntade rapportresultat, men många av dessa begränsningar begränsas av rapporttidsbearbetning.

## Tidsstämplar (valfritt)

Inställningen [!UICONTROL Timestamps optional] gör att du kan integrera och rapportera i flera rapportsviter med eller utan variabeln [`timestamp`](/help/implement/vars/page-vars/timestamp.md). Exempel på lämpliga användningsområden för [!UICONTROL Timestamps optional] är:

* Blanda tidsstämplade och tidsstämplade data i samma globala rapportserie
* Skicka tidsstämplade data från en mobilapp till en global rapportserie
* Uppgradera program för att använda offline-spårning utan att behöva skapa en ny rapportserie

Den här inställningen är aktiverad som standard för alla nya rapportsviter, såvida inte den nya rapportsviten kopierades från en rapportserie med en annan tidsstämpelkonfigurationsinställning.

>[!WARNING]
>
>Om du använder [!UICONTROL Timestamps optional] ska du inte ange [`visitorID`](/help/implement/vars/config-vars/visitorid.md) för tidsstämplade data. Den här åtgärden kan leda till inaktuella data och negativt påverka tidsberäkningar (t.ex. hur lång tid som har använts), attribuering, antal besök/besök och rapporter om kundens kundresa.

När du har aktiverat [!UICONTROL Timestamps optional] kan du inte inaktivera det i det här gränssnittet. Om du, i det osannolika scenariot, vill växla tillbaka till en annan inställning för tidsstämpelkonfiguration, kontaktar du Adobe kundtjänst.
