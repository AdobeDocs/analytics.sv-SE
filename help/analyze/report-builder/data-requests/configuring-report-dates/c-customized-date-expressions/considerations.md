---
description: Två viktiga saker att tänka på när du använder Anpassa uttryck för att ange datumintervall
title: Anpassade datumöverväganden
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Anpassade datumöverväganden

Två viktiga saker att tänka på när du använder Anpassa uttryck för att ange datumintervall:

* Den dag som rapporten (från och med) körs (eller begäranden uppdateras) avgör vilka data som är tillgängliga.
* Överföringen av rapportens start- och slutdatum påverkar det datumintervall som omfattas av rapporten.

Eftersom tillgängligheten av data är känslig både för rapportens tidsram och det datum då du uppdaterar begäranden i rapporten, måste du köra rapporten på rätt dag för att extrahera den önskade informationen. Exemplen nedan visar båda dessa överväganden.

Anta att du begär [!UICONTROL Page Views] med aggregerad granularitet. I Nordamerika börjar veckan på söndag. Om du vill få uppdaterade rapporter för perioden söndag till lördag (t.ex. den 23 november till den 29 november 2008) kör du rapporten (begäran om uppdatering) söndag (den 30 november) för föregående vecka (den 11/23 till 11/29).

Använd det här anpassade uttrycket:

*Från:* cw-1w *Till:* cw-1d

En analys av det anpassade uttrycket när det innehåller [!UICONTROL End Date] för begäran är den 30/11:

*Från:* cw-1w

den dag i den aktuella veckan som börjar på söndag, 30 november minus sju dagar = dagen i den föregående veckan med början på söndag, 23 november

*Till:* cw-1d

den dag i den aktuella veckan som börjar på söndag, 30 november minus en dag = lördag, 29 november

När det anpassade uttrycket har mappats till kalkylbladet uppdaterar du begäran med funktionen för söndag den 30 november 2008, inklusive [!UICONTROL End Date] för den flytande begäran. Uppgifterna återspeglar den veckovisa perioden.

Om du i stället uppdaterar uttrycket och anger lördag, 29 november som [!UICONTROL End Date] för den flytande begäran, kommer uppgifterna att återspegla vecka 11/16 till 11/22. Detta beror på att referensdatumet för uppdateringsbegäran är en dag tidigare.

Här är skillnaderna när [!UICONTROL End Date] för begäran är 29/11:

*Från:* cw-1w

den dag i den aktuella veckan som börjar på söndag, den 23 november minus sju dagar = dagen i den föregående veckan med början på söndag, den 16 november

*Till:* cw-1d

den dag i den aktuella veckan som börjar på söndag, 23 november minus en dag = lördag, 22 november

I Europa och vissa andra länder börjar veckan på måndag i stället för på söndag. I så fall kan du anpassa kalendern för att ändra startdatumet. (Se [Anpassad kalender](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
