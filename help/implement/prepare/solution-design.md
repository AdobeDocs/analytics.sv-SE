---
title: Skapa ett dokument för lösningsdesign
description: Lär dig vad ett designdokument är och hur du kan använda det i din organisation.
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Skapa ett dokument för lösningsdesign

Ett dokument för lösningsdesign (även kallat ett dokument för lösningsdesignreferens eller affärskrav) är i själva verket planen för er analysimplementering. Det definierar kriterier som identifieras av intressenter i hela organisationen och översätter dem till variabler i Adobe Analytics. Utan en har organisationer svårt att samordna rapporteringsbehoven och tenderar att missa insamlingen av viktiga data.

## Förutsättningar

[Validera er Analytics-implementering och publicera i produktion](../launch/validate-publish-prod.md) - Även om det inte krävs direkt rekommenderar Adobe att ni har en grundläggande implementering så att kritiska data samlas in medan ytterligare affärskrav är fastställda och implementerade.

## Designdokumentets ägarskap och plats

* **Bestäm vem i organisationen som ansvarar för att underhålla konstruktionsdokumentet.** Den här rollen kan antingen vara en individ eller ett team. Säkerställ att lösningsdesignen bibehålls även genom rolländringar eller omstruktureringar av organisationen. Det är ett levande dokument och måste underhållas på rätt sätt.
* **Bestäm var lösningsdokumentet ska placeras.** Det finns inte någon enda bra plats att lagra konstruktionsdokument, men de finns vanligtvis på en lättillgänglig intern plats. Exempel är ett delat kalkylblad eller en samarbetsyta som SharePoint eller en intern wiki. Den behöver inte vara redigerbar för alla, men det är bra för dem som har åtkomst till rapporter att åtminstone kunna visa den.

## Definiera affärskrav

När man avgör vilka data som ska samlas in är det enkelt att säga&quot;allt&quot;, men det kan snabbt bli ohanterligt att hantera och kan till och med ge mindre värde än att samla in mer koncisa mängder data.

1. **Ta reda på vilka nyckeltal du har som prestandaindikatorer.** Vad vill du att besökarna ska göra i slutändan? Svaret på den här frågan varierar beroende på bransch och vertikal, och kan vara flera saker. Exempel är inköp, registreringar och annonsklickningar.
1. **Ta reda på vilka data som är viktigast att samla in.** Ställ affärsfrågor som du vill ha specifika svar på. Svar på dessa frågor ger insikt i hur ni kan förbättra era nyckeltal.
1. **Ta reda på vilka behov ni har av spårning.** Gruppera dem i mått och mätvärden.
   * Dimensioner är variabler som innehåller text. Exempel är ett internt sökord, en produktkategori eller namnet på ett område som besökaren klickade på.
   * Mätvärden är specifika händelser som du vill att en besökare ska göra - när de utför en åtgärd som du vill ska numret vara ett. Exempel är att skicka en beställning, prenumerera på ett nyhetsbrev eller skicka ett enkätsvar.
1. **Mappa mått och mätvärden till en sida eller ett kalkylblad.** Den här sidan eller tabellen blir i slutändan ditt designdokument för lösningen. Några praktiska spalter eller punkter att ta med:
   * Implementeringsstatus: Planerade, aktiva, inaktiva, problem osv. Detta informerar läsarna om dokumentet om variabelns status, om den har implementerats, eller om det finns problem med datainsamlingen.
   * Variabelnamn: Exempel: &quot;Interna söktermer&quot;. Detta värde är vad analytikerna ser när de arbetar i Analytics.
   * Analysvariabeln mappas till: Vilken standardvariabel eller anpassad analysvariabel du väljer att tilldela värden till. Dimensioner faller vanligtvis under eVars medan mätvärden faller under händelser.
   * Logic: En beskrivning av hur variabeln ställs in och vad som avgör dess värde. Exempel:&quot;Endast angivet på interna söksidor. Tar värdet på frågesträngsparametern q.&quot;
   * Andra anteckningar som du vill ta med som hör till variabeln

## Ytterligare resurser

Att definiera ett designdokument är ett ganska komplext projekt, särskilt för organisationer som inte har skapat ett tidigare. Om man behöver ytterligare hjälp kan Adobe erbjuda specialkonsulter för att hjälpa er organisation att komma igång med Adobe Analytics. Kontakta din kontoansvarige om du vill registrera dig för Adobes professionella tjänster. Ett [tekniskt förimplementeringsfrågeformulär](assets/technical-pre-implementation-questionnaire.pdf) kan fyllas i så att Adobe vet exakt hur man kan hjälpa till baserat på organisationens behov.

Det finns också ett flertal Adobe-partners som är specialiserade på att hjälpa till att skapa ett designdokument för lösningar, samt implementera Adobe Analytics på er webbplats.

## Nästa steg

Implementera variablerna i lösningsdesigndokumentet.

[Skapa ett datalager](data-layer.md): Översätt variabler i ditt designdokument till JavaScript-variabler på din webbplats.
