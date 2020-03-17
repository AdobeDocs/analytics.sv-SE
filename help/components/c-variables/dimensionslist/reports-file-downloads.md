---
description: Filhämtningar hjälper dig att förstå hur ofta besökarna hämtar filer från din webbplats. Exempel på filhämtningar är ordprocessordokument, kalkylblad, ljudfiler, filmfiler, användarhandböcker och så vidare. Detta inkluderar både filer som sparas och öppnas direkt från webbläsaren och filer som sparas på användarens dator. I rapporten visas namnet på filen som hämtas, inklusive den fullständiga URL som krävs för att komma åt filen.
title: Filhämtningar
topic: Reports
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filhämtningar

Filhämtningar hjälper dig att förstå hur ofta besökarna hämtar filer från din webbplats. Exempel på filhämtningar är ordprocessordokument, kalkylblad, ljudfiler, filmfiler, användarhandböcker och så vidare. Detta inkluderar både filer som sparas och öppnas direkt från webbläsaren och filer som sparas på användarens dator. I rapporten visas namnet på filen som hämtas, inklusive den fullständiga URL som krävs för att komma åt filen.

**Navigering**

**[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Links]** > **[!UICONTROL File Downloads]**

Om den här rapporten inte är tillgänglig på standardplatsen, bör du kontakta dina administratörer som kan ha ändrat standardmenystrukturen för att bättre kunna tillgodose organisationens unika behov.

Använd den här rapporten för att:

* Bestäm vilka filer som laddas ned oftast från webbplatsen.
* Förstå om vissa filer laddas ned oftare under särskilda tidsperioder.
* Verifiera att alla format för ett visst dokument krävs.

   Du kanske för närvarande översätter dina användarhandböcker till tolv språk och gör dem tillgängliga via din webbplats. Med rapporter om nedladdning av filer vet du hur ofta varje manuell version laddas ned och kan bedöma värdet av att fortsätta att översätta användarhandboken till alla tolv språken.

**Felsökning**

Marknadsföringsrapporter samlar in information om filer som laddats ned från en sida på webbplatsen som innehåller JavaScript-kod. Vissa variabler måste dock finnas och ställas in korrekt så att filhämtningsinformation kan rapporteras. Om den här rapporten inte visar data, eller inte visar de förväntade värdena, följer du stegen nedan för att validera implementeringen.

1. Leta reda på den globala JavaScript-filen på din plats. Detta har ofta fått ett namn [!DNL s_code.js]men kan ha fått ett nytt namn. Om namnet har ändrats kan du söka efter värdet i JavaScript-filerna på webbplatsen, *`s.account`* som är en del av JavaScript-koden.

1. Leta reda på variabeln [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackdownllinks.html) i filen. Kontrollera att det är inställt på *true*

1. Leta reda på variabeln [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkdownfiletypes.html) . Kontrollera att alla filtillägg som behövs finns med i listan. Om det behövs lägger du till saknade tillägg som [!DNL .zip], [!DNL .pdf]och så vidare.)

Om dessa variabler verkar vara korrekt konfigurerade, men ändå inte tar emot data, bör de användare i organisationen som stöds kontakta Kundtjänst. [!UICONTROL File Downloads Report]
