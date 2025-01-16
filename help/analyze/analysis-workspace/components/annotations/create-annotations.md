---
title: Skapa anteckningar
description: Så här skapar du anteckningar i Workspace.
role: Admin
feature: Annotations
exl-id: 3cf9a0fd-11c9-4375-8bbe-9551ba86f86d
source-git-commit: 75d8705170169a0ef9f1ee59b12e4bb2c3afac7a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Skapa anteckningar {#create-annotations}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_details"
>title="Anteckningsinformation"
>abstract="Anteckningar gör att ni effektivt kan kommunicera kontextuella datanunkter och insikter till organisationen. De gör att du kan koppla kalenderhändelser till specifika mått/mätvärden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_scope"
>title="Omfång"
>abstract="Med omfång kan du anpassa vilka data som ska kommenteras. Beräknade mått och segment ärver inte automatiskt anteckningar som tillämpas på komponenter som används i deras definitioner. Du kan lägga till nya beräknade värden i omfångsavsnittet i en befintlig anteckning. Nya segment kräver en ny anteckning."

<!-- markdownlint-enable MD034 -->

Som standard kan bara administratörer skapa anteckningar. Användare har rätt att visa anteckningar på samma sätt som andra Analytics-komponenter (som segment, beräknade värden osv.).

Administratörer kan dock ge användare behörigheten [!UICONTROL Annotation Creation] (analysverktyg) via [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html).

1. Du kan komma igång på flera olika sätt om du vill skapa anteckningar:

| Skapandemetod | Information |
| --- | --- |
| **Gå till [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Annotation].** | Sidan Annotations Manager öppnas. Klicka på [!UICONTROL Create New Annotation] så öppnas [!UICONTROL Annotation builder]. |
| **Högerklicka på en punkt i en tabell.** | [!UICONTROL The Annotation builder] öppnas. Observera att som standard visas anteckningar som skapats på det här sättet bara i det projekt där de skapades. Men du kan göra dem tillgängliga för alla projekt. Lägg även märke till att datum och mätvärden redan har fyllts i.<p>![](assets/annotate-table.png) |
| **Högerklicka på en punkt i ett [!UICONTROL Line] diagram.** | [!UICONTROL Annotation builder] öppnas. Observera att som standard visas anteckningar som skapats på det här sättet bara i det projekt där de skapades. Men du kan göra dem tillgängliga för alla projekt. Lägg även märke till att datum och mätvärden redan har fyllts i.<p>![](assets/annotate-line.png) |
| **Gå till [!UICONTROL Components] > [!UICONTROL Create annotation] i Workspace.** | [!UICONTROL Annotation builder] öppnas. |
| **Använd den här snabbtangenten** för att öppna Anteckningsverktyget: (PC) `ctrl` `shift` + o, (Mac) `shift` + `command` + o | Observera, att när du använder snabbtangenten för att skapa en anteckning, skapar du en endagarsanteckning för det aktuella datumet, utan något förvalt omfång (mått eller mått). |

{style="table-layout:auto"}

1. Fyll i elementen [!UICONTROL Annotation builder].

   ![](assets/ann-builder.png)

   | Element | Beskrivning |
   | --- | --- |
   | [!UICONTROL Project-only Annotation] | Som standard gäller anteckningen det aktuella projektet. Genom att markera den här rutan kan du göra anteckningen tillgänglig för alla projekt som du äger.<p> ![](assets/project-only.png) |
   | [!UICONTROL Title] | Namnge anteckningen, t.ex.&quot;Memorial Day&quot; |
   | [!UICONTROL Description] | (Valfritt) Ange en beskrivning av anteckningen, t.ex.&quot;Offentlig semester observerad i USA&quot;. |
   | [!UICONTROL Tags] | (Valfritt) Ordna anteckningar genom att skapa eller använda en tagg. |
   | [!UICONTROL Applied date] | Välj det datum eller datumintervall som måste finnas för att anteckningen ska kunna visas. |
   | [!UICONTROL Color] | Använd en färg på anteckningen. Anteckningen visas i projektet med den valda färgen. Färg kan användas för att kategorisera anteckningar, t.ex. allmänna helgdagar, externa händelser, spårningsproblem. |
   | [!UICONTROL Scope] | (Valfritt) Dra och släpp mätvärdena som utlöser anteckningen. Dra och släpp sedan de dimensioner eller segment som fungerar som filter (d.v.s. som anteckningen ska vara synlig med). Om du inte anger ett omfång kommer anteckningen att gälla för alla dina data.<ul><li>**[!UICONTROL Any of these metrics are present]**: Dra och släpp upp till 10 mätvärden som utlöser kommentaren som ska visas.</li><li>**[!UICONTROL With all of these filters]**: Dra och släpp upp till 10 dimensioner eller segment som ska filtreras när anteckningen visas.</li></ul><p>Användningsexempel: En eVar har slutat samla in data för ett visst datumintervall. Dra eVarna till dialogrutan **[!UICONTROL Any of these metrics are present]**. Eller så rapporterar [!UICONTROL Visits]-måttet inga data - följ samma process.<p>**Obs!** Alla anteckningar som används på en komponent som sedan används som en del av ett beräknat mått eller en segmentdefinition ärver INTE automatiskt anteckningen. Det önskade beräknade måttet måste också läggas till i omfångsavsnittet för att anteckningen ska kunna visas. En ny anteckning bör dock skapas för alla segment som du vill kommentera med samma information.<p>Exempel: Du använder en anteckning för [!UICONTROL Orders] på en viss dag. Du använder sedan [!UICONTROL Orders] i ett beräknat mått för samma datumintervall. Det nya beräknade måttet visar inte automatiskt anteckningen för order. Det beräknade måttet måste också läggas till i omfångsavsnittet för att anteckningen ska visas. |
   | [!UICONTROL Apply to all report suites] | Som standard gäller anteckningen för den ursprungliga rapportsviten. Genom att markera den här rutan kan du göra så att anteckningen gäller för alla rapportsviter i företaget. |

   {style="table-layout:auto"}

1. Klicka på **[!UICONTROL Save]**.
