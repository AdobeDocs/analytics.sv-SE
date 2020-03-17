---
description: Beskriver hur du skapar ett mätvärde som visar vilka marknadsföringskanaler som hjälper dig att hantera beställningar. Detta kan anpassas till alla dimensioner eller framgångsrika händelser av intresse.
title: Mätvärde för orderassistenter
uuid: 7c82227a-7fcc-486f-bef8-164ea84af77c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Mätvärde för orderassistenter

Beskriver hur du skapar ett mätvärde som visar vilka marknadsföringskanaler som hjälper dig att hantera beställningar. Detta kan anpassas till alla dimensioner eller framgångsrika händelser av intresse.

1. Ange måttet&quot;Assisted Orders&quot; i beräkningsverktyget.
1. Dra i ett ordningstal på arbetsytan Definition. Justera sedan attribueringsmodellen med inställningsverktyget genom att markera **[!UICONTROL Use non-default attribution models]** kryssrutan.

   ![](assets/attr-model.png)

1. Välj **[!UICONTROL Custom]** som attribueringsmodell. Ändra bredderna till 0 (start), 100 (spelare) och 0 (närmare).

   ![](assets/custom-attr-model.png)

1. Spara måtten.
1. Skapa en frihandstabell i Analysis Workspace med mått för marknadsföringskanal, beställningar och nya mätvärden för Assisted Orders.

   ![](assets/mktg-channel-assists.png)

Det här är ett enkelt sätt att se vilka marknadsföringskanaler som har hjälpt till med körorder. Du kan också högerklicka på ett mätresultat i en frihandstabell och justera attribueringsmodellen direkt i tabellen.
