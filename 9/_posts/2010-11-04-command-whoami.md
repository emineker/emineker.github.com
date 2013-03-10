---
layout: post
title: who ile sistemde oturum açan kullanıcıları öğrenin
---

who daha çok client sistemlerde hangi kullanıcı en son ne zaman oturum açmış veya o an hangi kullanıcılar aktif gibi bilgileri görmek için kullanılan küçük bir bash betiğidir.

bu işlemleri kendi bilgisayarınızdan da yapabilirsiniz.

- sistemin en son açılış zamanını öğrenin

        $ who -b

- sistemde o anda bulunan kullanıcıları görün

        $ who -u

- sistemde çalışan process-leri görün

        $ who -l

- sistemde zaman zaman öldürülen işlemlerin listesi(kill process)

        $ who -d

- standart girdideki kullanıcı ve makina ismini verir

        $ who -m

- kullanıcılar tarafından çalıştırılmış ve halen aktif olan işlemleri (programları) gösterir

        $ who -p

- sistemde çalışan tüm kullanıcı isimlerini ve sayısını gösterir

        $ who -q

- sistemin o anki açılış seviyesini gösterir

        $ who -r

- yalnız isim, makina ve zamanı gösterir (öntanımlıdır yani sadece who ile de aynı sonuca erişebilirsiniz)

        $ who -s

- sistemin saat değişikliği zamanını verir

        $ who -t

- yukarıdaki tüm bilgileri aynı anda görmek istiyorsanız (-b -d -l -p -r -t -u)

        $ who -a


