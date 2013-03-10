---
layout: post
title: git depo taşıma
---

- hesap bilgileri

    	hesap adı: foo
    	taşınacak depo: bar
    	taşınacak hesap: baz

- taşınacak hesapta `bar` deposu açılır (boş depo)

- yereldeki `bar` kopyasına girip uzak referansı değiştirilir

    	// eski referans git@github.com:foo/bar
    	$ git remote set-url origin git@github.com:baz/bar
    	$ git push --all

bu yöntem sayesinde depo tarihçesi korunmuş olur.
