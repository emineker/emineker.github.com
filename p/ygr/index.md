# Yazılım Gereksinim Dökümanı

.fx: first

Kan Bağışı Merkezi Veritabanı ve Web Portalı


Nisan 2012

Emin Eker `<emineker@bil.omu.edu.tr>`

Dilara Koca `<dilara@bil.omu.edu.tr>`

---


# İçindekiler

- Giriş

    - Sistemin Amacı
    - Sistemin Kapsamı
    - Tanımlar, Kısa Adlar ve Kısaltmalar
    - Kullanılacak Teknolojiler
    - Genel Bilgiler

- Genel Açıklama
    - Kullanım Senaryosu Modeli
    - Mimari Şema ve Veritabanı Tasarımı
    - Kullanım Senaryosu Raporları
    - Ek Gereksinimler
    - İşlevsel İhtiyaçlar
    - Kullanıcı arabirimi Özellikleri

---


# Sistemin Amacı

- Kan bankalarının ve hastanelerin yakın çevrede olan ve kısa zamanda kan bağışı yapabilecek kişileri bulabilecekleri çevrimiçi, merkezileştirilmiş bir web portalı oluşturulması.
- Hızla değerlendirmek üzere kan bağışı yapan kişilerin sağlık raporlarının kaydını tutulması.

- Kan bağışı merkezi veritabanı ve web portalı kan bağışçılarının gönüllülükleri ile doğru orantılı olarak kan bağışlarının kayıt altına alınması ve ihtiyaçlar doğrultusunda (acil durumlarda) sisteme daha önceden kayıt yaptırmış ve onay olmış kurumlar tarafından email veya telefon aracılığı ile kendilerine anında ulaşılmasının sağlanmasıdır.

---


# Sistemin Kapsamı

- Öncelikler belirli bir bölgeyi kapsayacak bu proje daha sonra tüm ülkeye yayılıp merkezi bir sistem olarak gerekli kurum ve kuruluşlara hizmet sağlayacaktır.

---


# Tanımlar, Kısa Adlar ve Kısaltmalar

- **Donör:** Gönüllü kağ bağışçısı

- **Kurum:** Sürekli veya acil kan ihtiyacı olan devlet kurumu veya özel kuruluşlar (hastaneler, klinikler vb.)

- **Admin:** Sistem yöneticisi

---


# Kullanılacak Teknolojiler

- Proje MySQL veritabanı ve Ruby programlama dili kullanılarak Ruby on Rails web çatısı üzerinde Linux işletim sistemi Debian dağıtımı üzerinde geliştirilecektir. Projede ayrıca Java Script kodları da yer yer kullanılacaktır.
- Web sunucusu olarak ise Nginx, production bir Rails sistemi çalıştırabilmek için de Unicorn Rails sunucusu kullanılacaktır.
- Proje geliştiricileri ayrı (benzer) ortamlarda çalışacaklardır. Tüm geliştiriciler:

    - ruby >= 1.9.2
    - rails >= 3.1.0
    - Nginx 1.1.17
    - MySQL 5.1.61
    - unicorn v4.2.0
    - imagemacik görüntü işleme paketi

açık kaynak paketler kullanılacaktır.

Proje geliştirilme esnasında Chromium browser 19.01.1077 üzerinde çalışılmalı ve tüm tarayıcılarda test edilmelidir.

---


# Genel Bilgiler

- Kan bankalarının ve hastanelerin yakın çevrede olan ve kısa zamanda kan bağışı yapabilecek kişileri bulabilecekleri çevrimiçi, merkezileştirilmiş bir web portalı oluşturulacak.

- Ayrıca, hızla değerlendirmek üzere kan bağışı yapan kişilerin sağlık raporlarının kaydını tutacaktır.

- Kan bağışı merkezi veritabanı ve web portalı kan bağışçılarının gönüllülükleri ile doğru orantılı olarak kan bağışlarının kayıt altına alınması ve ihtiyaçlar doğrultusunda (acil durumlarda) sisteme daha önceden kayıt yaptırmış ve onay olmış kurumlar tarafından email veya telefon aracılığı ile kendilerine anında ulaşılmasını sağlayacaktır.

Projenin temel özellikleri aşağıda verilmiştir:

- Sistemde dört çeşit kullanıcı olacaktır.
- Bunlar; donör, misafir, kurum ve yönetici kullanıcılarıdır.
- Bütün kullanıcılar sisteme kullanıcı adı ve sifresi ile giriş yapabilecektir.

---


# Sistemin Kulanıcıları:

- Sistem yöneticisi (bu, merkezi kan bankası kurumundan bir kişi ya da genel bir birim olabilir)
- Kan Bankaları, Hastaneler, Klinikler, vb.
- Kan Bağışçıları
- Üye Olmayan Kişiler

