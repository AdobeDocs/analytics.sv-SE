---
title: Referenstyp
description: Vilken typ av referent det är, beroende på varifrån besökaren kom.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: 825cded49c0ff456925e522ae2d0660b09ea6edd
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Referenstyp

Referenstypen [dimension](overview.md) rapporterar vilka generiska kanaler besökarna klickade igenom för att komma till din webbplats. Adobe underhåller reglerna för varje dimensionsobjekt, till skillnad från [marknadsföringskanaler](marketing-channel.md), där din organisation underhåller regler för varje kanal.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [referenten](referrer.md) för träffen, som är beroende av [interna URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimension-objekt

Bland Dimension-objekten finns typen av referent för träffen. Specifika värden är:

* **Typed/Bookmarked**: Det finns inga referensdata för träffen.
* **Sökmotorer**: Referenten kom från en identifierad sökmotor som innehåller en nyckelordsfrågesträng.
* **Sociala nätverk:**: Referensdata tillhörde ett socialt nätverk som känns igen av Adobe.
* **Andra webbplatser**: Referensdata tillhör inte en sökmotor eller ett socialt nätverk som Adobe känner igen.
* **Hårddisk**: Referenten kom från en lokal kopia av en webbsida på besökarens hårddisk.
* **E-post**: Referenten kom från en URL med protokollet `imap://` eller `mail://`. Inkluderar inte e-posttjänster online eftersom dessa vanligtvis använder protokollet `https://`.

### Sociala nätverk

Följande lista refererar till söktabellen&quot;Sociala nätverk&quot; som används i Adobe. Adobe tillhandahåller den här listan som en tjänst åt Adobe Analytics kunder. Om du vill rekommendera Adobe att lägga till en domän i den här listan ska du be en supportrepresentant i din organisation kontakta Kundtjänst.

>[!NOTE]
>
>Den här listan skiljer sig från standardlistan med sociala nätverk i [Bearbetningsregler för marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `bsky.app`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
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
* `go.bsky.app`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `hi5.com`
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `likeshop.me`
* `linkedin.com`
* `linkin.bio`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
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
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `threads.com`
* `threads.net`
* `tiktok.com`
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
* `web-cdn.bsky.app`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `x.com`
* `xanga.com`
* `xing.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Sökmotorer i dimensionsobjektet Andra webbplatser

När du visar specifika domäner i dimensionen &quot;Refererartyp&quot; kan det finnas domäner som du förväntar dig under &quot;Sökmotorer&quot; i stället för under &quot;Andra webbplatser&quot;. Du kan till exempel se `'google.com'` under Andra webbplatser.

* **Sökmotordomäner i dimensionsobjektet för sökmotorer**: Referenten uppfyllde alla villkor för att klassificeras som sökmotor av Adobe. Den refererande domänen är en giltig sökmotor, *och* den refererande URL:en innehåller en nyckelordsfrågesträngsparameter.
* **Sökmotordomäner i dimensionsobjektet Andra webbplatser**: Den refererande URL:en uppfyllde inte alla kriterier för att klassificeras som en sökmotor. Vanliga exempel är underdomäner som är dedikerade till andra funktioner förutom sökning. `mail.google.com` eller `autos.yahoo.com` är till exempel inte sökmotorer, utan finns i en toppnivådomän som vanligtvis är kopplad till sökning. Dessa underdomäner innehåller inte någon nyckelordsfrågesträng, vilket är orsaken till att de ingår i Andra webbplatser i stället för Sökmotorer.
