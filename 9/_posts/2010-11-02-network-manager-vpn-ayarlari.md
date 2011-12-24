---
layout: post
title: network-manager vpn ayarları
---

- herşeyden önce sistem yöneticileri tarafından size bir vpn client doğrulama paketi gelmiş olmalı.  bu paket içinde üç dosya önemli, varlığını kontrol edin:

       ca.crt     →  sunucu sertifikası
       <user>.crt →  kullanıcı sertifikası
       <user>.key →  kullanıcı anahtarı

       client.opvn → openvpn komut satırı erişimi için yapılandırma[1]

paketi örneğin ~/.vpn gibi bir dizine açın.  bu dizinin, ~/.ssh dizini gibi, güvenli olmasında yarar var.  dizin 700, dosyalar 600 kipinde.

- doğru yazılımların kurulduğuna emin olun:

       $ sudo apt-get install network-manager-openvpn

yazılımlar eksik değilse paneldeki network-manager (nm) appletinde vpn
bağlantıları kısmına girdiğinizde bir vpn bağlantısı eklenebilir hale
gelecektir.

- yeni bir VPN bağlantı oluşturarak (buna örneğin "uzak" gibi bir isim verebilirsiniz) şu değerleri girin (gateway için client.ovpn içine bakmalısınız aşağıdaki sadece bir örnek):

       gateway (geçit): 19.191.9.19 (bu değer client.ovpn içinde yazar)
       type: default değerde bırakın
       user certificate (kullanıcı sertifikası): ~/.vpn/<user>.crt
       ca certificate: ~/.vpn/ca.crt
       private key (özel anahtar): ~/.vpn/<user>.key
       private key password: boş geçin

sekmenin üst ve altında kalan seçenekler size kalmış (bende ikisi de
kapalı).

- ileri (advanced) ayarlara girerek "use LZO compression" etkinleştir.

bu noktadan itibaren vpn bağlantasını seçerek etkinleştirebilir ve kullanabilirsiniz. fakat vpn bağlantısı etkin iken ağ erişiminde bir yavaşlama ve/veya uzem sayfalarına erişememe gibi sorunlar çıkabilir (ben de oldu).  bunun engellemek için rotayı biraz spesifik yapmalısınız. nm'de ilgili vpn bağlantısını aşağıdaki gibi düzenleyin:

- ipv4 ayarları sekmesinde 'routes'a girerek alttaki iki seçeneği aşağıda verilen uyarılara göre işaretleyiniz (ingilizcesiyle):

        "Ignore automatically obtained routes" =>  *tiksiz*
        "Use this connection only for resources on its network" => *tikli*

hepsi bu kadar.

\[1] vpn bağlantısını nm yerine komut satırından kullanmak isterseniz:

       $ sudo openvpn ~/.vpn/client.ovpn
