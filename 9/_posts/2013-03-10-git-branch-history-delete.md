---
layout: post
title: git dal geçmişi temizle
---

Çalıştığınız bir dalın geçmişini temizlemek istediğinizde aşağıdaki
adımları takip edebilirsiniz

        örnek dal adı: foo
        yedek dal adı: bar


- dalı yedekle

        $ git checkout -t -b foo origin/foo
        $ git branch -M foo bar


- uzaktaki dalı sil

        $ git push origin :foo


- ebeveyni olmayan yeni bir dal oluştur

        $ git symbolic-ref HEAD refs/heads/foo
        $ rm -f .git/index
        $ git clean -fdx

**Dikkat:** son satırdaki komut depodaki git tarafından takip edilmeyen tüm dosyaları siler


- yeni dalı ilkle

        $ touch README.md
        $ git add .


- ebeveynsiz dalı gerçekten oluştur

        $ git commit -a -m first


- eski `foo` dalını tek bir bütün halinde bulunduğumuz yeni dala merge et

        $ git merge --squash bar


- yedek dalı sil

        $ git branch -D bar


- yeni dalı gönder

        $ git commit -a -m "create branch"
        $ git push origin foo

