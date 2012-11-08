---
layout: post
title: Terminalde Takvim İşlemleri
---

konsoldan tarih bilgilerine ulaşabileceğiniz süper bir program: cal

kendisi ile biraz önce tanıştım hemen ufak tefek aktarımını yapayım

- içinde bulunduğunuz ayı görüntülemek için bu komutu girmeniz yeterli

        $ cal

- içinde bulunduğunuz ay ile birlikte bir önceki ve bir sonraki ayı gösterir

        $ cal -3

- içinde bulunduğunuz ayın günlerini yılın hangi günleri olduğunu gösterir

        $ cal -j

- içinde bulunduğunuz yılın tüm aylarını görüntülemek için:

        $ cal -y

- eğer herhangi bir yılın herhangi bir ayının bilgilerini öğrenmek istiyorsanız

        $ cal november 2008

- hatta türkçe şekliyle

        $ cal ocak 2003

- hatta ayı da sayıyla girebilirsiniz

        $ cal 5 1996


genel bir örnek görelim

        $ cal şubat 2007

        çıktı:

            Ağustos 2010
        Pz Sa Çr Pr Cu Ct Pa
                           1
         2  3  4  5  6  7  8
         9 10 11 12 13 14 15
        16 17 18 19 20 21 22
        23 24 25 26 27 28 29
        30 31


herhangi bir yılın herhangi bir ayınının günlerinin o yılın hangi günlerine denk geldiğini öğrenelim

        $ cal -j 3 1919

        çıktı:

                 Mart 1919
         Pz  Sa  Çr  Pr  Cu  Ct  Pa
                             60  61
         62  63  64  65  66  67  68
         69  70  71  72  73  74  75
         76  77  78  79  80  81  82
         83  84  85  86  87  88  89
         90



