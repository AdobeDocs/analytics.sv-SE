---
description: Lär dig att strukturera projekt i Analysis Workspace. Kuration begränsar åtkomsten till komponenter innan du delar ett projekt.
keywords: Analysis Workspace kurser
title: Kuratprojekt
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: 41d067ab852f4eb5c4a1368ade364fdb706bb9d9
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---

# Kuratprojekt

Med kurering kan du begränsa komponenterna (mått, mått, segment, datumintervall) innan du delar ett projekt. När en mottagare öppnar projektet visas en begränsad uppsättning komponenter som du har valt för dem. Kurering är ett valfritt men rekommenderat steg innan du delar ett projekt.

>[!NOTE]
> Produktprofiler är den primära mekanismen som styr vilka komponenter en användare kan se. De hanteras via Adobe Experience Cloud Admin Console. Curation är ett sekundärt filter.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Kuratprojekt](https://video.tv.adobe.com/v/24711?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Använd projektstrukturering

1. Välj **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
Komponenterna som används i projektet läggs till automatiskt.
Om ett projekt har flera rapportsviter visas ett aktuellt släppmål för varje rapportsvit i projektet.
1. (Valfritt) Om du vill lägga till fler komponenter drar du de komponenter du vill dela från den vänstra panelen till släppzonen **[!UICONTROL Curate components]** för datavyn.
1. Välj **[!UICONTROL Done]**.


![](assets/curation-field.png)

När en mottagare öppnar ett välstrukturerat projekt visas endast den urval av komponenter som du har definierat:


## Ta bort projektstrukturering

Så här tar du bort projektstrukturering och återställer alla komponenter i den vänstra listen:

1. Välj **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Välj **[!UICONTROL Remove Curation]**.
1. Välj **[!UICONTROL Done]**.

## Vuxen rapportsvitens urval

Om du vill använda kurering på rapportsvitnivå, så att den tillämpas på många projekt samtidigt, kan du [strukturera komponenter i en virtuell rapportserie](https://experienceleague.adobe.com/sv/docs/analytics/components/virtual-report-suites/vrs-components).

>[!NOTE]
>
> Vuxenkurering används alltid innan projektet struktureras. Även om ditt kuraterade projekt innehåller vissa komponenter, filtreras de bort om den aktuella virtuella rapportsviten inte innehåller dessa komponenter.
> 

## Alternativ för komponenturval

I ett välstrukturerat projekt eller en virtuell rapportserie får mottagaren alternativet att **[!UICONTROL Show All]** komponenter i den vänstra listen. [!UICONTROL Show All] visar olika uppsättningar av komponenter, beroende på:

* Användarens behörighetsnivå (admin eller icke-admin)
* Projektroll (ägare/redigerare eller inte)
* Typ av kuration som används (Virtual Report SuiteS eller Project)
* Komponenter som ägs av eller delas med användaren. Ägda/delade komponenter omfattar segment, beräknade värden och datumintervall. De innehåller inte implementerade komponenter som eVars, props och anpassade händelser.

Obs! Roller som inte är administratörsvy har inte åtkomst till den vänstra listen i ett projekt, så de har utelämnats från tabellen nedan.

| Kurvtyp | Administratörer | Projektägare eller redigeringsroll som inte är administratör | Dubblettroll som inte är administratör |
|---|---|---|---|
| **Aktuell virtuell rapportserie** | Alla komponenter i den virtuella rapportsviten som inte är förvaltade | Icke-förvaltade virtuella rapportsvitkomponenter som den här rollen äger eller som har delats med dem | Icke-förvaltade virtuella rapportsvitkomponenter som den här rollen äger eller som har delats med dem |
| **Kuraterat projekt** | Alla projektkomponenter som inte är kuraterade | Alla projektkomponenter som inte är kuraterade | Ej förvaltade projektkomponenter som den här rollen äger eller som har delats med dem |
| **Kuraterat projekt i en kuraterad virtuell rapportsserie** | Alla komponenter som inte är förvaltade, visas under **[!UICONTROL Non-Curated Project Components]** och **[!UICONTROL Non-Curated Virtual report suite components]** | Alla icke-förvaltade projektkomponenter OCH icke-förvaltade virtuella rapportsvitkomponenter som den här rollen äger eller som har delats med dem | Virtuellt rapportpaket och projektkomponenter som den här rollen äger eller som har delats med dem är inte förvaltade |
