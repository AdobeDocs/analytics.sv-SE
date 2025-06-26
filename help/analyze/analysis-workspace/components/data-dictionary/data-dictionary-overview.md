---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkänd, som är dubbletter osv.
title: Översikt över dataordlistan
feature: Components
role: User, Admin
exl-id: ecc62287-dc20-41b3-9430-f14ea9fc05e6
source-git-commit: 74ef4e73b6ed1e2a4ad498e2314af704acb6d8cb
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 0%

---


# Översikt över dataordlistan {#data-dictionary-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="Dataordlista"
>abstract="Med Data Dictionary kan både användare och administratörer hålla reda på och bättre förstå komponenterna i sin Analytics-miljö. <br/>Analysadministratörer ansvarar för att strukturera information om varje komponent i Data Dictionary."

<!-- markdownlint-enable MD034 -->


Med Data Dictionary i Analysis Workspace kan både användare och administratörer hålla reda på och bättre förstå komponenterna i sin Analytics-miljö.

Analysadministratörer ansvarar för att strukturera information om varje komponent i Data Dictionary så att den blir tillgänglig för användarna.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dataordlista för Analysis Workspace](https://video.tv.adobe.com/v/3418028/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]



## Fördelar för användare

Med Data Dictionary får användarna en bättre förståelse för alla komponenter som är tillgängliga för dem.

Den information som finns i ordlistan innehåller:

* En komponents funktion och avsedda användning.

* Komponenter som vanligtvis används med den som du visar.

* Komponenter som liknar de som du visar.

* Anger om en komponent har godkänts av systemadministratören.

Mer information om hur du får åtkomst till datamordlistan och om vilken information som finns i den finns i [Visa komponentinformation i datamordlistan](view-data-dictionary.md).

## Fördelar för administratörer

Med Data Dictionary kan systemadministratörer hålla reda på och strukturera komponenterna i sin Analytics-miljö.

Analysadministratörer kan använda Data Dictionary för följande syften:

* Identifiera duplicerade komponenter som behöver konsolideras.

* Identifiera komponenter som inte samlar in några data så att de kan uppdateras eller tas bort.

* Identifiera komponenter som ännu inte har godkänts.

* Uppdatera komponentbeskrivningar direkt i Analysis Workspace. Alla uppdateringar som görs av komponentbeskrivningarna i datamallen återspeglas i datavyn.

  På samma sätt återspeglas alla uppdateringar av komponentbeskrivningarna i datavyn i Analysis Workspace.

  Mer information om hur du lägger till komponentbeskrivningar i antingen Analysis Workspace eller en datavy finns i [Lägga till komponentbeskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Åtkomst till dataordlistan

Du kan komma åt datamodlistan på något av följande sätt i Analysis Workspace:

![Ikon för datamordlista i den vänstra panelen](assets/data-dictionary-access.png)

* Från ![Bokmärke](/help/assets/icons/Bookmark.svg) på knapppanelen.



* Från ![Bokmärke](/help/assets/icons/Bookmark.svg) i infoporten för en komponent.


Mer information om de olika alternativen som är tillgängliga i datamordlistan finns i [Visa komponentinformation i datamordlistan](view-data-dictionary.md).

## Uppdatera och strukturera dataordlistan

Adobe Analytics-administratörer ansvarar för att upprätthålla en felfri datamordlista för sin organisation, vilket beskrivs i [Övervaka datamordlistehälsa](monitor-data-dictionary-health.md).

Som en del av den här processen kan Adobe Analytics-administratörer redigera information om varje komponent i dataordlistan enligt beskrivningen i [Redigera komponentposter i datamappningen](edit-entries-data-dictionary.md).

## Flytta, minimera eller stänga datamappningslistan

När du öppnar dataordlistan (enligt beskrivningen i [Åtkomst till dataordlistan](#access-the-data-dictionary)) visas den som ett fönster ovanpå Analysis Workspace.

Du kan ändra fönstret för datamordlistan på något av följande sätt:

* Dra det till valfri plats i Analysis Workspace

  Om du stänger och öppnar Analysis Workspace igen finns fönstret Datamordlista kvar på den plats där du senast flyttade det. <!--True?-->

* Minimera fönstret.

  När värdet är minimerat visas datamordlistan som en blå flik i det nedre högra hörnet av Analysis Workspace.

  När du väljer den blå fliken öppnas Data Dictionary för den komponent som du senast visade.

* Stäng fönstret.


<!--
# Data Dictionary overview

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment.   

Analytics administrators are responsible for curating information about each component in the Data Dictionary to make it available to users.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data dictionary](https://video.tv.adobe.com/v/3418028?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Benefits for users

The Data Dictionary helps users gain a better understanding of each component that is available to them. 

Information available in the Data Dictionary includes: 

* A component's function and intended use

* Components typically used with the one you are viewing

* Components that are similar to the one you are viewing

* Whether a component is approved by the system administrator 

For information about how to access the Data Dictionary and for details about the information it contains, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Benefits for administrators

The Data Dictionary helps system administrators keep track of and curate the components in their Analytics environment. 

Following are some of the ways Analytics administrators can use the Data Dictionary: 

* Identify duplicate components that need to be consolidated.

* Identify components that aren't collecting any data so they can be either updated or deleted.

* Identify components that are not yet approved.

* Update component descriptions directly in Analysis Workspace. Any updates made to component descriptions in the Data Dictionary are reflected in the Report Suite.

  Similarly, any updates made to component descriptions in the Report Suite are reflected in Analysis Workspace.

  For more information about adding component descriptions in either Analysis Workspace or in a Report Suite, see [Add component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Access the Data Dictionary

You can access the Data Dictionary in any of the following ways within Analysis Workspace:

* From the **Data Dictionary** icon in the left rail.

  ![Data Dictionary icon in the left rail](assets/data-dictionary-access-icon.png)

* From the **Data Dictionary** icon within the info popover of a component. 

  ![Data Dictionary icon in info popover](assets/data-dictionary-access-infopopover.png)


For detailed information about the various options available in the Data Dictionary, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Update and curate the Data Dictionary

Analytics administrators are responsible for maintaining a healthy Data Dictionary for their organization, as described in [Monitor Data Dictionary Health](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).

As part of this process, Analytics administrators can edit information about each component in the data dictionary, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

## Move, minimize, or close the Data Dictionary

When you open the Data Dictionary (as described in [Access the Data Dictionary](#access-the-data-dictionary)), it displays as a window on top of Analysis Workspace. 

You can manipulate the Data Dictionary window in any of the following ways:

* Drag it to any area within Analysis Workspace 

  If you close and re-open Analysis Workspace, the Data Dictionary window remains in the location where you last moved it.

* Minimize it

  When minimized, the Data Dictionary appears as a blue tab in the lower-right corner of Analysis Workspace.

  When you select the blue tab, the Data Dictionary opens to the component you were most recently viewing. 

* Close it

-->