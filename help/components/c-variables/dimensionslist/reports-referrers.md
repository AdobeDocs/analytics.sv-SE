---
title: Referenter
description: Visar URL:en för föregående träff, om träffen låg utanför din plats.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# Referenter

Dimensionen Referent visar den URL som besökarna kom ifrån innan de kom till er webbplats. Om en besökare till exempel klickar på en länk från `example.com/example-page.html` och anländer till din webbplats, `example.com/example-page.html` är det referenten om den inte är definierad som en del av din domän.

Denna dimension kräver att du konfigurerar rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter ser Adobe Analytics alla domäner som interna för din webbplats.

## Dimensionsegenskaper

* Den här dimensionen använder den senaste allokeringen som standard.
* Den här dimensionen upphör som standard efter besök.
* Denna dimension omfattas av den unika gränsen på 500 kB innan dimensionsvärden grupperas under (lågtrafik). Datalagret har ingen unik gräns.
* Om det inte finns något referensvärde för ett mätvärde grupperas det under `Typed/Bookmarked`.
* Denna dimension sätts vanligtvis in vid besökets första träff, men kan ställas in vid mitt besök.

## Felsökning

**F: Varför ser jag`googleusercontent.com`som ett dimensionsvärde?**

S: [Google](https://about.google/) använder domänen `googleusercontent.com` för sitt värdbaserade innehåll. Innehåll på webben:

* **Cachelagrade sidor**: Googles spindlar krymper ständigt webben och sparar webbsidor om de skulle tas offline eller på annat sätt vara otillgängliga. Dessa cachelagrade sidor är tillgängliga bredvid alla sökresultat genom att klicka på länken &quot;Cached&quot; från någon av Googles sökresultatsidor. När en användare klickar på den här länken och sedan tittar på det ursprungliga innehållet på din webbplats, `googleusercontent.com` visas det som sin referensdomän. Dessa sidor har underdomänen `webcache.googleusercontent.com`.
* **Översatta sidor**: Google erbjuder en robust och bekväm översättningstjänst. När du visar en webbplats med den här tjänsten kommer den från `googleusercontent.com`. Refererardimensionen visar URL:er från den här domänen om användaren klickar på en länk för att återgå till det ursprungliga innehållet. Dessa sidor har underdomänen `translate.googleusercontent.com`.
