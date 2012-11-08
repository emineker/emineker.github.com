---
layout: post
title: ubuntu sürümünüzü öğrenin
---

Konsoldan tek bir komutla ubuntu sürümünüzü öğrenelim. Aslında bu sadece bir dosya ve bize içindeki bilgiler yani bilgisayarımızın ubuntu sürüm bilgileri lazım. Bunun için bu dosyanın içini cat komutu ile görüntülememiz yeterli.

        $ cat /etc/lsb-release

çıktı ise şu şekilde olacak:

        DISTRIB_ID=Ubuntu
        DISTRIB_RELEASE=10.10
        DISTRIB_CODENAME=maverick
        DISTRIB_DESCRIPTION="Ubuntu 10.10"


tam bu noktada adamlar yapmış diyoruz yine meğer betiği de varmış

hemen konsola girin ve şunu yazın

        $ lsb_release -a


tabiki yukarıdaki bilgiler benim bilgisayarımdaki ubuntu sürümüne göre sonuç veriyor sizde faklı sonuçlar vermesi doğaldır.

