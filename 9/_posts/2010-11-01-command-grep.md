---
layout: post
title: grep ile samanlıkta iğne arayalım
---

Grep yani 'Global Regular Expression Printer' daha yanisi de 'evrensel düzenli ifade yazicisi'dır. Adından da anlaşıldığı gibi dosyalarda, program çıktılarında (ki en önemli özelliği budur) vs. kullanılan muhteşem bir arama aracıdır. Örneklere bakalım hemen anlaşılacaktır zaten.


**bir dosya içersindeki belirli kelimeyi bulma**

- /etc/passwd dosyası içerisinden emin kelimesinin geçtiği satırları listeler

        $ grep emin /etc/passwd

- /etc/passwd dosyası içerisinden emin gecmeyen satırları listeler

        $ grep -v emin /etc/passwd

- /etc/passwd dosyası içersindeki emin dizgisinin kaç kez geçtiğini görmek istiyorsak -c (count) parametresi kullanılır

        $ grep -c emin /etc/passwd

- linux sistemlerinin büyük-küçük harf duyarlılığının olduğunu biliyoruz. bu sebebden dolayı Emin kelimesinin araması ile emin kelimesinin aranmasından elde edilen sonuçlar aynı olmayacaktır. bu duyarlılığı -i (–ignore-case) parametresi ile devre dışı bırakabiliriz.

        $ grep -i emin /etc/passwd

- eğer aramayı bir dizin içerisindeki tüm dosya ve alt dizinlere uygulamak istiyorsak -r (recursive) parametresi kullanılır

        $ grep -r emin /home/emin

- grep ile listelenen sonuçların dosya içerisinde hangi satırda olduğunu görmek için -n (line-number) parametresi kullanılır

        $ grep -n emin /etc/passwd

- çok fazla sonuç dönerse ve biz sadece ilk birkaç sonuç ile ilgileneceksek -m (–max-count) parametresi kullanılır

        $ grep -m 4 emin /etc/passwd

- verilen bir karakteri verilen bir dizin altındaki dosyalarda ara ve içinde bulunduğu dosya isimlerini listeler

        $ grep -l 'printf' /code/*.c


- kelime içinde bulunan söz dizisini aramak yerine, kelimenin kendisinini bulmak isteyebiliriz. örneğin “can” ismini bulunduran satırları aramak istediğimizde, “erzincan” kelimesinin de içinde bulunduğu satırlar da listelenecektir. bunun önüne geçmek için -w -w (–word-regexp) parametresi kullanılır

        $ grep -w can /etc/passwd

- emin ile başlayan satırları listeler

        $ grep ^emin /etc/passwd

- emin ile biten satırları listeler

        $ grep emin$ /etc/passwd

- eğer bir dosya içerisinde farklı farklı özelliklere sahip satırların listelenmesini istiyorsak | (pipe) kullanılır

        $ grep \(emin\|can\|emre\) /ect/passwd

- bir diğer şekli ile 2006 ve 2008 yılları ile başlayan satırları listeler

        $ grep  ^200\(6\|8\) /etc/passwd

not: ‘\’ karakteri özel bir karakter (escape karakteri) olup, kendisinden sonra gelen karakterin özel olduğunu ve komuta dahil edilmesi gerektiğini bildirir. Yukarıdaki örnekte, ‘(‘, ‘|’ ve ‘)’ karakterlerinden önce gelip, bu karakterlerin aranacak metine dahil edilmeyip, komutun bir parçası olması gerektiğini ifade eder. Yukarıdaki örneği açacak olursak (emin veya can veya emre) şeklinde yorumlayabiliriz. Parantezleri sadece gruplamak için kullanıyoruz ve cümle içinde aramıyoruz. Yani “(emin” dizgisini değil, “emin” dizgisini arıyoruz.


**program çıktılarına yönlendirme**

- üstteki örneğin bir başka kullanılış şekli; ls -l ile listelenen dosyalardan rwxrvx özellikli olanları listeler

        $ ls -l | grep rwxrwx


grep komutunun kullanımı bu şekilde

