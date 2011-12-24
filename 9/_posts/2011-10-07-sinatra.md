---
layout: post
title: sinatra kurulumu ve ilk uygulaması
---

adamlar yapmış

### kurulum

eğer sisteminizde 19/x kurulu ise sadece yönetim görevlerinden ruby gem
paketlerini kurup bu aşamayı geçmeniz yeterli eğer 19/x kurulu değilse

        $ sudo aptitude install ruby

        $ sudo ln -s /usr/bin/ruby1.8 /usr/bin/ruby
        $ sudo ln -s /usr/bin/ri1.8 /usr/bin/ri
        $ sudo ln -s /usr/bin/rdoc1.8 /usr/bin/rdoc
        $ sudo ln -s /usr/bin/irb1.8 /usr/bin/irb

        $ sudo aptitude install libyaml-ruby libzlib-ruby

        $ sudo ln -s /usr/bin/gem1.8 /usr/bin/gem

        $ sudo apt-get install libsinatra-ruby

evet sadece bu kadar hem de ruby kurulumları ile birlikte

### ilk uygulama

hemen bir foo dizini açalım ve içeri girelim

        $ mkdir foo && cd foo

foo dizinimizde ilk uygulamamız için hemen bir hi.rb oluşturalım ve içerisine
şu satırları girelim

        require 'sinatra'

        get '/' do
          "Hello World!"
        end

        get '/hi' do
          "hi baby!"
        end

hi.rb kaydedip çıktıktan sonra hemen sinatra gemini çekelim

        $ gem install sinatra

// sudo gerekebilir

sıra uygulamayı çalıştırmakta

        $ ruby -rubygems hi.rb

arkasında promtta şu satırları görüyoruz

        == Sinatra has taken the stage ...
        >> Listening on 0.0.0.0:4567

eğer localhost'da çalışıyorsanız 0.0.0.0 yazan yer localhost olur

ilk uygulamamızı yazdık işte bu kadar
