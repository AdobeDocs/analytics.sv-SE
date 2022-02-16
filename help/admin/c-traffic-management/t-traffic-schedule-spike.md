---
title: Schemalägg en trafiktopp
description: Samarbeta med Adobe för att säkerställa att högtrafikhändelser inte får någon fördröjning.
feature: Traffic Management
exl-id: a6bbd975-6d31-40f5-8f80-491ec3a5c5f5
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Schemalägg en trafiktopp

Adobe försöker att samarbeta med kunder för att säkerställa att ett trafikrelaterat evenemang lyckas. Att schemalägga trafiktoppar är startpunkten i den partnerprocessen. I avsnittet Schemalägg inkapsling kan du informera Adobe om tillfälliga trafiktoppar så att lämpliga resurser kan tilldelas för att hantera dem.

Avancerad databalansering på serversidan med flera dedikerade medarbetare används för att säkerställa att alla kunder har de senaste rapporterna som är möjliga. När er organisation informerar Adobe om trafiktoppar kan Adobe se till att den plötsliga trafikökningen är en positiv upplevelse. Underlåtenhet att meddela Adobe om trafikökningar kan öka latensen under kritiska rapporteringsperioder.

Läs informationen om [Ledtid som krävs för trafikökningar](/help/admin/c-traffic-management/traffic-lead-time.md) innan du schemalägger en trafikspik.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Report suites]**.
1. Välja en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Traffic Management]** > **[!UICONTROL Schedule Spike]**.
1. I **[!UICONTROL Spike Start Date]** anger du det datum då du förväntar dig att trafiktoppen ska börja.
1. I **[!UICONTROL Spike End Date]** anger du det datum då du förväntar dig att trafikökningen ska sluta.
1. I **[!UICONTROL Expected Daily Page Views During Spike]** anger du den totala förväntade dagliga sidvisningen under trafikspikperioden och klickar sedan **[!UICONTROL Submit]**.

   Se till att du anger det totala antalet förväntade sidvyer, inte bara ytterligare sidvyer.

   >[!NOTE]
   >
   >Om du vill schemalägga en trafikökning anger du ett telefonnummer i din användares kontaktinformation så att Adobe kan kontakta dig med frågor om det behövs.

## Därför är det viktigt att alltid schemalägga trafiktoppar

När kunderna informerar Adobe om trafiktoppar för varje rapporteringsprogram gör Adobe allt som är möjligt för att säkerställa att det får minimal inverkan på rapporteringen.

* Organisationer som har schemalagda trafiktoppar får prioritet om data börjar bli latenta. Vikten av detta koncept är särskilt viktig under semestersäsongen, eftersom många organisationer planerar trafiktoppar.
* Om Adobe meddelar att ni avsevärt har överskattat/underskattat den förväntade trafiken jämfört med tidigare år kan de kontakta er för att säkerställa att ni är korrekta.
* Det är viktigt att schemalägga en trafiktopp varje år, även om organisationen får samma toppar varje år. Många organisationer släpper nya appar, kombinerar rapportsviter och migrerar/kasserar rapportsviter under året. Adobe kan inte veta vilka rapporteringsprogram som får extra trafik om inte organisationen schemalägger en trafiktopp varje gång. Även om Adobe använder historiska data för att få en uppskattning är det viktigt att eventuella extra resurser läggs till i rätt rapportsvit.

## Åtgärder som din organisation kan vidta

Adobe vill säkerställa att era erfarenheter av aktuell rapportering är enhetliga. Adobe rekommenderar starkt följande för att kunna göra detta så effektivt som möjligt:

* Schemalägg alla trafikspikar enligt [Ledtid som krävs för trafikökningar](traffic-lead-time.md). **Det är särskilt viktigt att alla trafiktoppar som förutses under november-december planeras till den 15 september**. Om du missar deadline, schemalägg toppen så snart som möjligt. Mindre ledtid är bättre än inget, och Adobe arbetar med de aktuella resurserna för att bäst kunna hantera era rapportsviter.
* Om Adobe kontaktar dig angående en schemalagd trafiktoppning ska du informera dig om realtidsrapportering eller fullständig bearbetningsrapportering är viktigare. Vissa organisationer förlitar sig mer på realtidsrapportering än andra. Att förstå vilken typ av rapportering du använder kan hjälpa Adobe att prioritera på rätt sätt.
* De viktigaste rapporterna och när du hämtar dem kan du kommunicera med din kontoansvarige för att hjälpa dem att rekommendera åt dig.
