---
layout: post
title: mysql kullanıcı parolası değiştirme
---


- mysql kullanıcı parolası değiştirmek için

    	$ mysqladmin -u root -p'eskiparola' password yeniparola

- diğer bir yolu ise

    	$ mysqladmin -u root -p password yeniparola

her iki durumda da bu değişikliği yapmanız için sizden eski parolanızı girmeniz isteniyor

