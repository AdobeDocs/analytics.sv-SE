---
description: Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.
title: Ny rapportsvit - inställningar
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 8c0e88a22928d79599ab0a0ad3efc8159712d739
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 0%

---

# Ny rapportsvit - inställningar

Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.

Beskrivningar av elementen som används när [en rapportserie skapas](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>[Dokumentationen för den virtuella rapportsviten](/help/components/vrs/c-workflow-vrs/vrs-create.md) visar hur du skapar virtuella rapportsviter.

| Element | Beskrivning |
| --- | --- |
| Rapportsvit-ID | Anger ett unikt ID som bara kan innehålla alfanumeriska tecken. Detta ID kan inte ändras efter att det har skapats. Adobe anger det ID-prefix som krävs och kan inte heller ändras.  När du skapar flera rapportsviter måste du se till att namnkonventionen du använder garanterar unika ID:n för rapportsviten. |
| Platsrubrik | Identifierar rapportsviten i Admin Tools. Den här titeln används också i listrutan Report Suite i Suite-rubriken. |
| Tidszon | Schemalägger händelser och tidsstämpeldata. |
| Bas-URL | (Valfritt) Definierar basdomänen för rapportsviten. URL-adressen fungerar som ett internt URL-filter om du inte uttryckligen definierar interna URL-filter för rapportsviten. |
| Standardsida | (Valfritt) Tar bort förekomster av standardsidvärdet från URL:er som påträffas. Om rapporten för mest populära sidor innehåller URL-adresser i stället för sidnamn, förhindrar den här inställningen flera URL-adresser för samma webbsida.  URL:erna `https://example.com` och `https://example.com/index.html` är till exempel vanligtvis samma sida.<p> Du kan ta bort överflödiga filnamn så att båda dessa URL:er visas som `https://example.com` i dina rapporter. Om du inte anger det här värdet tar Analytics automatiskt bort följande filnamn från URL:er: `index.htm`, `index.html`, `index.cgi`, `index.asp`, `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi` och `home.asp`. Om du vill inaktivera filnamnsborttagning anger du ett standardsidvärde som aldrig förekommer i dina URL-adresser. |
| Go Live Date | Informerar Adobe om det datum då du förväntar dig att den här rapportsviten ska aktiveras. Om ditt driftsättningsschema ändras kan du göra en uppdaterad trafikberäkning med verktyget för permanent förväntad trafik i Traffic Management. |
| Beräknade sidvisningar per dag | Identifierar det beräknade antalet sidvisningar som du förväntar dig att den här rapportsviten ska ha stöd för under en dag. Stora trafikvolymer kräver en längre godkännandeprocess. För att undvika förseningar i bearbetningen bör denna uppskattning göras så korrekt som möjligt. |
| Basvaluta | Anger standardvalutan som används för att lagra alla monetära data. Analysrapporter konverterar transaktioner i andra valutor till basvalutan med hjälp av den aktuella konverteringsgraden vid den tidpunkt då data tas emot. Analysrapportering använder JavaScript-variabeln currencyCode för att identifiera valutan för en viss transaktion. |
| Aktivera bearbetning av japanska nyckelord | Aktiverar stöd för flerbytetecken för rapportsviten. Om du inaktiverar stöd för flerbytetecken antas data ha formatet `ISO-8859-1`. På webbsidor måste teckenuppsättningen anges i variabeln charSet JavaScript. <p>Stöd för flerbytetecken lagrar tecken i rapportsviten med UTF-8. Vid mottagande konverterar systemet data från webbsidans teckenuppsättning till teckenuppsättningen UTF-8, så att du kan använda vilket språk som helst i dina marknadsföringsrapporter.  Kontakta Adobe Account Team eller Customer Care om du vill ändra stödet för flerbytetecken för en befintlig rapportsvit. |
| Använd förenklad navigeringsmeny | Den här funktionen ingick i [Rapporter och analyser](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?), som inte längre stöds. |

{style="table-layout:auto"}
