---
title: Skapa ett dokument för lösningsdesign
description: Lär dig vad ett designdokument är och hur du kan använda det i din organisation.
feature: Implementation Basics
exl-id: 0b5c5ddd-5f53-4790-a649-1381135dacda
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 0%

---

# Skapa ett dokument för lösningsdesign

Ett dokument för lösningsdesign (även kallat ett dokument för lösningsdesignreferens eller affärskrav) är i själva verket planen för er analysimplementering. Det definierar kriterier som identifieras av intressenter i hela organisationen och översätter dem till variabler inom Adobe Analytics. Utan en har organisationer svårt att samordna rapporteringsbehoven och tenderar att missa insamlingen av viktiga data.

## Förutsättningar

[Validera er Analytics-implementering och publicera till produktion](../launch/validate-publish-prod.md) - Även om det inte krävs direkt rekommenderar Adobe att man har en grundläggande implementering så att viktiga data samlas in samtidigt som ytterligare affärskrav fastställs och implementeras.

## Designdokumentets ägarskap och plats

* **Bestäm vem i organisationen som ansvarar för att underhålla konstruktionsdokumentet.** Den här rollen kan antingen vara en individ eller ett team. Säkerställ att lösningsdesignen bibehålls även genom rolländringar eller omstruktureringar av organisationen. Det är ett levande dokument och måste underhållas på rätt sätt.
* **Bestäm var lösningsdokumentet ska placeras.** Det finns inte någon enda bra plats att lagra konstruktionsdokument, men de finns vanligtvis på en lättillgänglig intern plats. Exempel är ett delat kalkylblad eller en samarbetsyta som SharePoint eller en intern wiki. Den behöver inte vara redigerbar för alla, men det är bra för dem som har åtkomst till rapporter att åtminstone kunna visa den.

## Definiera affärskrav

När man avgör vilka data som ska samlas in är det enkelt att säga&quot;allt&quot;, men det kan snabbt bli ohanterligt att hantera och kan till och med ge mindre värde än att samla in mer koncisa mängder data.

1. **Ta reda på vilka nyckeltal du har som prestandaindikatorer.** Vad vill du att besökarna ska göra i slutändan? Svaret på den här frågan varierar beroende på bransch och vertikal, och kan vara flera saker. Exempel är inköp, registreringar och annonsklickningar.
1. **Ta reda på vilka data som är viktigast att samla in.** Ställ affärsfrågor som du vill ha specifika svar på. Svar på dessa frågor ger insikt i hur ni kan förbättra era nyckeltal.
1. **Ta reda på vilka behov ni har av spårning.** Gruppera dem i mått och mätvärden.
   * Dimensioner är variabler som innehåller text. Exempel är ett internt sökord, en produktkategori eller namnet på ett område som besökaren klickade på.
   * Mätvärden är specifika händelser som du vill att en besökare ska göra - när de utför en åtgärd som du vill ska siffran ökas med ett. Exempel är att skicka en beställning, prenumerera på ett nyhetsbrev eller skicka ett enkätsvar.
1. **Mappa mått och mätvärden till en sida eller ett kalkylblad.** Den här sidan eller tabellen blir i slutändan ditt designdokument för lösningen. Några praktiska spalter eller punkter att ta med:
   * Implementeringsstatus: Planerad, aktiv, inaktiv, problem osv. Detta informerar läsarna om dokumentet om variabelns status, om den har implementerats, eller om det finns problem med datainsamlingen.
   * Variabelnamn: Till exempel&quot;Intern sökning&quot;. Detta värde är vad analytikerna ser när de arbetar i Analytics.
   * Analysvariabeln mappas till: Vilken standardvariabel eller anpassad analysvariabel du väljer att tilldela värden till. Dimensioner faller vanligtvis under eVars, medan mätvärden faller under händelser.
   * Logic: En beskrivning av hur variabeln ställs in och vad som avgör dess värde. Exempel:&quot;Endast angivet på interna söksidor. Tar värdet på frågesträngsparametern q.&quot;
   * Andra anteckningar som du vill ta med gäller variabeln

## Ytterligare resurser

Att definiera ett designdokument är ett ganska komplext projekt, särskilt för organisationer som inte har skapat ett tidigare. Om du behöver ytterligare hjälp kan Adobe ge dig specialkonsultationer som hjälper dig att komma igång med Adobe Analytics. Kontakta Adobe Account Team om du vill anmäla dig till Adobe professionella tjänster. A [Teknisk förimplementeringsenkät](assets/technical-pre-implementation-questionnaire.pdf) kan fyllas i så att Adobe vet exakt hur man kan hjälpa efter organisationens behov.

Det finns också flera partners på Adobe som specialiserar sig på att skapa ett dokument för lösningsdesign samt implementera Adobe Analytics på er webbplats.

## Nästa steg

Implementera variablerna i lösningsdesigndokumentet.

[Skapa ett datalager](data-layer.md): Översätt variabler i ditt designdokument till JavaScript-variabler på din webbplats.
