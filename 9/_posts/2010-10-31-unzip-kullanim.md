---
layout: post
title: unzip ile zip dosyalarını açmak
---

unzip ile zip dosyası içindeki dosyaları çıkarmak veya listelemek

**Kurulum**

        $ sudo apt-get install unzip

**Kullanım**

elimizde yeni.zip isminde bir rar dosyası olsun

- zip dosyası içindeki dosyaları olduğu gibi çıkarmak için:

        $ unzip yeni.zip

- zip dosyası içindeki dosyaların hakkında ayrıntılı bilgi endinmek için:

        $ unzip -v yeni.zip

        Archive:  /home/emin/yeni.zip
          Length      Date    Time    Name
        ---------  ---------- -----   ----
                0  2010-10-31 16:47   yeni/
                0  2010-10-31 16:47   yeni/extra/
                0  2010-10-31 16:47   yeni/default
                0  2010-10-31 16:47   yeni/extra/ngin
        ---------                     -------
                0                     4 files

- zip dosyası içindeki dosyaları liste halinde görmek için:

        $ unzip -l yeni.zip

        Archive:  /home/emin/yeni.zip
         Length   Method    Size  Cmpr    Date    Time   CRC-32   Name
        --------  ------  ------- ---- ---------- ----- --------  ----
               0  Stored        0   0% 2010-10-31 16:47 00000000  yeni/
               0  Stored        0   0% 2010-10-31 16:47 00000000  yeni/extra/
               0  Stored        0   0% 2010-10-31 16:47 00000000  yeni/default
               0  Stored        0   0% 2010-10-31 16:47 00000000  yeni/extra/ngin
        --------          -------  ---                            -------
               0                0   0%                            4 files

şimdide kullanıcı dizininde yeni adında içinde çeşitli dosyalar ve dizinler bulunan bir dizinimiz olsun 

- birden fazla dosyayı zipleme:

        $ zip zip_adi ~/yeni/*

- dosyaları şifre ile birlikte ziplemek için:

        $ zip -e zip_adi ~/yeni/*

bu komutu girdikten sonra sizden zip dosyası için şifre istenecek


zip programı ziplenecek dosyaları belirli bir düzene göre zipler yanı sıkıştırır. 
Bunu aldığı argümanlarla belirler. zip programının 10 çeşit zipleme çeşiti var. 
0'dan başlayarak 9'a kadar aldığı argümanla sıkıştırma oranını belirler.

- sıkıştırmadan sadece arşivlemek için

        $ zip -0 zip_adi ~/yeni/*

- hem arşivlemek için hem de ziplemek yani sıkıştırmak için

        $ zip -9 zip_adi ~/yeni/*

bu tip ziplemede her seviyede zipleme süresi artacaktır.
Sıkıştırma oranı ne kadar artarsa sürede o kadar artar.


unzip programını bu şekilde kullanıyoruz

