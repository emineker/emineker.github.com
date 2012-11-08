---
layout: post
title: github kullanıcı ismi kontrolünü terminalden yapın
---

githubdan hesap alacak arkadaşlar veya yeni isimle hesap alacak arkadaşlar ya da kullanıcı isimleriyle ilgili işlemler yapmak isteyen arkadaşlar size githubdan selam getirdim

github diyor ki :

        yeni bir kullanıcı hesabı mı alacaksın?
        o zaman bu hesap daha önce alınmış mı alınmamış mı diye sayfa aramana gerek yok
        gel sana bir satır kod vereyim
        konsolundan yap bu işi

adam gelmiş sana kolaylık sağlamış sen kullanmayacak mısın?

ben kullanıyorum vallahi ve konsola sadece şu satırı yazıyorum

        $ curl -s http://github.com/api/v2/yaml/user/show/emineker

bakın bu satırı yazdım ve bana ne çıktısını verdi

        user: 
          gravatar_id: 61350fe7190927121a48cd3385a76c95
          created_at: 2010-07-08 03:00:02 -07:00
          public_repo_count: 0
          public_gist_count: 0
          following_count: 0
          id: 326255
          type: User
          followers_count: 0
          login: emin

bir de şöyle bir kullanıcı adı var mı yok mu ona bakalım

        $ curl -s http://github.com/api/v2/yaml/user/show/abdurrezzak

çıktısı ise bu oldu

        --- 
        error: User not found

meğer abdurrezzak diye bir github kullanıcısı yokmuş

bu kayıtları görebilmek için github kullanıcısı olmanız şart ve o bilgisayarda github'a adapte edilmiş olmalı. github bu kayıtları sorgulamanız için size bir hak vermiş ama bir de ufak sınır koymuş tabi. arka arkaya 60 kullanıcı hesabı sorgulama izni veriyor belirli bir süre sonra tekrar arama yapabiliyorsunuz.

kolay gelsin...


