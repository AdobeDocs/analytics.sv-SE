---
title: Datalagringspolicy
description: En datalagringspolicy avgör hur länge Adobe lagrar dina data.
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 0%

---


# Datalagringspolicy

Data som samlas in av Adobe Analytics sparas under en viss tidsperiod. Den tid som Adobe lagrar dessa data varierar från kontrakt till kontrakt och beskrivs i en organisations policy för datalagring. Den här principen gäller själva data, vilket innebär att den påverkar alla analysrapporteringsfunktioner (Analysis Workspace, API för rapportering m.m.).

**Standardprincipen för datalagring för Adobe Analytics är 25 månader.** Din organisations lagringspolicy kan vara annorlunda, beroende på avtal.

Data som lagras baseras på aktuellt datum och datum/tid för historiska data. Datumet/tiden som spelades in i träffar kan vara ett annat datum/tid än det datum/den tidpunkt då träffarna togs emot av Adobe.

## Justera standardperioden för datalagring

Om du vill minska eller förlänga standardperioden för datalagring kontaktar du din organisations kontoansvarige.

* Det kostar inget att minska standardperioden för datalagring.
* Om man vill utöka datalagringen till mer än 25 månader efter standardperioden för lagring av uppgifter måste man köpa utökningar, som kan fås i steg om ett år. Upp till åtta förlängningar kan köpas, under totalt 10 år i månaden (två år i månaden för fallissemang plus åtta år).

## Datalagring och dataintegritet

Adobe måste i sin roll som personuppgiftsbiträde vidta lämpliga åtgärder för att hjälpa sina kunder med att uppfylla kraven på åtkomst, borttagning och andra förfrågningar från enskilda personer. Att tillämpa lämpliga, säkra och vältajmade principer för borttagning är en viktig del av att uppfylla denna skyldighet. GDPR gäller alla kunder som marknadsför eller bearbetar information till EU-medborgare. CCPA gäller alla kunder som marknadsför eller bearbetar information om Kalifornien-medborgare. Därför är dataintegritet en förändring i den globala lagstiftningen.

## Radering av data

När data överskrider din datalagringspolicy behåller Adobe rätten att ta bort dem utan alternativ för återställning. Ni måste se till att alla data som ni vill behålla ligger inom er organisations datalagringspolicy.

## Frågor och svar

**Hur bestämmer jag mig för min organisations period för datalagring?**

Ert företag, som personuppgiftsansvariga, kan identifiera intressenter (som ert marknadsförings-, analys- och sekretessteam) i er organisation som ansvarar för att fatta beslut om datalagring. Er organisation är bäst på att veta hur länge Adobe Analytics lagrar data.

**Hur beräknar jag datalagringsfönstret?**

Datalagringspolicyn definierar ett rullande datalagringsfönster där fullständiga data kan visas och rapporteras. Startdatumet för datalagring bestäms av det aktuella datumet minus den period då data finns kvar. Slutdatumet för datalagring bestäms av det aktuella datumet. Data inkluderas i datalagringsfönstret om tidsstämpeln för data är mellan startdatumet och slutdatumet.

**Kan jag begära en kopia av mina data innan de tas bort?**

Ja. Adobe kan tillhandahålla en historisk datapassage av råa data på träffnivå. Mer information finns i [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md) i användarhandboken för Export. Om du har dataexportkrav som inte omfattas av användargränssnittet kontaktar du din organisations kontoansvarige. Särskilda inkvarteringar kan göras. kostnaderna kan variera.

**När tar Adobe bort data?**

Kontakta er organisations kontoansvarige för den specifika tid då era data ska tas bort. Data tas vanligtvis bort rullande månadsvis.
