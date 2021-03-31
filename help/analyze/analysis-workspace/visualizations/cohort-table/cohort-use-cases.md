---
description: Använd exempel för kohortanalys.
keywords: Analysis Workspace
title: Användningsexempel på kohortanalyser
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
feature: Visualiseringar
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 0%

---


# [!UICONTROL Cohort Analysis] användningsfall

Använd exempel för [!UICONTROL Cohort Analysis].

## Användningsexempel för appinteraktion {#section_ADEC6EE79F1846319B2E0D9544CC5E40}

Anta att du vill analysera hur användare som installerar din app interagerar med den med tiden. Installerar de den och använder den aldrig? Använder de den en stund och faller sedan bort? Eller förblir de förlovade med tiden?

Du kan skapa en [!UICONTROL Cohort Analysis]-sexmånadersperiod:

**Kornighet**: Månadsvis, från januari 2015 till juni 2015.

**Inkluderingsmått**: Appinstallationer.

**Returmått**: Sessioner eller starter

Besökarna räknas inte som *`engaged`* under efterföljande månader såvida de inte har en session eller åtminstone startar programmet. [!UICONTROL Cohort Analysis] visar sedan mönster som används där  *`App Install`* alltid förekommer i månad 0. Du kan märka att användningen minskar i månad 2, oavsett när användarna installerade appen. (För dem som installerade programmet i januari 2015 är månad 2 mars 2015. För dem som installerade programmet i februari 2015 är månad 2 april 2015 och så vidare.) Med den här analysen kan du skicka ett e-postmeddelande eller ett push-meddelande till alla användare under den andra månaden efter att de har installerat appen för att påminna dem om att använda appen.

## Användningsexempel för prenumeration {#section_FDECB16766CF415BB84AE46BA491FB5F}

Du arbetar på Adobe.com och erbjuder en kostnadsfri prenumeration på Creative Cloud. Målet är att man ska uppgradera från den kostnadsfria versionen till den 30-dagars testversionen eller, i slutändan, den betalda versionen.

**Kornighet**: Månadsvis

**Inkluderingsmått**: Hämta länk

**Returmått**: Köp betald Creative Cloud

Med denna [!UICONTROL Cohort Analysis] kan du till exempel se att mellan 8 % och 10 % av de kostnadsfria Creative Cloud-användarna uppgraderar var som helst under den första månaden efter installationen, oavsett när de installerades. 12-15 % uppgradering under den andra månaden. Efter det kommer en uppgradering av programmet att upphöra: 4-5 % i den tredje månaden, 3-4 % i den fjärde månaden och 1-2 % i den femte månaden.

Eftersom ni vet att ni inte behöver förlora potentiella kunder under den tredje månaden har ni skapat en e-postkampanj som är utformad att skickas ut i mitten av den tredje månaden till ett urval av användare och som erbjuder en rabattkupong på 50 USD till användare som ännu inte har uppgraderat.

Kolla in rapporten från kohortanalysen några månader senare. För kohorter som bildas efter lanseringen av kampanjen har konverteringen till betalda Creative Cloud-prenumerationer under den tredje månaden ökat från 4-5 % till 13-14 %, vilket resulterar i hundratusentals dollar per kohort för varje månadskohort som kommer tre månader framåt från den tidpunkten.

## Komplexa kohortsegment använder skiftläge

En stor hotellkedja vänder sig till flera kundgrupper för att få kampanjer och hålla koll på resultatet. För att identifiera de bästa grupperna med användarkohorter att rikta sig till, vill de skapa mycket specifika kohortgrupper. Med hjälp av de utökade [!UICONTROL Inclusion]- och [!UICONTROL Return]-kriterierna i [!UICONTROL Cohort]-tabeller kan de definiera precis rätt kohortgrupper med flera mätvärden och segment för att identifiera underpresterande kundgrupper för att rikta in dem på kampanjer och erbjudanden för att öka bokningarna.

## App Version Adobes användningsexempel

Ett stort försäkringsföretag driver mycket av kundengagemanget genom att använda sin mobilapp. Men när nya funktioner läggs till i appen är det viktigt att kunderna uppgraderar till den senaste appversionen. De kan analysera och jämföra alla sina appversioner sida vid sida med [!UICONTROL Custom Dimension] Cohort för att se vilka kunder de ska ha som appversion. Dessutom kan de spåra både lojalitet och bortfall för att se om specifika appversioner gör att kunderna slipper använda appen över tid. Tack vare mobilmeddelanden kan de återengagera dessa användare för att få dem att uppgradera till den senaste versionen och dra nytta av de senaste funktionerna.

## Användningsexempel för kampanjfokus

Ett multinationella medieföretag använder riktade kampanjer för att locka användare till olika plattformar för att öka engagemanget. Annonskostnaderna per plattform bygger på kundengagemang och kundlojalitet. Därför är framgångsrika kampanjer avgörande för att deras verksamhet ska lyckas. De använder vår nya kohortfunktion [!UICONTROL Custom Dimension] i [!UICONTROL Cohort]-tabeller för att jämföra olika kampanjer sida vid sida för att identifiera vilka kampanjer som är mest effektiva när det gäller att värva och behålla användare för att öka engagemanget. De kan sedan identifiera vilka aspekter som gör en kampanj framgångsrik och använda den på andra kampanjer för att öka engagemanget på deras olika plattformar.

## Produktstartexempel

En stor klädhandlare har många specifika kundsegment som genererar stora delar av intäkterna för sin verksamhet. Varje segment har specifika produkter som är utformade och skapade med segmentet i åtanke. När de lanserar en produkt vill de veta hur den nya produkten har ökat försäljningen till olika kohorter med tiden. Med den nya [!UICONTROL Latency Table]-inställningen i [!UICONTROL Cohort Analysis] kan de analysera ett visst kundsegments beteende och intäkter före och efter lanseringen. Med hjälp av den här informationen kan de identifiera vilka produkter som genererar nya intäkter och vilka som inte drar nytta av kundernas intresse.

## Individuell tröghet - De flesta lojala användare använder skiftläge

Ett stort flygbolag får större delen av sin framgång och sina intäkter från återkommande och lojala kunder. I många fall utgör deras lojala resenärer merparten av intäkterna och att behålla dessa kunder är avgörande för deras långsiktiga framgång. Det kan ofta vara svårt att identifiera sina mest lojala och enhetliga kunder. Men med den nya [!UICONTROL Rolling Calculation]-inställningen i [!UICONTROL Cohort Analysis] kunde de analysera lojala kundsegment och ta reda på vilka resenärer som upprepade köpare varje månad. De kunde sedan inrikta sig på resenärerna med belöningar och förmåner för deras lojalitet. Genom att byta från lojalitet till bortfall kunde de också identifiera vilka kunder som inte var återkommande köpare varje månad och inrikta sig på dessa segment med kampanjer för att återengagera dem och säkerställa att de fortsätter att vara lojala kunder i framtiden.
