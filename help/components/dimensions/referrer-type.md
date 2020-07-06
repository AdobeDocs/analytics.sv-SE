---
title: Referenstyp
description: Vilken typ av referent det är, beroende på varifrån besökaren kom.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# Referenstyp

Dimensionerna Refererartyp rapporterar vilka generiska kanaler besökarna klickade igenom för att komma till din webbplats. Adobe behåller reglerna för varje dimensionsvärde, till skillnad från [marknadsföringskanaler](marketing-channel.md), där organisationen behåller reglerna för varje kanal.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [träffens](referrer.md) referens, som är beroende av [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimensionsvärden

Dimensionsvärden är typen av träffens referent. Specifika värden är:

* **Typat/bokmärkt**: Det finns inga referensdata för träffen.
* **Sökmotorer**: Referenten kom från en identifierad sökmotor som innehåller en nyckelordsfrågesträng.
* **Sociala nätverk:**: Referensdata tillhör ett av Adobe erkänt socialt nätverk.
* **Andra webbplatser**: Referensdata tillhör inte en sökmotor eller ett socialt nätverk som Adobe känner igen.
* **Hårddisk**: Referenten kommer från en lokal kopia av en webbsida på besökarens hårddisk.
* **E-post**: Referenten härstammar från en URL med ett protokoll till `imap://` eller `mail://`. Inkluderar inte e-posttjänster online eftersom dessa vanligtvis använder `https://` protokoll.

### Sociala nätverk

Följande lista refererar till den söktabell för sociala nätverk som Adobe använder. Adobe tillhandahåller den här listan som en tjänst åt Adobe Analytics-kunder. Om du vill rekommendera Adobe att lägga till en domän i listan ska du ha en supportrepresentant i din organisation. Kontakta kundtjänst.

>[!NOTE]
>
>Den här listan skiljer sig från standardlistan med sociala nätverk i [bearbetningsreglerna](../c-marketing-channels/c-rules.md)för marknadsföringskanaler.

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `yozm.daum.net`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Sökmotorer i dimensionsvärdet &quot;Andra webbplatser&quot;

När du visar specifika domäner i dimensionen &quot;Refererartyp&quot; kan det finnas domäner som du förväntar dig under &quot;Sökmotorer&quot; i stället för under &quot;Andra webbplatser&quot;. Du kan till exempel se `'google.com'` under Andra webbplatser.

* **Sökmotordomäner i dimensionsvärdet** Sökmotorer: Referenten uppfyllde alla kriterier för att klassificeras som sökmotor av Adobe. Den refererande domänen är en giltig sökmotor *och* den refererande URL:en innehåller en nyckelordsfrågesträngsparameter.
* **Sökmotordomäner i dimensionsvärdet** Andra webbplatser: Den refererande URL:en uppfyllde inte alla kriterier för att klassificeras som sökmotor. Vanliga exempel är underdomäner som är dedikerade till andra funktioner förutom sökning. Till exempel, `mail.google.com` eller `autos.yahoo.com` är inte sökmotorer, men finns på en toppnivådomän som vanligtvis är kopplad till sökning. Dessa underdomäner innehåller inte någon nyckelordsfrågesträng, vilket är orsaken till att de ingår i Andra webbplatser i stället för Sökmotorer.
