---
layout: post
title: unrar ile rar dosyalarını açmak
---

unrar ile rar içindeki dosyaları çıkarmak veya listelemek

**Kurulum**

        $ sudo apt-get install unrar

**Kullanım**

elimizde yeni.rar isminde bir rar dosyası olsun

- rar dosyası içindeki dosyaları olduğu gibi çıkarmak için:

        $ unrar -x yeni.rar

- rar dosyasındaki tüm 'dosya'ları bulunduğunuz dizine çıkarmak için:

        $ unrar -e yeni.rar

- rar dosyası içindeki dosyaları listelemek için:

        $ unrar -l yeni.rar
        
        çıktı:

        UNRAR 3.93 freeware      Copyright (c) 1993-2010 Alexander Roshal

        Archive yeni.rar

        Name             Size   Packed Ratio  Date   Time     Attr      CRC   Meth Ver
        -------------------------------------------------------------------------------
        bilgisayar          0        8   0% 29-10-10 16:04 -rw-r--r-- 00000000 m3b 2.9
        ingilizce           0        8   0% 29-10-10 16:17 -rw-r--r-- 00000000 m3b 2.9
        dersler             0        0   0% 29-10-10 16:20 drwxr-xr-x 00000000 m0  2.0
        yeni                0        0   0% 29-10-10 16:20 drwxr-xr-x 00000000 m0  2.0
        -------------------------------------------------------------------------------
        4                0       16   0%

- rar içindeki dosyaları test etmek için

        $ unrar -t yeni.rar

        çıktı:

        UNRAR 3.93 freeware      Copyright (c) 1993-2010 Alexander Roshal

        Testing archive yeni.rar

        Testing     yeni/bilgisayar
                         12%  OK 
        Testing     yeni/dersler/ingilizce
                         37%  OK 
        Testing     yeni/dersler
                        OK
        Testing     yeni
                        OK
        All OK

- rar içindeki dosyaların stdout çıkışlarını görmek için:

        $ unrar -p yeni.rar

        çıktı:

        UNRAR 3.93 freeware      Copyright (c) 1993-2010 Alexander Roshal


        Extracting from yeni.rar

        ------ Printing yeni/bilgisayar

         12%
        ------ Printing yeni/dersler/ingilizce

         37%
        All OK

- rar içindeki dosyaları tüm yol bilgileri ile listelemek için:

        $ unrar -v yeni.rar

        çıktı:

        UNRAR 3.93 freeware      Copyright (c) 1993-2010 Alexander Roshal

        Archive yeni.rar

        Pathname/Comment
                        Size   Packed Ratio  Date   Time     Attr      CRC   Meth Ver
        -------------------------------------------------------------------------------
        yeni/bilgisayar
                        0        8   0% 29-10-10 16:04 -rw-r--r-- 00000000 m3b 2.9
        yeni/dersler/ingilizce
                        0        8   0% 29-10-10 16:17 -rw-r--r-- 00000000 m3b 2.9
        yeni/dersler
                        0        0   0% 29-10-10 16:20 drwxr-xr-x 00000000 m0  2.0
        yeni
                        0        0   0% 29-10-10 16:20 drwxr-xr-x 00000000 m0  2.0
        -------------------------------------------------------------------------------
        4               0       16   0%


unrar programının kullanımı bu şekilde

