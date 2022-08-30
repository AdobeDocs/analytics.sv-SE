---
description: Dialogrutan Datastyrning i Administratörsverktyg ger en översikt över vilka rapportsviter som har konfigurerats för datastyrning, om de har mappats till en Experience Cloud-organisation och om det finns en policy om datalagring för den här rapportsviten.
title: Visa/hantera inställningar för datastyrning i rapportsviten
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 538d5bcea449ecb868ff9ebcce4ca742f91b4a87
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 75%

---

# Visa/hantera inställningar för datastyrning i rapportsviten

Dialogrutan Datastyrning i Administratörsverktyg ger en översikt över vilka rapportsviter som har konfigurerats för datastyrning, om de har mappats till en Experience Cloud-organisation och om det finns en policy om datalagring för den här rapportsviten.

1. Logga in på Adobe Experience Cloud.
1. Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]**.

>[!NOTE]
>
>Om du inte ser det här menyalternativet måste du läggas till i en [produktprofil i Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html) med behörigheter för den här funktionen.

1. Visa alla rapportsviter som ingår i ditt inloggningsföretag:

   ![](assets/privacy_setup_an.png)

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL Report Suites]** | På den första raden visas rapportsvitens egna namn. Den andra raden innehåller rapportsvitens interna namn. Om du kan ange etiketter för en rapportsvit blir den första raden en klickbar länk som tar dig till etikettsidan. |
| **[!UICONTROL Organization Mapping]** | <ul><li>Mappad: Den här rapportsviten har redan mappats till samma Experience Cloud-organisation som det Analytics-inloggningsföretag du är inloggad på. Endast rapportsviter som har den här inställningen kan etiketteras.</li><li>Mappad till en annan organisation: En annan Experience Cloud-organisation har redan mappat den här rapportsviten till sin organisation.</li></ul> |
| **[!UICONTROL Data Retention Policy]** | Implementeringen av datasekretess i Analytics kräver att du har en policy för datalagring. Den här inställningen visar om:<ul><li>det finns en policy för datalagring för den här rapportsviten, och</li><li>Hur länge Adobe lagrar data innan de raderas. Standardperioden för datalagring är 25 månader.</li></ul>**Anteckning**: Adobe Analytics kan inte hjälpa dig med att bearbeta förfrågningar till API:t för datasekretess, d.v.s. att bearbeta de förfrågningar om åtkomst eller borttagning som du får från slutanvändarna, om datalagringsperioden inte har ställts in. Kontakta din Customer Success Manager för att ange din datalagringsperiod. |
| **[!UICONTROL Groups]** | Grupperingsfunktionen är för närvarande inte implementerad. |
| Vänster sidofält | Klicka på kanalikonen för att öppna eller stänga sidorutan. The [!UICONTROL Organization Mapping] I visas antalet rapportsviter som hör till de beskrivna kategorierna. The [!UICONTROL Data Retention Policy] -avsnittet visar varje unik datalagringspolicy som finns för din organisation och antalet rapportsviter som har tilldelats den lagringspolicyn. |
| **[!UICONTROL Export to CSV]** | Om du markerar kryssrutan bredvid en eller flera rapportsviter visas alternativet  Exportera till CSV . Med det här alternativet kan du hämta en CSV-fil som innehåller alla aktuella etikettdefinitioner för alla variabler för alla valda rapportsviter. Vi rekommenderar att ditt juridiska team granskar dina etikettval och det här alternativet underlättar den här granskningen. I stället för att behöva utföra granskningen när du är inloggad i användargränssnittet för datastyrning kan du dela .CSV-filen med dem. |
