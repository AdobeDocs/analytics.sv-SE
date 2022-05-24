---
title: Referenstyp
description: Vilken typ av referent det är, beroende på varifrån besökaren kom.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: 14f0ca66fdbd0468ef6b6eef41fcc020b43cddc9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Referenstyp

Dimensionerna Refererartyp rapporterar vilka generiska kanaler besökarna klickade igenom för att komma till din webbplats. Adobe behåller reglerna för varje dimensionsobjekt, till skillnad från [Marknadsföringskanaler](marketing-channel.md), där organisationen upprätthåller regler för varje kanal.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [hänvisare](referrer.md) av träffen, som är beroende av [Interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimensioner

Bland Dimensionerna finns typen av referent för träffen. Specifika värden är:

* **Typat/bokmärkt**: Det finns inga referensdata för träffen.
* **Sökmotorer**: Referenten kom från en identifierad sökmotor som innehåller en nyckelordsfrågesträng.
* **Sociala nätverk:**: Referensdata hör till ett socialt nätverk som Adobe känner igen.
* **Andra webbplatser**: Referensdata tillhör inte en sökmotor eller ett socialt nätverk som Adobe känner igen.
* **Hårddisk**: Referenten kommer från en lokal kopia av en webbsida på besökarens hårddisk.
* **E-post**: Referenten härstammar från en URL med protokollet `imap://` eller `mail://`. Inkluderar inte e-posttjänster online eftersom dessa vanligtvis används `https://` -protokoll.

### Sociala nätverk

Följande lista refererar till uppslagstabellen&quot;Sociala nätverk&quot; som används i Adobe. Adobe tillhandahåller denna lista som en tjänst åt Adobe Analytics kunder. Om du vill rekommendera Adobe att lägga till en domän i listan ska du be en supportrepresentant i organisationen kontakta Kundtjänst.

>[!NOTE]
>
>Den här listan skiljer sig från standardlistan med sociala nätverk i [Bearbetningsregler för marknadsföringskanaler](../c-marketing-channels/c-rules.md).

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

### Sökmotorer i dimensionsobjektet Andra webbplatser

När du visar specifika domäner i dimensionen &quot;Refererartyp&quot; kan det finnas domäner som du förväntar dig under &quot;Sökmotorer&quot; i stället för under &quot;Andra webbplatser&quot;. Du kan till exempel se `'google.com'` under Andra webbplatser.

* **Sökmotordomäner i dimensionsobjektet Sökmotorer**: Referenten uppfyllde alla kriterier för att klassas som sökmotor av Adobe. Den refererande domänen är en giltig sökmotor, *och* den refererande URL:en innehåller en nyckelordsfrågesträngsparameter.
* **Sökmotordomäner i dimensionsobjektet Andra webbplatser**: Den refererande URL:en uppfyllde inte alla kriterier för att klassificeras som sökmotor. Vanliga exempel är underdomäner som är dedikerade till andra funktioner förutom sökning. Till exempel: `mail.google.com` eller `autos.yahoo.com` är inte sökmotorer, men finns på en toppnivådomän som vanligtvis är kopplad till sökning. Dessa underdomäner innehåller inte någon nyckelordsfrågesträng, vilket är orsaken till att de ingår i Andra webbplatser i stället för Sökmotorer.