---


# Kullanım Senaryosu Modeli

- Donör, sisteme tamamen kendi isteğiyle kayıt olabilir ve sistem üzerinde bir parolaya sahip olur.
- Aynı zamanda sistem kullanıcı adı olacak email adresi ve parolasıyla sisteme giriş yapar.
- Sistemde içerisinde kayıt olurken verdiği bilgileri düzenleyebilir, parolasını değiştirebilir.
- Donör ve kurumlar açısından önemli olan bir diğer faktör kullanıcının sağlık bilgileri ve kan verme tarihleridir. Donör yine bu bilgileri de güncelleyebilmektedir.

---


# Mimari Şema ve Veritabanı Tasarımı

Ekte (Raporda) Sunulmuştur


---


# Kullanım Senaryosu Raporları

Ekte (Yazlım Raporunda Kullanım Klavuzu Bölümünde) Sunulmuştur

---


# İşlevsel İhtiyaçlar 1:

- Sistem yöneticisinin kan bağışçılarına ilişkin tüm ayrıntılara erişimi olmalıdır
- Kan bağışçısı için kişisel bilgiler doldurulurken, yalnızca Ad, Bölge, iletişim ayrıntıları (telefon numarası ya da e-posta adresi olabilir) ve kan grubu alanlarının doldurulması zorunlu olmalıdır . Diğer ayrıntıları isteyen alanların doldurulması zorunlu kılınmamalıdır. Kan bağışçılarıyla ilgili ayrıntılar, xml gibi daha az boş alan olacak şekilde kaydedilmelidir.
- Kan bankaları, hastaneler ve benzeri kurumlar, yakın çevrede kan veren kişileri arayabilir; ancak arama sonuçları yalnızca son 3 ay içinde kan vermemiş olan kişileri göstermelidir
- Kan bağışı yapıldıktan sonra gelecekte de aynı kişiye başvurabilmek için kan veren kişilerden, sağlık durumlarıyla ilgili geribildirim sağlamaları istenmelidir.
- Web sitesine üye olmayan kullanıcılar, kan bağışçılarıyla ilgili hiçbir ayrıntıya erişemezler.

---


# İşlevsel İhtiyaçlar 2:

- Yalnızca hastaneler, kan bankaları ve benzeri kurumlar kan bağışçılarının iletişim bilgilerini (telefon numarası / e-posta adresi gibi) görebilmelidir
- Kan bağışçısı, yalnızca adı ve yaşadıkları bölgeyi görebilmelidir. Herhangi bir kan bağışı yardımı için başka bir kan bağışçısı aramaları gerektiğinde, bunun için yöneticinin yardımı ve kan bağışçısının dolduracağı bir formla birlikte geçerli bir neden gereklidir.
- Her kan bağışına dayalı olarak, kan veren kişilerin akrabaları, arkadaşları ve diğer yakınları için kan gerekmesi durumunda kan bağışçıları tarafından kullanılabilecek bir puan verilir. (Verilen puan, bu kan bağışçıları için üye kan bankaları tarafından kan bulunmasında belirli bir öncelik sağlar)
- Üye olmayanlar da herhangi bir kan bankasında kan ya da kan bağışçısı arayabilir ve ardından cep telefonları aracılığıyla hızlıca kayıt yaptırabilir ve kan gereksinimlerine ilişkin talep oluşturabilirler.

---


# İşlevsel Olmayan İhtiyaçlar:

- Bu uygulamayı bir pazarlama stratejisi olarak kullanarak, Facebook gibi sosyal ağlarla bağlantılandırmaya çalışın.
- Sistem, her üç aydan sonra aynı kan bağışçısını seçmek yerine, her defasında farklı bir kişiyi seçebilecek kadar akıllı olmalıdır

---


# İsteğe Bağlı Özellikler:

- Sistem, her üç aylık dönem sonunda aynı kan bağışçısını seçmek yerine, her defasında farklı bir kişiyi seçebilecek kadar akıllı olmalıdır
- Ayrıca, kan bağışçılarını bilgilendirmek için kan bağışı kampanyaları düzenleyen Rotary klubü gibi kurumların katılımını sağlayın

---


# Kullanıcı Arabirimi Öncelikleri:

- Profesyonel görünüm ve yapı
- Tüm kayıtlarda düşük gereksinimli formlar kullanılması
- Tarayıcı testi ve IE, NN, Mozila ve FireFox desteği.
- Sistem yöneticisineverilerin tablolar halinde sunulması
- Raporların .PDF veya diğer herhangi bir biçimde dışarı aktarılması


