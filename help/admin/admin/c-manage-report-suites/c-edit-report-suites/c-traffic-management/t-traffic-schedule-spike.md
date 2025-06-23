---
title: Schemalägg en trafiktoppning
description: Samarbeta med Adobe för att säkerställa att högtrafikhändelser inte drabbas av fördröjning.
feature: Report Suite Settings
role: Admin
exl-id: a6bbd975-6d31-40f5-8f80-491ec3a5c5f5
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 0%

---

# Schemalägg en trafiktoppning

Adobe försöker att samarbeta med kunder för att säkerställa att ett trafikrelaterat evenemang lyckas. Att schemalägga trafiktoppar är startpunkten i den partnerprocessen. I avsnittet Schemalägg inkapsling kan du informera Adobe om tillfälliga trafiktoppar så att lämpliga resurser kan tilldelas för att hantera dem. Du kan uppskatta tidigare serveranrop för att få en bättre uppfattning om storleken på den trafikökning du behöver schemalägga.

Avancerad databalansering på serversidan med flera dedikerade medarbetare används för att säkerställa att alla kunder har de senaste rapporterna som är möjliga. När ni informerar Adobe om trafiktoppar kan Adobe se till att den plötsliga trafikökningen blir en positiv upplevelse. Underlåtenhet att meddela Adobe om trafikökningar kan öka latensen under kritiska rapporteringsperioder.

{{$include /help/_includes/traffic-lead-time.md}}

## Schemalägg en trafiktoppning

Så här schemalägger du en trafiktopp:

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Report suites]**.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Traffic Management]** > **[!UICONTROL Schedule Spike]**.
1. (Valfritt) Du kan uppskatta tidigare serveranrop för att få en bättre uppfattning om hur stor trafikökning du behöver schemalägga.

   Du kan till exempel få förra årets dagliga serveranrop som genomsnitt under en viss tidsperiod, plus en förväntad ökning av serversamtalsvolymen för det här året. Du kan sedan schemalägga en trafiktopp baserat på den här multiplikationsfaktorn.

   1. I området **[!UICONTROL Past Server Calls]** väljer du ett start- och slutdatum för de valda rapportsviterna.

      Mängden [!UICONTROL **Peak Day**], [!UICONTROL **Peak Day Server Call**] och [!UICONTROL **Daily Average of Server Call**] genereras.

   1. Ange ett värde för multiplikationsfaktorn och välj sedan **[!UICONTROL Click to multiply and set]**.

      Värdet för var och en av kolumnerna multipliceras för varje rapportserie.
1. I området [!UICONTROL **Set Spike Parameters**], i fältet **[!UICONTROL Spike Start Date]**, anger du det datum då du förväntar dig att trafikspiken ska starta.
1. I fältet **[!UICONTROL Spike End Date]** anger du det datum då du förväntar dig att trafiktoppen ska sluta.
1. I fältet **[!UICONTROL Peak Day Server Calls]** anger du den totala förväntade toppnivån för sidvisningar per dag under trafiktoppningsperioden.
1. I fältet **[!UICONTROL Peak Hour Server Calls]** anger du den totala förväntade toppnivån för sidvisningar per timme under trafiktoppningsperioden.
1. Välj **[!UICONTROL Submit]**.

   Se till att du anger det totala antalet förväntade sidvyer, inte bara ytterligare sidvyer.

   >[!NOTE]
   >
   >Om du vill schemalägga en trafikökning anger du ett telefonnummer i kontaktinformationen så att Adobe kan kontakta dig med frågor om det behövs.

## Därför är det viktigt att alltid schemalägga trafiktoppar

När kunderna meddelar Adobe om trafiktoppar för varje rapporteringsprogram gör Adobe allt som är möjligt för att säkerställa att det får minimal påverkan på rapporteringen.

* Organisationer som har schemalagda trafiktoppar får prioritet om data börjar bli latenta. Vikten av detta koncept är särskilt viktig under semestersäsongen, eftersom många organisationer planerar trafiktoppar.
* Om Adobe noterar att ni avsevärt överskattat/underskattat förväntad trafik jämfört med tidigare år kan de kontakta er för att säkerställa att ni är korrekta.
* Det är viktigt att schemalägga en trafiktopp varje år, även om organisationen får samma toppar varje år. Många organisationer släpper nya appar, kombinerar rapportsviter och migrerar/kasserar rapportsviter under året. Adobe vet inte vilka rapporteringsprogram som kan ta emot extra trafik, såvida inte ni planerar en trafikökning varje gång. Även om Adobe använder historiska data för att få en uppskattning är det viktigt att eventuella extra resurser läggs till i rätt rapportsvit.

## Åtgärder som din organisation kan vidta

Adobe vill säkerställa att era erfarenheter av aktuell rapportering är enhetliga. Adobe rekommenderar starkt följande för att kunna utföra detta:

* Schemalägg produktionstid för alla trafiktoppar. **Det är särskilt viktigt att alla trafiktoppar som förväntas under november-december schemaläggs till den 15 september**. Om du missar deadline, schemalägg toppen så snart som möjligt. Mindre ledtid är bättre än inget alls, och Adobe arbetar med de aktuella resurserna för att bäst passa era rapportsviter.
* Om Adobe kontaktar dig angående en schemalagd trafiktoppning ska du informera dig om realtidsrapportering eller fullständig bearbetningsrapportering är viktigare. Vissa organisationer förlitar sig mer på realtidsrapportering än andra. Genom att förstå vilken typ av rapportering du använder kan Adobe prioritera på rätt sätt.
* De viktigaste rapporterna och när du hämtar dem kan du kommunicera med ditt Adobe-kontoteam och hjälpa dem att rekommendera åt dig.
