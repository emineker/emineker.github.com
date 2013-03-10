---
layout: post
title: sunucuya ssh ile şifresiz otomatik giriş yapma
---

### ssh-keygen ile özel anahtar oluşturma

öncelikle

        $ ssh-keygen

komutu ile `ssh` anahtarımızı oluşturalım eğer daha önceki herhangi bir işlem
için ssh anahtarımızı oluşturmuş isek bu işlemi tekrar yapmayalım ki diğer
işlemlerimiz (örn: git) aksamasın

### ssh-copy-id ile ssh anahtarını sunucu ile bağdaştırma

arkasından `ssh-copy-id` komutu ile ssh anahtarımızı sunucuya gönderelim

örneğin sunucunun ip adresi `19.19.19.19` olsun sunucudaki kullanıcı adımız da `emineker`

        $ ssh-copy-id emineker@19.19.19.19

şeklinde sunucuya ssh anahtarımızı gönderip onay alabiliriz eğer yereldeki
kullanıcı adı ve sunucudaki kullanıcı adımız aynı ise direkt olarak

        $ ssh-copy-id 19.19.19.19

şeklinde de ssh anahtarını onaylatabiliriz. diğer bir durum ise ip adresi yerine
domain ismi yazabilme eğer ki ip adresimizin bağlı domain `test.com` ise

        $ ssh-copy-id emineker@test.com

veya

        $ ssh-copy-id test.com

diyerek de bu işlemimizi gerçekleştirebiliriz

bu komutları verdikten sonra bizden sunucu parolamız istenecektir. parolamızı da
girdikten sonra herhangi bir sorun ile karşılaşmamıssak artık ssh anahtarımızı göndermiş ve
onay almış durumdayız.

bundan sonra sunucuya direk olarak

        $ ssh emineker@19.19.19.19

veya

        $ ssh 19.19.19.19

veya

        $ ssh emineker@test.com

veya

        $ ssh test.com

şeklinde bağlanabiliriz

### sunucu isimlerini istediğimiz şekilde atama

eğer ki ip adresini aklımızda tutmakta zorlanıyor veya uzun bir domain adresimiz varsa
bunlara kısa isimler atayarak bu problemi çözebiliriz

        $ vim ~/.ssh/config

dosyası içerisine şu komutları girelim (dosya yok ise oluşturalım)

        Host foo
            HostName test.com
            ForwardAgent yes

artık 19.19.19.19 ip adresli makinaya

        $ ssh foo

komutunu vererek direk erişebilir duruma geldik eğer daha fazla sunucuya bu
şekilde erişmek istiyorsak yine aynı dosyayı şu şekilde düzenleyebiliriz

        Host foo
            HostName test.com
            ForwardAgent yes

        Host bar
            HostName best.test.com
            ForwardAgent yes


NOT: bu işlemleri barındırdığımız makinanızın başkalarının ellerine geçmemesine özen gösteriniz.


