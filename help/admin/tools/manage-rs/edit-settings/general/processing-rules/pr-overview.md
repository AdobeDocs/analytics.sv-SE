---
description: Bearbetningsregler förenklar datainsamling och hantering av innehåll när det skickas till rapportering.
subtopic: Processing rules
title: Översikt över bearbetningsregler
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# Översikt över bearbetningsregler

Med bearbetningsregler kan du ändra hur data samlas in innan de skrivs till en rapportserie.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]**

>[!WARNING]
>
>Bearbetning av regler påverkar direkt datainsamlingen och kan orsaka dataförlust om de används felaktigt. Testa alltid bearbetningsregler i en utvecklingsrapportsserie innan du aktiverar dem i en produktionsrapportsserie för att minska problem med datakvaliteten.

De två viktigaste användningsområdena för bearbetningsregler är:

* **Använd arbetsflödet för implementering av kontextdatavariabler**: I stället för att ange variabler direkt i implementeringen kan du använda [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) för att ange nyckel-/värdepar. I stället för inställningen:

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  Du kan i stället ange:

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  Du kan sedan mappa kontextdatavariablerna till önskade mått och mätvärden i analysgränssnittet.

  När du kommunicerar med utvecklare i organisationen för att implementera Analytics för en egenskap, förenklas kommunikationsprocessen genom att använda kontextdatavariabler. Utvecklare kan helt enkelt implementera varje nyckel/värde-par en gång, och sedan kan ni som Analytics-administratör se till att data når rätt implementeringsvariabel.

* **Ändra data när de samlas in**: Det här användningsexemplet har ett stort antal program, till exempel tillfälliga korrigeringar av datakvalitet eller för att fylla i implementeringsluckor. Mer information och specifika exempel finns i [Användningsexempel för bearbetningsregler](pr-use-cases.md).

## Behörigheter

Produktadministratörer har som standard tillgång till bearbetningsregler. Du kan ge icke-administratörer åtkomst till bearbetningsregler genom att inkludera dem i en produktprofil som innehåller behörighetsobjektet **[!UICONTROL Processing rules]**. Mer information finns i [Behörigheter för produktprofiler för verktygen i Report Suite](/help/admin/admin-console/permissions/report-suite-tools.md).

## Att tänka på när du skapar eller redigerar bearbetningsregler

När du skapar eller redigerar bearbetningsregler ska du tänka på följande:

* **Möjliga tomma värden**: När du skapar en regel bör du ta hänsyn till fall när det tomma värdet för överskrivning är tomt. Om du till exempel har en regel som skriver över eVar1 med eVar2 och eVar2 är tom, tas båda variablerna bort. Adobe rekommenderar att du lägger till ett villkor som söker efter ett variabelvärde innan du använder det för att skriva över ett annat värde.
* **Använd omedelbart när du sparar**: Bearbetningsreglerna tillämpas på insamlade data så fort du sparar dem. De gäller inte retroaktivt för data som redan samlats in.
* **Bearbetningsordning i regler**: Om du har flera bearbetningsregler gäller ordningen som de körs i. Om du använder en viss variabel i flera regler måste du se till att de körs i rätt ordning. Om du skriver över eVar3 i regel 1 är det ursprungliga eVar3-värdet inte tillgängligt i efterföljande regler.
* **Bearbetningsordning i datainsamlingsflödet**: Se [Bearbetningsordning för data i Adobe Analytics](/help/technotes/processing-order.md) om du vill veta var bearbetningsreglerna gäller i den övergripande datainsamlingsflödet.
* **Kodning**: Använd UTF-8-kodning i nästan alla fall.
* **Skiftlägeskänslighet**: Strängjämförelser i bearbetningsregler är inte skiftlägeskänsliga. De strängvärden som du använder för att skriva över värden använder samma regler som för att fylla i variabeln direkt.
* **En rapportserie**: När du redigerar bearbetningsregler gäller de bara för en rapportserie. Om du väljer flera rapportsviter i Report Suite-hanteraren måste du välja en enda rapportserie. När du har skapat eller redigerat de önskade bearbetningsreglerna kan du [kopiera dessa regler till andra rapportsviter](pr-copy.md).
* **Inget dataundantag**: Att exkludera data är inte en avsedd funktion i bearbetningsregler. Överväg att använda [`abort`](/help/implement/vars/config-vars/abort.md) på datainsamlingsnivå eller använd [VISTA-regler](/help/technotes/vista.md) efter att data har samlats in.
* **Tillgängliga variabler**: Alla dimensioner och mått är inte tillgängliga i bearbetningsregler. Se [Dimensioner och mätvärden som är tillgängliga för bearbetningsregler](pr-variables.md) för en fullständig lista över vad som stöds.
* **Antal regler som tillåts**: Varje rapportserie kan innehålla upp till 150 regler. Varje regel kan innehålla upp till 30 villkor.

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mappa kontextdatavariabler till utkast och eVars med bearbetningsregler](https://experienceleague.adobe.com/sv/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
