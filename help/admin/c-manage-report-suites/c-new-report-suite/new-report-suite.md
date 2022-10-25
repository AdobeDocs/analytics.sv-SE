---
description: Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.
title: Ny rapportsvit – inställningar
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 4f51233fa7373481c0e001f86398a09fbbb35fb3
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 2%

---

# Ny rapportsvit – inställningar

Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.

Beskrivningar av de element som används vid [skapa en rapportsvit](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>The [Dokumentation för Virtual Report Suite](/help/components/vrs/c-workflow-vrs/vrs-create.md) visar hur du skapar virtuella rapportsviter.

| Element | Beskrivning |
| --- | --- |
| Rapportsvit-ID | Anger ett unikt ID som bara kan innehålla alfanumeriska tecken. Detta ID kan inte ändras efter att det har skapats. Adobe anger det ID-prefix som krävs och kan inte ändras.  När du skapar flera rapportsviter måste du se till att namnkonventionen du använder garanterar unika ID:n för rapportsviten. |
| Platsrubrik | Identifierar rapportsviten i Admin Tools. Den här titeln används också i listrutan Report Suite i Suite-rubriken. |
| Tidszon | Schemalägger händelser och tidsstämpeldata. |
| Bas-URL | (Valfritt) Definierar basdomänen för rapportsviten. URL-adressen fungerar som ett internt URL-filter om du inte uttryckligen definierar interna URL-filter för rapportsviten. |
| Standardsida | (Valfritt) Tar bort förekomster av standardsidvärdet från URL:er som påträffas. Om rapporten för mest populära sidor innehåller URL-adresser i stället för sidnamn, förhindrar den här inställningen flera URL-adresser för samma webbsida.  URL:erna `https://example.com` och `https://example.com/index.html` är vanligtvis samma sida.<p> Du kan ta bort överflödiga filnamn så att båda dessa URL:er visas som `https://example.com` i era rapporter. Om du inte anger det här värdet tar Analytics automatiskt bort följande filnamn från URL:er: `index.htm`, `index.html`, `index.cgi`, `index.asp`,  `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi`och `home.asp`. Om du vill inaktivera filnamnsborttagning anger du ett standardsidvärde som aldrig förekommer i dina URL-adresser. |
| Go Live Date | Informerar Adobe om vilket datum du förväntar dig att den här rapportsviten ska aktiveras. Om ditt driftsättningsschema ändras kan du göra en uppdaterad trafikberäkning med verktyget för permanent förväntad trafik i Traffic Management. |
| Beräknade sidvisningar per dag | Identifierar det beräknade antalet sidvisningar som du förväntar dig att den här rapportsviten ska ha stöd för en dag. Stora trafikvolymer kräver en längre godkännandeprocess. För att undvika förseningar i bearbetningen bör denna uppskattning göras så korrekt som möjligt. |
| Basvaluta | Anger standardvalutan som används för att lagra alla monetära data. Analysrapporter konverterar transaktioner i andra valutor till basvalutan med hjälp av den aktuella konverteringsgraden vid den tidpunkt då data tas emot. Analysrapporter använder JavaScript-variabeln currencyCode för att identifiera valutan för en viss transaktion. |
| Inaktivera stöd för flerbytetecken | Inaktiverar stöd för flerbytetecken för rapportsviten. Om du inaktiverar stöd för flerbytetecken antas data finnas i `ISO-8859-1` format. Webbsidorna måste ange sin teckenuppsättning i JavaScript-variabeln charSet. <p>Stöd för flerbytetecken lagrar tecken i rapportsviten med UTF-8. Vid mottagande konverterar systemet data från webbsidans teckenuppsättning till teckenuppsättningen UTF-8, så att du kan använda vilket språk som helst i dina marknadsföringsrapporter.  Kontakta din kontoansvarige eller kundtjänst om du vill ändra stödet för flerbytetecken för en befintlig rapportsvit. |

{style=&quot;table-layout:auto&quot;}
