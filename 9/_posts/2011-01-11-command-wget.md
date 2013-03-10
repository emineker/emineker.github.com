---
layout: post
title: wget komutu ile konsoldan dosya indirme
---

**wget nedir?**

wget => web get kelime grubunun kısaltmasıdır

wget, linux altidaki internetten dosya veya dizin indirmek icin kullanilan cok pratik bir arac. bircok parametre sayesinde hertürlü indirme yöntemini uygulamak mümkün. şimdi bunları örnekler ile görmeye çalışalım


**wget ile dosya indirime**

- normal olarak dosya indirme

        $ wget http://ondokuz.biz/chrome/biz/biz-normal-128x128.png

sadece wget komutunu kullanarak internetten adresini bildiğimiz bir dosyayı bu şekilde bilgisayarımıza indirebiliriz

- herhangi bir dosyayı indirmeyi yarım bırakıp, daha sonra devamını indirebiliriz. kaldığı yerden devam etme özelliğini kullanmak için:

        $ wget -c ftp://ftp.linux.org.tr/ubuntu-releases//maverick/ubuntu-10.10-desktop-i386.iso

bunun için wget komutuna eklemeniz gereken parametre `-c` yani continue parameterisidir. bu indirmeyi yarıda kesseniz bile daha sonra yine aynı seçenek ile aynı komutu verdiğiniz taktirde indirme yarım kaldığı yerden devam eder


- site üzerinden komple dizini indirmek:

internetteki bir siteyi veya bir dizini komple olarak indirmek istediğinizde `--recursive` anlamına gelen `-r` parametresini kullanabilisiniz.

        $ wget -r http://emineker.net/

url olarak verdiğiniz yer bir dizin olmak zorunda. download olurken domain ve alt dizin yapısı aynen iner.
bu sayede -r parametresi ile http://emineker.net/ sitesi bilgisayarıma emineker.net dizini şeklinde inmiş olur.

eğer indirmek istediğiniz internet adresinin domain ön takısını almak istemiyorsanız -nH eklemelisiniz. yani:

        $ wget -r -nH http://emineker.net/

komutunu verdiğimiz taktirde site içindeki tüm dosyalar emineker.net dizinine değil bulunduğunuz dizine inmeye başlayacaktır.

eğer sadece sitede istediğiniz bir dizinin inmesini istiyorsanız `--mirror` anlamına gelen `-m` paremetresi ile `--no-parent` anlamına gelen `-np` paremetresini kullanabiliriz:

        $ wget -m -np http://emineker.net/

şimdi sitede bulunan belirli özellikteki dosyaları indirelim bunun için `--accept` anlamına gelen `-A` paremetresini kullanabiliriz.
mesela sitede jpg ve png formatındaki dosyaları indirmek için şu komutu vermemiz yeterli

        $ wget -r -A jpg,png http://emineker.net/

bu sayede verilen url adresinde ve alt dizinlerinde sadece jpg ve png dosyaları indirilir.

şimdi de tam tersini yapalım. uyguladığımız filtre haricindeki dosyaların tümünü indirmeyi nasıl yapabiliriz?
bunun için `--reject` anlamına gelen `-R` paremetresini kullanabiliriz.

        $ wget -r -R tar.gz,jpg http://emineker.net/

bu sayade sitede tar.gz ve jpg haricindeki tüm dosyaları indirebiliriz.


- download hızını sınırlandırmak

internet hızınız hızlı değil ve bunu download için harcamak istemiyorsanız `--limit-rate=INT` şeklinde sınırlandırabilirsiniz.

        $ wget -c --limit-rate=25k http://ondokuz.biz/chrome/biz/biz-normal-128x128.png

bu şekilde dosya sadece 25k ile indirilir.


- bir dosya içerisindeki url adreslerinden download etmek

her komut için tekrar tekrar wget komutunu vermek istemiyorsunuz en güzel çözüm bütün dosyaların adreslerini bir text dosyası haline getirip
`--input-file` anlamına gelen `-i` parametresini kullanmaktır. veya bu sefer de kısaltma değil direk komutu kullanalım:

        $ wget -c --input-file=~/download.txt

dosya içinde belirtilen adresler indirilir.


- indirilen dosyayı yönlendirme

internetten çektiğimiz dosyayı bulunduğumuz dizine değil de bir başka dizine indirmek istersek:

        $ wget -c http://ondokuz.biz/chrome/biz/biz-normal-128x128.png -P ~/dosyalar

bu komut ile indirme işlemi bulunduğunuz dizine değil `-P` ile belirttiğimiz dizinde yapılır.
eğer belirtilen dizin yoksa otomatik oluşturulur.


- güncel dosyaları indirme 

belirli bir adresden devamlı indirme yapıyorsunuz. ve adres de kendini devamlı güncelliyor ise
 tüm dosyaları teker teker bir daha indirmenize gerek yok. bunun için `--timestamping` anlamına gelen `-N` paremetresini kullanabiliriz.

eski bir tarihte aşağıdaki komutu verdiğiniz varsayalım

        $ wget -r -nH http://emineker.net/

şimdi de bu adreste yeni dosyalar var mı yok mu diye kontrol edip eğer varsa indirmek istiyoruz. 
bunun için aşağıdaki komutu vermemiz yeterli

        $ wget -r -nH -N http://emineker.net/

- ftp adreslerinden dosya çekmek

bazen ftp adreslerinden konsoldan dosya çekemessiniz. ama bu dosyaları tarayıcınızda rahatlıkla indirebilirsiniz.
bu sorunu çözmek için `--passive-ftp` paremetresini eklememiz gerekir.

        $ wget -c --passive-ftp ftp://ftp.linux.org.tr/ubuntu-releases//maverick/ubuntu-10.10-desktop-i386.iso

- wget komutu ile log dosyası oluşturmak

wget ile indirme esnasında konsol ekranında bir sürü bilgilendirme mesajı adresler durum diyagramları çıkar.
bunlar anlıktır ve daha sonra ulaşılabilecek veriler değildir.
bunun için verilerin ekranda görünmesi yerine bunları bir dosyaya yönlendirebiliriz.
`--output-file` anlamına gelen `-o` paremetresini kullanarak bu işi şu şekilde halledelim.

        $ wget -r -nH http://emineker.net/ -o log_wget

bu komuttan sonra bir log_wget isminde dosya oluşur ve veriler bu dosya içerisine yazılır


**NOT:** daha fazla bilgi için `/etc/wgetrc` dosyasına bakılabilir

