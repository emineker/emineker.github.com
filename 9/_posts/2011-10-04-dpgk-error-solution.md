---
layout: post
title: /usr/bin/dpkg returned an error code (1) hatası ve çözümü
---

Eğer ki paket kurulumlarında veya daha çok upgrade'lerde bu hatayla
karşılaşıyorsanız yapmanız gerekenler

### 1. adım

öncelikle şu komutu deneyin

	$ sudo dpkg --remove <paket adı>

`paket adı` kısmına sorunlu paket ismini yazıp kaldırmayı deneyin.
bu şekilde büyük ihtimalle sorununuz çözülmüş olur. ancak yine çözülmediyse
2 adıma geçin

### 2. adım

grub paketini `özenli` bir şekilde tasfiye edelim

    	$ aptitude purge grub

arkasından grub-pc grup-common paketleirni tasviye edelim

    	$ aptitude purge grub-common

ve gerekli olan grub-pc paketini yeniden kuralım

    	$ aptitude install grub-pc

şimdi paket kurabiliyor yükseltme yapabiliyor olmanız gerekli

NOT: kaldırılacak paketlere dikkat edin önleminizi almayı unutmayın

