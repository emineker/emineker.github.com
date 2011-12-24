---
layout: post
title: gnome3 ortamını kurmak
---

- Ubuntu üzerinde denenmiş ve kurulmuştur.
- Ne yaptığını Bilmiyorsanız denememeniz tavsiye edilir
- Sabır gerektirir

Öncelikle Gnome3 deposunu sistemimize ekleyelim

    sudo add-apt-repository ppa:gnome3-team/gnome3

sonra paket listelerini güncelleyelim

    sudo apt-get update

en son olarak da sistemimizi yükseltelim

    sudo apt-get dist-upgrade

işlemimiz sonuçlandıktan sonra sistemimizi yeniden başlatmalıyız
ubuntu yeniden açıldığında oturum penceresinde Masaüstü ayarını
“Ubuntu Gnome Shell” olarak seçiyoruz.

eğer sisteminiz 10.04 gibi daha önceki ubuntu sürümleri ise

    gnome-shell --replace

komutunu vererek gnome3 ortamna geçebilirler

NOT: bu işlemleri yaparken sisteminizin güncel ve sorunsuz olmasına özen gösteriniz

![gnome3](http://www.gnome.org/wp-content/uploads/2011/09/overview-420x336.png)
![gnome3](http://www.gnome.org/wp-content/uploads/2011/09/app_list-420x263.png)
![gnome3](http://www.gnome.org/wp-content/uploads/2011/09/cc-all-420x269.png)


