# Vim

.fx: first

Emin Eker `<emineker@bil.omu.edu.tr>`

[http://emineker.net/](http://emineker.net/)

Eylül 2011

![vim](media/vim-logo.png)

---


# Linux Sistem Yönetimi & Text Editörler

- Her ne kadar linux sunucularda sistemin ve servislerin yönetimi için çeşitli yönetim arayüzleri geliştirilse de bu grafik arayüzlerin hem sayısı az hemde yetenekleri kısıtlıdır
- Aynı zamanda aktif servis veren bir sunucu üzerinde sürekli masaüstü ortamı çalışması da sistem kaynaklarının bir bölümü tükettiğinden, bunlar sadece gerektiğinde kullanılırlar
- Bu nedenle linux sistem yöneticileri çoğunlukla bu ihtiyaçlarını sistem ve servislere ilişkin yapılandırma dosyalarını düzenleme/değiştirme yoluna giderek karşılarlar

Linux sistem yöneticiliğinde, text editörlerine işte bu noktada oldukça ihtiyaç duyulur.

---


# Text Editörlerinin Padişahı: Vim

- Vim, Bill Joy tarafından tasarlanan yaşı 30 yılı aşmış bir editör olan vi editörünü temel alan çok güçlü bir metin editörüdür. Zaman içerisinde Vi extra özelliklerle güçlendirilmiş ve bugünkü halini almıştır.


## Vi ile Vim Editörlerinin Farkları Nelerdir?

- Vim editörü vi editörünün geliştirilmiş halidir.

- Vi ile Vim arasındaki farklar sistemdeki /usr/share/vim/vim73/doc/vi_diff.txt dosyasında mevcuttur

        !sh
        $ cat /usr/share/vim/vim63/doc/vi_diff.txt
komutu ile dosya içeriğini görebilirsiniz

---


# Neden Vim?

- Özellikle linux dağıtımlarında çok fazla metin editörü ve bunların kendilerine has özellikleri var.
- Bu editörler birbiri ile kıyaslandığında Vim çok gelişmiş bir metin editörüdür.
- Çünkü birçok işlemi text pencerenizi kapatmadan aynı anda yapmanızı sağlar.
- Sistem yöneticilerin ve programcıların işlerini oldukça kolaylaştırır.

Unix geleneklerine sahip olan Vim özellikle linux sistem yöneticileri ve programcılar tarafından oldukça yaygın kullanılan bir editördür.
Unix tabanlı hemen hemen her sistemde bulunur.

---


# Vim’in Temel Özellikleri

Vim editörünün temel özellikleri

- çoklu seviyede UNDO mekanizması
- çoklu pencere
- tampon bellek kullanımı
- sentaks renklendirme
- komut modunda dosya ismi tamamlaması

Vim’in bu gibi temel özellikleri ile kendisini diğer editörlerden oldukça ayrı bir noktada tutmaktadır.

---


# Örnek Bir Çalışma Anı

- otomatik indent

![vim](media/autoindent.gif)

- split

![vim](media/split.gif)

---


# Ayrıntı!

.fx: dikkat

- Vim alışması ve öğrenmesi gerçekten çok sancılı bir metin editörüdür ama alıştıktan sonra, yani içten gelen içgüdü gibi bir hal aldığında (buna `second nature` deniyor, yani ellerinizin siz düşünmeden yaptığı işe odaklanması ve üzerine düşeni yapması) çalışmayı hızlandırıyor.

- Genellikle klavyeyi onparmak kullanan insanların bu editöre alışması biraz daha kolaydır. Bir bilgisayarcı için onparmak herşey demektir.

- Slaytlarda göreceğiniz, asıl üzerinde durulan konu da budur. Klavyenizde sadece belirli bir görevi olan belirli tuşlar vardır `delete ve yön tuşları` gibi. Fakat göreceksiniz ki Vim üzerinde bu tuşların görevleri karakter tuşlarıyla da gerçekleştirilebilmektedir. Bunun nedeni elleri klavyenin üzerinden ayırmamak ve sürekliği sağlamaktır.

- Daha önce Vim unix geleneğine sahip bir text editörü demiştik. Ancak bunu söylemiş olmamız sadece linux işletim sitemlerinde çalıştığı anlamına gelmiyor. Vim tarşınabilir bir programdır. Bu yüzden neredeyse tüm işletim sistemleriyle uyumludur. Linux, FreeBSD, AmigaOS, Atari MINT, BeOS, DOS, MacOS, NextStep, OS/2, OSF, RiscOS, SGI, UNIX, VMS, WIn16 + Win32 + Win64 gibi

---


# Vim Metin Editörünü Edinin

- Daha önce de söylediğimiz gibi vim unix geleneklerine sahip bir metin editörüdür.
- Bu yüzden linux dağıtımlarından bu editöre ulaşmak oldukça kolaydır.

Terminale gidelim ve bu komutu girelim:

    !sh
    $ sudo apt-get install vim

Vim editörünü linux dağıtımımıza yüklemiş olduk

---


# Vim’e Nasıl Ulaşılır ?

- Öncelikle Vim’e erişmek için bilindiği gibi terminalden ismi ile çağırıp çalıştırabiliyoruz.

Konsoldan Vim’e

    !sh
    $ vim

ve

    !sh
    $ vi

şeklinde ulaşabiliyoruz

Vim’in Vi’in geliştirilmiş hali olduğunu söylemiştik.

Ama yanlış anlaşılmasın biraz önceki vi komutuyla vi metin editörünü çağırmadık.

vi burada bir alias görevinde. vi de bizi vim’e götürecek.

---


# Vim Kullanımına Giriş

Vim’in escape, insert ve command olmak üzere üç modu vardır.

- insert modu ile dosya üzerinde değişiklikler yapabiliriz.

    Dosya içerisindeyken i tuşuna basarak insert yani yazma moduna geçmiş oluruz

- escape modu ile kısayolları kullanabiliriz.

    Dosya içerisindeyken esc tuşuna basarak escape moduna geçmiş oluruz

- command modu ile de dosyadan çıkış yapmadan komut satırı işlemlerimizin bir kısmını gerçekleştirebiliriz.

    Dosya içerisindeyken önce esc arkasından : işaretiyle command moda yani komut moduna geçmiş oluruz.

---


# Vim ile Zorunlu Hareketler 1

## Dosya açmak

    !sh
    $ vim index.html

ile bulunduğumuz dizinde index.html adında bir dosya açtık.

Dosya adını belirtmeden yine terminalden

    !sh
    $ vim

ile programa giriş yapıp escape modunda

    !sh
    :w index.html

yazarak da dosyamızı index.html olarak kaydetmiş oluyoruz.

---


# Vim ile Zorunlu Hareketler 2

## Dosyadan çıkmak

Dosyadan çıkma işlemlerimizi aşağıda da gördüğümüz gibi daima command modda
yapacağız. Biraz önce vim ile açtığımız index.html dosyasında

- dosyaya çeşitli eklemeler yaptık ve her ihtimale karşı dosyadan çıkmadan sadece kaydetmek istiyoruz bunun için -> :w

- eğer dosya içerisine birşeyler eklediysek kaydedip çıkmak için -> :wq

- eğer dosya içerisinde değişiklik yapmadıysak olduğu gibi çıkmak istiyorsak -> :q

NOT: eğer değişiklik yaptıktan sonra bu komutu verirsek dosyada değişiklikler var mesajını alırız.

- dosya içerisinde yaptığımız değişiklikleri kaydetmeden çıkmak için (yani ilk haline dönmek için) -> :q!

---


# Yön Tuşlarını Kullanmak

İmleç tuşları yani klavyemizin yöntuşlarıyla dosya içerisinde ileri-geri  veya sağ-sol yaparak ilerleyebiliriz.
Ancak bu görevi yapan `hjkl` tuşlarını kullanmaya alışırsak editör içerisinde çok daha hızlı hareket edebiliriz.

         ^
	     k	           İpucu: h tuşu soldadır ve sola hareket eder.
    < h     l >	       l tuşu sağdadır ve sağa hareket eder.
         j	           j tuşu aşağı yönlü bir ok gibidir.
         v	           k tuşu yukarı yönlü bir ok gibidir.

tabi ki bu işlemlerin hepsi yine escape modda yapılabilir.

---


# Dosya İçerisinde Kopyala-Yapıştır

index.html dosyamız ve bu dosyamızda aşağıdaki gibi kodlarımız olsun:

    !html
    <div class="landslide">
        <header><h2>foo</h2></header>
        <section>
            <p>su gibi berrak ol evladım!</p>
        </section>
    </div>

Dosya içerisindeyken insert modu ile çeşitli eklemeler düzenlemeler yaptık.

Arkasından escape moduna geçerek

- kopyalamak istediğimiz satıra gelerek yy tuşuna
- kesmek istediğimiz satıra gelerek dd tuşuna

Kopyaladığımız veya kestiğimiz satırları yapıştırmak için ise yapıştırmak istediğimiz satıra gelelim

- eğer üzerinde bulunduğumuz satırın bir alt satırına yapıştırmak istiyorsak küçük p tuşuna
- üzerinde bulunduğumuz satırın bir üzerindeki satıra yapıştırmak için ise büyük P tuşuna basalım (shift + p)

---


# Visual Mod

Visual mod yani görsel mod sayesinde birden fazla satır üzerinde işlemler yapabiliyoruz.

    !python
    import landslide

    class MyMacro(Macro):
        def process(self, content, source=None):
            return content + '<p>hop</p>', ['hop_slide']

    g = generator.Generator(source='slide.md')
    g.register_macro(MyMacro)
    print g.render()

örneğin

- yukarıdaki satırda istediğimiz satırın istediğimiz yerine gelerek v tuşuna basalım
- arkasından yukarı-aşağı ve sağ-sol yön tuşlarıyla istediğimiz bölgeyi seçelim

artık sıra kopyalama veya kesme işleminde bunun için ne yapmamız gerektiğini biliyoruz

- yapıştırmak istediğimiz yere gelip

seçtiğimiz kısmı olduğu gibi yapıştırabiliriz.

---


# Visual-Block Mod

Visual-Block modun Visual moddan farkı blok seçim yapabilmesidir.

Hemen bir önceki sayfadaki kod üzerinde deneme yapalım.

- Kod üzerine gelip ctrl + v tuş kombinasyonuyla visual-block moduna geçelim
- Arkasından visual moddaki gibi seçim yapalım

        burda görmemiz gereken farklılık
        visual moddaki birden fazla satır
        block halinde seçebilme durumumuzdur

- Visual mod seçeceğimiz satırların tümünü seçmemizi sağlıyordu
- Visual-block mod ise bize istediğimiz bir grup satırın istediğimiz kısımlarını seçmemizi sağlar

---


# Dosya Üzerinde Silme ve Geri Alma

### Silme

- Escape modunda iken delete tuşu ile harf harf silebiliriz.
- Aynı şekilde yine karakter karakter silmek için x tuşu kullanılabilir be kullanılmalıdır.
- Visual veya Visual-Block modu ile toplu seçimlerimizde yine delete tuşu ile silebiliriz.
- dd tuşları ile de seçtiğimiz kısmı veya üzerinde bulunduğumuz satırı keserek de ordan kaldırmış oluruz.


### Geri alma

sadece silme işlemlerinde değil kopyalama, yapıştırma, kesme gibi bir çok işlemi geri almak istediğinizde

- Önce escape moduna geçip
- Arkasından command modda

        !sh
        :u
ile en son işleminizi geri alıp dosyanızı bir işlem önceki haline getirebilirsiniz.

---


# Devamı gelecek

daha yeni başladık


