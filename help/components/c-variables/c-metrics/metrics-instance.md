---
description: Antalet gånger som ett värde har angetts för en variabel.
keywords: instances
title: Instanser
topic: Metrics
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Instanser

Antalet gånger som ett värde har angetts för en variabel.

Förekomster räknas för alla träfftyper, men räknas inte när ett värde registreras för en variabel vid en efterföljande träff på grund av persistence.

Om en användare till exempel kommer till din webbplats via [!DNL example.com]innehåller den första bildbegäran på din webbplats referenten till [!DNL example.com]. När det här värdet anges tilldelas en instans [!DNL example.com] även om referenten registreras för alla sidor som visas under besöket.

Instanser för konverteringsvariabler i datalagret lades till i mitten av 2011, vilket gör att datalagerbegäranden kan behandla en specifik konverteringsvariabelinstans som ett mått. Dessa mått är inte tillgängliga för rapportering innan de introducerades.
