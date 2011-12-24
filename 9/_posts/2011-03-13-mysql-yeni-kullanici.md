---
layout: post
title: mysql üzerinde yeni bir kullanıcı oluşturma-silme
---

mysql veritabanını bağlanabilmek ve onu kullanabilmek için bir kullanıcı hesabı oluşturulmalıdır. mysql kullanıcı hesabı oluşturmak için kullanılan komut GRANT’tır. Bu komut ile kullanıcı hesabı oluştururken sunucunun üzerinde çalıştığı host ismide belirtilebilir. Eğer bu tür bağlantı parametreleri belirtilmezse mysql varsayılan değerleri alacaktır. Örneğin, eğer host adı belirtilmezse mysql sunucunun yerel host üzerinde çalıştığını varsayacaktır

mysql üzerinde yeni bir kullanıcı oluşturmak için önce root yetkisi ile giriş yapmalıyız

    $ mysql -u root -p
    Enter password:

şifremizi giriyoruz ve mysql promtunu görüyoruz

    mysql>

promtu gördükten sonra artık mysql üzerinde işlem yapabiliriz

- root haklarına sahip yeni bir kullanıcı oluşturmak

        mysql> create user 'kullanici'@'%' identified by 'parola';
        mysql> grant all  on *.* to 'kullanici'@'%';
        mysql> flush privileges;

bu komutlarla birlikte tamamen root haklarına sahip yeni bir kullanıcı oluşturduk bu yeni kullanıcı sisteme heryerden bağlanabilecek ve tüm yetkilere sahip olacaktır

- belirli bir IP’den tüm yetkilerle erişim sağlayabilecek bir bullanıcı oluşturmak

        mysql> create user 'kullanici'@'192.168.12.12' identified by 'parola';
        mysql> grant all on *.* to 'kullanici'@'192.168.12.12';
        mysql> flush privileges;

- belirli bir IP’den kısıtlı yetkilerle erişim sağlayabilecek bir kullanıcı oluşturmak

        mysql> create user 'kullanici'@'192.168.12.12' identified by 'parola';
        mysql> grant select,insert,update,delete on *.* to 'kullanici'@'192.168.12.12';
        mysql> flush privileges;

bu komutlarla mysql üzerinde belirli bir ip üzerinden bağlanarak sadece select, insert, update ve delete yetkilerine sahip yeni bir kullanıcı hesabı açılmış olur

- belirli bir IP’den, kısıtlı yetkilerle ve sadece tek DB’ye erişebilecek yeni bir kullanıcı oluşturmak

        mysql> create database yeni_DB;
        mysql> create user 'kullanici'@'192.168.12.12' identified by 'parola';
        mysql> grant select,insert,update,delete on yeni_DB.* to 'kullanici'@'192.168.12.12';
        mysql> flush privileges;

bir önceki hesap açma işlemleri ile yeni kullanıcıya tüm DB’lere erişim hakkı vermiş olduk. eğer bu yeni kullanıcının sadece tek bir DB’ye erişebilmesini istiyorsak hesabı bu şekilde açmalıyız

        mysql> grant select,insert,update,delete on yeni_DB.* to 'kullanici'@'192.168.12.12';

satırı ile yeni_DB üzerinde sadece select, insert, update ve delete işlemleri için izin verdik bu işlemleri isteğinize bağlı olarak kullanici hesabına verip vermemek sizin elinizde

        mysql> create database yeni_DB;
        mysql> grant all privileges on yeni_DB.* to 'kullanici'@'localhost' identified by "parola";

şeklinde verecek tanımlayacak olursak oluşturulan yeni kullanıcı yeni_DB üzerinde tüm işlemleri gerçekleştirebilir
NOT: bu kısımda kullanıcı hesabı oluşturma ve veritabanıyla ilişkilendirme işlemi aynı anda gerçekleştirilir.
 
mysql üzerinde yeni bir kullanıcı hesabı açma işlemleri bu şekilde şimdi de silme işlemine bakalım

        mysql> drop user kullanici;

komutunu vererek daha öncesinde oluşturduğumuz kullanici hesabını silmiş oluyoruz

NOT: kullanici değişkeni yerine oluşturulacak yeni mysql kullanıcı adı, parola yerine ise oluşturulacak bu hesabın parolası yazılır

