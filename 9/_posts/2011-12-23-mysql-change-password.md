---
layout: post
title: mysql kullanıcı parolası değiştirme
---


- mysql kullanıcı parolası değiştirmek için

        $ mysqladmin -u root -p password new_password

- diğer yol

    	$ mysqladmin -u root -p'eskiparola' password new_password

ancak bu şekilde parolaları sistem geçmişine düşecek şekilde vermemelisiniz

