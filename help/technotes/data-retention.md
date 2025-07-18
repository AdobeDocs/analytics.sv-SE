---
title: Datalagringspolicy
description: En datalagringspolicy avgör hur länge Adobe lagrar dina data.
exl-id: f3bb02d2-380d-4eb7-8449-e0318fc8c0a6
feature: Data Governance
source-git-commit: e937b63c9409d75875e3d0c8b46a89024c093ebe
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---

# Datalagringspolicy

Data som samlas in av Adobe Analytics sparas under en viss tidsperiod. Den tid som Adobe sparar dessa data varierar från kontrakt till kontrakt och beskrivs i en organisations datalagringspolicy. Denna policy gäller för själva data, vilket innebär att den påverkar alla analysrapporteringsfunktioner (Analysis Workspace, API för rapportering etc.).

**Standarddatalagringsprincipen för Adobe Analytics är 25 månader.** Din organisations lagringspolicy kan vara annorlunda, beroende på kontrakt.

Data som lagras baseras på aktuellt datum och datum/tid för historiska data. Datumet/tiden som spelades in i träffar kan vara ett annat datum/tid än det datum/den tidpunkt då träffarna togs emot av Adobe.

## Justera standardperioden för datalagring

Om du vill minska eller förlänga den standardinställda datalagringsperioden kontaktar du Adobe Account Team.

* Det kostar inget att minska standardperioden för datalagring.
* Om man vill utöka datalagringen till mer än 25 månader efter standardperioden för lagring av uppgifter måste man köpa utökningar, som kan fås i steg om ett år. Upp till åtta förlängningar kan köpas, under totalt 10 år i månaden (två år i månaden för fallissemang plus åtta år).

## Datalagring och dataintegritet

Adobe måste i sin roll som personuppgiftsbiträde vidta lämpliga åtgärder för att hjälpa sina kunder med att uppfylla åtkomst, borttagning och andra förfrågningar från enskilda personer. Att tillämpa lämpliga, säkra och vältajmade principer för borttagning är en viktig del av att uppfylla denna skyldighet. GDPR gäller alla kunder som marknadsför eller bearbetar information till EU-medborgare. CCPA gäller alla kunder som marknadsför eller bearbetar information om Kalifornien-medborgare. Därför är dataintegritet en förändring i den globala lagstiftningen.

## Borttagning av data

När data överskrider din datalagringspolicy behåller Adobe rätten att ta bort dem utan alternativ för återställning. Ni måste se till att alla data som ni vill behålla ligger inom er organisations datalagringspolicy.

## Visa/hantera aktuell datalagringspolicy

Dialogrutan Datastyrning i [!UICONTROL Admin]-verktygen ger en översikt över vilka rapportsviter som har konfigurerats för datastyrning. Här anges också om de har mappats till en Experience Cloud-organisation och om det finns en datalagringspolicy för den här rapportsviten. [Mer information](/help/admin/admin/c-data-governance/an-gdpr-workflow.md)

## Frågor och svar

+++ Hur bestämmer jag mig för min organisations period för datalagring?

Ert företag, som personuppgiftsansvariga, kan identifiera intressenter (som ert marknadsförings-, analys- och sekretessteam) i er organisation som ansvarar för att fatta beslut om datalagring. Er organisation är bäst på att veta hur länge Adobe Analytics lagrar data.

+++

+++ Hur beräknar jag datalagringsfönstret?

Datalagringspolicyn definierar ett rullande datalagringsfönster där fullständiga data kan visas och rapporteras. Startdatumet för datalagring bestäms av det aktuella datumet minus den period då data finns kvar. Slutdatumet för datalagring bestäms av det aktuella datumet. Data inkluderas i datalagringsfönstret om tidsstämpeln för data är mellan startdatumet och slutdatumet.

+++

+++ Kan jag begära en kopia av mina data innan de tas bort?

Ja. Adobe kan tillhandahålla en historik över råa data på träffnivå. Mer information finns i [Datafeeds](/help/export/analytics-data-feed/data-feed-overview.md) i användarhandboken för Exportera. Om du har dataexportkrav som inte omfattas av användargränssnittet kontaktar du Adobe Account Team. Man kan göra speciella anpassningar; kostnaderna kan variera.

+++

+++ När raderar Adobe data?

Kontakta Adobe Account Team för att få veta när dina data ska tas bort. Data tas vanligtvis bort rullande månadsvis.

+++

