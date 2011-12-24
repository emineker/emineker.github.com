---
layout: post
title: mysql ile veritabanı taşıma işlemleri
---

veritabanı taşıma işlemi sırasında önce taşıyacağımız veritabanının sql
dosyasını oluşturduktan sonra bu sql dosyasını elle oluşturacağımız yeni
veritabanına taşıyacağız.

- veritabanını sql dosyalarına aktarma

	$ mysqldump -u root -p`parola` `foo` > bar.sql

bu şekilde veri tabanında foo isimli veri tabanını bar.sql dosyasına taşıdık

örnek olarak veritabanındaki wordpress isimli veri tabanını wordpress.sql
dosyasına taşıyalım

	$ mysqldump -u root -p wordpress > wordpress.sql

- sql dosyasını veritabanına yükleme

	$ mysql -u root -p`parola` `bar` < bar.sql

biraz önce oluşturduğumuz wordpress.sql dosyasını yeni veritabanına yükleyelim

	$ mysql -u root -p bar < wordpress.sql

bu şekilde de wordpress.sql dosyasını bar veritabanına yükledik

NOT: sql dosyasını yeni (bar) veri tabanına yüklemeden önce
yüklenecek veritabanı (bar) oluşturulmalıdır.

