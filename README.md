<h1 align="center"> Naruno </h1>

> Neden kuruyorum? Donanımı neredeyse hiç yok deneliecek kadar az, sunucu almadım bir node'un yanına kurdum.

> Teşvikli evet, 1000 kişi ile sınırlı, ne kadar süreceği hakkında bilgim yok tahmınım kısa.

> Topluluk kanalları: [Duyuru](https://t.me/RuesAnnouncement) - [Sohbet](https://t.me/RuesChat) - [Naruno Discord](https://discord.gg/YR2DYn72)


<h1 align="center"> Gereksinimler </h1>

> [Hetzner Sunucu](https://github.com/ruesandora/Hetzner/edit/main/README.md) Kullanıyorum.

```sh
1 CPU
1 RAM
500 MB (not, SSD değil)
Ubuntu 20.04 veya üstü.
```

<h1 align="center"> Kurulum </h1>

```sh
# Öncelikle güncellemeler ve Kütüphaneler

sudo apt-get update && sudo apt-get upgrade -y
sudo apt install ca-certificates curl gnupg lsb-release git htop python3
```

<h1 align="center"> PIP kurulumu yapıyoruz </h1>

> 1- Küçük bilgiler ✍🏻: pip, python'da bir paket yöneticisidir, yüklediğimiz kütüphaneleri daha efektif kullanabilmek için kullanırız.
```sh
wget https://bootstrap.pypa.io/get-pip.py
python3 get-pip.py

# Pip ile Naruno kurulumu yapıyoruz
pip3 install naruno
```

<h1 align="center"> Cüzdan oluşturma ve Token alma </h1>

```
# <ruesSifre> yazan yere bir şifre belirleyin ama unutmayın yoksa walleti açamazsınız.
narunocli --createwallet <ruesSifre>

# Incentive almak için wallet 1 cüzdana geçmek gerekli
narunocli --wallet 1

## Çıkan 2 cüzdanlı çıktıyı kaydedin.
narunocli --printwallet
```


> [Bu](https://naruno.org/ourloginmyfrient.php?action=register) adrese gidip kullanıcı adı ve mail ile register olluyoruz.

> Daha sonra `system@naruno.org` mail adresine, `CURRENTLY USED` başlığında ki `1` numaralı `cüzdan adresinizi` ve `discord isminizi` mail olarak atalım bize token gelecek.

> Şu formatta mail atalım, discord ismi - cüzdan adresi altlı üstlü. Tokenler gece kuruyorsanız bu node'u gelmez sabah gelir.

> Tokenleri görmek için: `narunocli -gb` komutunu giriyoruz ve çıktıda `1002` veya `1004` gibi bir sayı yazar.

<h1 align="center"> Ping system'i kurma ve Node'u başlatma </h1>

```
## ping atalım
pip3 install address_ping_system

# Baklava modunu açmamız gerekli aşağıdaki komudu girin
narunocli -bon

# Not: Bazen komutlar çalışmaz veya hata görürseniz minimun 5 dakika bekleyiniz lütfen sonra deyeniz
# Not- 2: Bunu sync olmak gibi düşünebilirisniz.
```

<h1 align="center"> Son işlemlerimiz </h1>

```
#  Bu komutta, <ruesSifre> yazan yere daha önce belirlediğiniz şifreyi yazın.
#  1984 portunu başka nodeda kullanıyorsanız kendiniz belirleyebilirsiniz.

aps --password <ruesSifre> --port 1984 ping c923c646f2d73fcb8f626afacb1a0ade8d98954a
```

> Bu komuttan sonra `4-5` dakika log akacak ve loglar kesilip `True` çıktısı verecek.

![image](https://github.com/ruesandora/Naruno/assets/101149671/be63d1d7-9ca3-41f7-bd24-238b8a4849bc)


> 2- Küçük bilgiler ✍🏻: VPS içinde çalışan portlara bakmak için: `lsof -i -P -n | grep LISTEN`

> Explorer üstünde istediğiniz işlemi görüntülemek için [buradan](http://scan.test_net.1.naruno.org/).

> Cüzdan Yedekleme: `narunocli --narunoexport` , Ardından sunucuda `/usr/local/lib/python3.8/dist-packages/naruno/backups/` altındaki .zip dosyasını indirip yedek alabilirsiniz

> Başka bir sunucuya taşımak için, sırasıyla komutlar: 
```
narunocli --narunoimport zip_dosya_yolu 
narunocli --wallet 1
narunocli -bon
```

> Nodu silmek için 
```
pip3 uninstall naruno address_ping_system -y
aps --password <ruesSifre> --port 4569 ping c923c646f2d73fcb8f626afacb1a0ade8d98954a
```

<h1 align="center"> Konu dışı </h1>

> 3- Küçük bilgiler ✍🏻: bazı örneklerde gösterdiğim küçükBüyük yazım sitiline camelCase deriz, birleşik yazılan kodda araya _ koymak yerine camelCase kullanmak daha hoş bence.

> Ayrıca yıl sonuna doğru eğer yapabilirsem Java veya Python öğretmeye başlayacağım, o zamana kadar `küçük bilgiler` ile aşinalığınız arttırmaya çalışırım.

> Naruno zaten hiç alan kaplamadığı için gittiği kadar çalıştırırım node'u.

> Topluluk kanalları: `Genellikle burada çok aktifim`, [Duyuru](https://t.me/RuesAnnouncement) - [Sohbet](https://t.me/RuesChat) - [Naruno Discord](https://discord.gg/YR2DYn72)
