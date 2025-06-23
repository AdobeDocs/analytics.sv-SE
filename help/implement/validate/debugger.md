---
title: Äldre Adobe Experience Cloud Debugger
description: Installera den gamla Adobe Experience Cloud Debugger. Den här felsökaren undersöker taggar för taggarna Analytics, Target, Advertising Cloud, Identity Service och Data Collection.
feature: Implementation Basics
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Äldre Adobe Experience Cloud Debugger

>[!IMPORTANT]
>
>Det här felsökningsverktyget finns inte längre kvar. Adobe rekommenderar i stället att du använder [Adobe Experience Cloud Debugger Chrome Extension](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).

[!UICONTROL Legacy Debugger] undersöker taggar för de flesta Adobe Experience Cloud-tjänster. Med hjälp av felsökaren kan du se vilka data som skickas till Adobe på en viss sida på webbplatsen. Du kan använda den här informationen för att felsöka eller validera implementeringen av din organisation.

## Installera den gamla felsökaren

Skapa ett JavaScript-bokmärke för att installera felsökningsprogrammet.

### Steg 1: Kopiera kod för bokmärke

Kopiera följande kod till Urklipp:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Steg 2: Klistra in kod för bokmärke i ett bokmärke

Varje webbläsare har olika sätt att hantera bokmärken, men konceptet är detsamma. Ett bokmärke skapas med det önskade namnet och bokmärkeskoden som URL.

#### Chrome

Om du insisterar på att inte använda tillägget [Chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) kan du använda det gamla felsökningsbokmärket i stället.

1. Klicka på de tre punkterna i det övre högra hörnet och gå sedan till Bokmärken > Bokmärkeshanteraren. Du kan också trycka på `Ctrl` + `Shift` + `O` (Windows) eller `Cmd` + `Shift` + `O` (Mac).
2. Klicka på de tre punkterna i det övre högra hörnet av bokmärkeshanteraren och klicka sedan på Lägg till nytt bokmärke.
3. I fältet Namn ger du det etiketten&quot;Adobe Experience Cloud Debugger&quot; och klistrar in kodfragmentet i URL-fältet.
4. Använd bokmärkeshanteraren för att placera det nya bokmärket på önskad plats.

#### Firefox

1. Klicka på de tre raderna i det övre högra hörnet och gå sedan till Bibliotek > Bokmärken > Visa alla bokmärken. Du kan också trycka på `Ctrl` + `Shift` + `B` (Windows) eller `Cmd` + `Shift` + `B` (Mac).
2. Klicka på Ordna > Nytt bokmärke.
3. I fältet Namn ger du det etiketten&quot;Adobe Experience Cloud Debugger&quot; och klistrar in kodfragmentet i fältet Location. Fälten Taggar och Nyckelord är inte obligatoriska.
4. Använd biblioteksfönstret för att placera det nya bokmärket på önskad plats.

#### Edge

Edge kan inte skapa ett bokmärke manuellt, men en bokmärkes-URL kan redigeras i ett bokmärkesdiagram.

1. Klicka på stjärnikonen till höger om URL-fältet för att bokmärka den aktuella sidan.
2. Ge bokmärket&quot;Adobe Experience Cloud Debugger&quot; ett namn och spara det där du vill.
3. Klicka på stjärnikonen med linjer för att öppna fältet Favoriter.
4. Högerklicka på det nya bokmärket och välj Redigera URL.
5. Klistra in kodfragmentet i textfältet och tryck sedan på Retur.

#### Safari

Safari kan inte skapa ett bokmärke manuellt, men en bokmärkes-URL kan redigeras i ett bokmärkesdiagram.

1. Klicka på delningsikonen i det övre högra hörnet, som öppnar ett modalt bokmärkesfönster.
2. Ge bokmärket&quot;Adobe Experience Cloud Debugger&quot; ett namn och spara det där du vill.
3. Klicka på Bokmärken > Redigera bokmärken och leta reda på det nya bokmärket.
4. Högerklicka > Redigera adress och klistra sedan in kodfragmentet i textfältet.

## Använda den gamla felsökningsfunktionen

Navigera till önskad sida på webbplatsen och klicka sedan på bokmärket. Ett popup-fönster visas med data som skickats till Adobe.

>[!NOTE]
>
>Vissa reklamblockerande plugin-program och popup-blockerare kan störa inläsningen av felsökningsfönstret. Kontrollera om det finns blockerade popup-fönster i webbläsaren och tillåt dem så att felsökaren kan fungera korrekt.

Felsökaren har flera tillgängliga alternativ, som alla anpassar hur data visas. Inget av dessa alternativ påverkar datainsamlingen.

* **Visade Experience Cloud-produkter:** Visar eller döljer bildbegäranden för respektive Experience Cloud-produkt.
* **URL-avkodning:** URL avkodar bildbegäran så att den matchar vad som visas i rapporten. Adobe rekommenderar att du låter den här rutan vara markerad.
* **Automatisk uppdatering:** Uppdaterar automatiskt popup-fönstret med några sekunder för att kontrollera om det finns fler bildbegäranden på sidan. Om du behöver kopiera/klistra in innehåll i felsökaren inaktiverar du automatisk uppdatering så att markeringen inte ändras.
* **Eget format:** Växlar visningsformatet mellan användbara etiketter och råfrågesträngar i en bildbegäran. Mer information finns i [Frågeparametrar för datainsamling](query-parameters.md).

Om du vill spara standardvisningsalternativen för felsökaren högerklickar du på länken Adobe Debugger i det övre högra hörnet och kopierar sedan länkadressen. Redigera ditt aktuella felsökningsbokmärke och klistra in det uppdaterade kodfragmentet i URL-fältet.
