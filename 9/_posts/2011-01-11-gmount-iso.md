---
layout: post
title: iso dosyalarını sisteme mount etmek
---

elimizde bir image dosyamız var ve bu dosyanın içeriğine erişmek istiyoruz 
program kullanmadan image dosyalarının sisteme bağlamak için sırasıyla şu işlemleri yapabiliriz

öncelikle /mnt dizini altında bir dizin oluşturalım

        $ sudo mkdir /mnt/ubuntu

ardından iso dosyamızı buraya bağlayalım (mount)

        $ mount -t iso9660 -o loop ubunut-10.10-desktop-i386.iso /mnt/ubuntu

böylelikle iso dosyamızı /mnt/ubuntu dizinine bağlamış olduk

eğer elinizde nero programının oluşturduğu NRG uzantılı image dosyası varsa bunları siteme bağlamak için
daha önce iso dosyaları için yaptığımız gibi /mnt dizini altına bir dizin açıyoruz ardından

        $ mount -o loop offset=307200 image.nrg /mnt/image

komutu ile nero image dosyalarını siteme bağlamış oluyoruz


**Gmount programı ile iso dosyalarını sisteme bağlamak**

cd'lerimizi program kullanarak sanal sürücü gibi çalıştırmak isteyebiliriz bunun için gmountiso paketini yükleyelim

        $ sudo apt-get install gmountiso

programın kullanımı oldukça basit.
resimde görüldüğü gibi Image File (.ISO) kısmına image dosyamızın yolunu giriyoruz
Mount point kısmına ise nereye hangi isimle mount edilmesi gerektiğini yazıyoruz
ve Mount butonuna bastıktan sonra işlem tamamdır.
mnt dizininiz altında image dosyanız bir sürücü gibi yerleşmiş oldu.

![Gmount iso](/images/gmount-iso.png)

resimde göründüğü gibi Mounted Image bölümünde daha önce bağladığımız image dosyalarını seçerek
Unmount butonu ile sistemden ayırabiliyoruz

**NOT**: bu program ile en iyi sonucu sadece iso dosyalarını siteminize bağlarken alırsınız
diğer image türlerini bir üstteki yöntem ile yapmanız önerilir 



