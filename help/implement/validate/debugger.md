---
title: Äldre Adobe Experience Cloud Debugger
description: Installera den gamla felsökningsfunktionen för Adobe Experience Cloud. Den här felsökaren undersöker taggarna för Analytics, Target, Advertising Cloud, Identity Service, DTM och Launch.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Äldre Adobe Experience Cloud Debugger

>[!IMPORTANT] Det här felsökningsverktyget finns inte längre kvar. Adobe rekommenderar i stället att du använder [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html).

Taggarna [!UICONTROL Legacy Debugger] kontrolleras för de flesta Adobe Experience Cloud-tjänster. Med hjälp av felsökaren kan du se vilka data som skickas till Adobe på en viss sida på din webbplats. Du kan använda den här informationen för att felsöka eller validera implementeringen av din organisation.

## Installera den gamla felsökaren

Skapa ett JavaScript-bokmärke för att installera felsökningsprogrammet.

### Steg 1: Kopiera bokmärkeskod

Kopiera följande kod till Urklipp:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Steg 2: Klistra in kod för bokmärke i ett bokmärke

Varje webbläsare har olika sätt att hantera bokmärken, men konceptet är detsamma. Ett bokmärke skapas med det önskade namnet och bokmärkeskoden som URL.

#### Krom

Om du insisterar på att inte använda [färgtillägget](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)kan det gamla felsökningsbokmärket användas i stället.

1. Klicka på de tre punkterna i det övre högra hörnet och gå sedan till Bokmärken > Bokmärkeshanteraren. Du kan också trycka på `Ctrl` + `Shift` + `O` (Windows) respektive `Cmd` + `Shift` + `O` (Mac).
2. Klicka på de tre punkterna i det övre högra hörnet av bokmärkeshanteraren och klicka sedan på Lägg till nytt bokmärke.
3. I fältet Namn anger du det som&quot;Adobe Experience Cloud Debugger&quot; och klistrar in kodfragmentet i URL-fältet.
4. Använd bokmärkeshanteraren för att placera det nya bokmärket på önskad plats.

#### Firefox

1. Klicka på de tre raderna i det övre högra hörnet och gå sedan till Bibliotek > Bokmärken > Visa alla bokmärken. Du kan också trycka på `Ctrl` + `Shift` + `B` (Windows) respektive `Cmd` + `Shift` + `B` (Mac).
2. Klicka på Ordna > Nytt bokmärke.
3. I fältet Namn anger du det som&quot;Adobe Experience Cloud Debugger&quot; och klistrar in kodfragmentet i fältet Plats. Fälten Taggar och Nyckelord är inte obligatoriska.
4. Använd biblioteksfönstret för att placera det nya bokmärket på önskad plats.

#### Edge

Edge kan inte skapa ett bokmärkesdiagram manuellt, men en bokmärkes-URL kan redigeras i ett bokmärkesdiagram.

1. Klicka på stjärnikonen till höger om URL-fältet för att bokmärka den aktuella sidan.
2. Ge bokmärket&quot;Adobe Experience Cloud Debugger&quot; och spara det där du vill.
3. Klicka på stjärnikonen med linjer för att öppna fältet Favoriter.
4. Högerklicka på det nya bokmärket och välj Redigera URL.
5. Klistra in kodfragmentet i textfältet och tryck sedan på Retur.

#### Safari

Safari kan inte skapa ett bokmärke manuellt, men en bokmärkes-URL kan redigeras i ett bokmärkesdiagram.

1. Klicka på delningsikonen i det övre högra hörnet, som öppnar ett modalt bokmärkesfönster.
2. Ge bokmärket&quot;Adobe Experience Cloud Debugger&quot; och spara det där du vill.
3. Klicka på Bokmärken > Redigera bokmärken och leta reda på det nya bokmärket.
4. Högerklicka > Redigera adress och klistra sedan in kodfragmentet i textfältet.

## Använda den gamla felsökningsfunktionen

Navigera till önskad sida på webbplatsen och klicka sedan på bokmärket. Ett popup-fönster visas med data som skickats till Adobe.

>[!NOTE] Vissa reklamblockerande plugin-program och popup-blockerare kan störa inläsningen av felsökningsfönstret. Kontrollera om det finns blockerade popup-fönster i webbläsaren och tillåt dem så att felsökaren kan fungera korrekt.

Felsökaren har flera tillgängliga alternativ, som alla anpassar hur data visas. Inget av dessa alternativ påverkar datainsamlingen.

* **Visade Experience Cloud-produkter:** Visar eller döljer bildbegäranden för varje Experience Cloud-produkt.
* **URL-avkodning:** URL avkodar bildbegäran så att den matchar det som visas i rapporten. Adobe rekommenderar att du låter rutan vara markerad.
* **Uppdatera automatiskt:** Uppdaterar automatiskt popup-fönstret med några sekunders mellanrum för att kontrollera om det finns fler bildbegäranden på sidan. Om du behöver kopiera/klistra in innehåll i felsökaren inaktiverar du automatisk uppdatering så att markeringen inte ändras.
* **Eget format:** Växlar visningsformatet mellan användbara etiketter och råfrågesträngar i en bildbegäran. Mer information finns i [Frågeparametrar](query-parameters.md) för datainsamling.

Om du vill spara standardvisningsalternativen för felsökaren högerklickar du på länken Adobe Debugger i det övre högra hörnet och kopierar sedan länkadressen. Redigera ditt aktuella felsökningsbokmärke och klistra in det uppdaterade kodfragmentet i URL-fältet.
