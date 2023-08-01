Ovenden Incentive Program


//IHTIYAÇLAR

1 Core
1Gb Ram
500Mb disk
Ubuntu 20.04Lt ve üstü

https://docs.naruno.org/baklava-testnet/ovenden-incentive-program.html



### SIFIRDAN KURULUM İÇİN

#Öncelikle güncellemeler ve Kütüphaneler

sudo apt-get update && sudo apt-get upgrade -y

apt install ca-certificates curl gnupg lsb-release git htop python3


#PIP kurulumu yapıyoruz

wget https://bootstrap.pypa.io/get-pip.py

python3 get-pip.py


#Pip ile Naruno kurulumu yapıyoruz

pip3 install naruno


#Cüzdan oluşturma

//<ŞİFRE> yazan yere bir şifre belirleyin ama unutmayın yoksa walleti açamazsınız.
// Incentive almak için wallet 1 cüzdana geçmek gerekli aşağıdaki komudu girin


narunocli --createwallet sifre

narunocli --wallet 1

narunocli --printwallet

Wallets:
0) 6d09e8c99487e36fa6e3bd95d9d240505a357e00

1) b356e5edd49015dad8b69c607130588512380f24 - CURRENTLY USED



*** `https://naruno.org/ourloginmyfrient.php?action=register` sayfasına girip kullanıcı adı ve mail adresi gireceksiniz doğrulama mailini yaptıktan sonra`system@naruno.org` mail adresinden size TR saati sabah 12.00 veya 00.00 da davet maili gelecek. Maili cevaplayıp wallet 1 adresinizi ve discord kullanıcı adınızı yazıp yanıtlamanız gerekmekte.


#Cüzdan bakiye görmek için

narunocli -gb


#Application 1: Address Ping System

pip3 install address_ping_system


#Baklava modunu açmamız gerekli aşağıdaki komudu girin

narunocli -bon


#Usage

//<ŞİFRE> yazan yere daha önce belirlediğiniz şifreyi yazın. --port olarak 4569 yerine istediğiniz portu yazabilirsiniz (sunucunuzda farklı bir portla çakışmayacak şekilde). Aşağıdaki komut girildikten sonra çok sayıda çıktı gelmektedir en son "True" komudunu görmemiz gerekmekte. 


aps --password <ŞİFRE> --port 4569 ping c923c646f2d73fcb8f626afacb1a0ade8d98954a


//"True" gördüyseniz işlem bu kadar.. Çıktı aşağıdaki gibi oalcak

023-08-01 20:41:26,793 - DEBUG - TRANSACTIONS - Second one: <naruno.transactions.transaction.Transaction object at 0x7f19f30762c0> (validate_transaction.py:40)
2023-08-01 20:41:26,795 - INFO - REMOTE_APP - New datas received (remote_app.py:733)
2023-08-01 20:41:30,217 - DEBUG - REMOTE_APP - Starting checker function (checker.py:31)
2023-08-01 20:41:41,023 - DEBUG - API - 404: 404 Not Found: The requested URL was not found on the server. If you entered the URL manually please check your spelling and try again. (main.py:692)
2023-08-01 20:41:41,027 - DEBUG - API - ::1 GET http://localhost:4569/transactions/received b'' (main.py:422)
2023-08-01 20:41:41,413 - DEBUG - API - ::1 GET http://localhost:4569/transactions/sended/validated b'' (main.py:406)
2023-08-01 20:41:41,819 - INFO - REMOTE_APP - New datas received (remote_app.py:733)
2023-08-01 20:41:41,820 - DEBUG - REMOTE_APP - Retrieved 3 new transactions (checker.py:46)
2023-08-01 20:41:41,820 - DEBUG - REMOTE_APP - Exiting checker function (checker.py:78)
True


//VPS içinde çalışan portlara bakmak için aşağıdaki komudu kullanabilirsiniz.

 lsof -i -P -n | grep LISTEN


#Explorer üstünde işlemi görüntülemek için aşağıdaki sayfayı kullanın

http://scan.test_net.1.naruno.org/



#Cüzdan Yedekleme

narunocli --narunoexport

//Ardından sunucuda /usr/local/lib/python3.8/dist-packages/naruno/backups/ altındaki .zip dosyasını indirip yedek alabilirsiniz




#Başka bir sunucuya taşımak isterseniz bu komutu kullanabilirsiniz

narunocli --narunoimport zip_dosya_yolu

//Zip dosyasını yeni sunucuda /root altına yüklediyseniz dosya yolu /root/..dosyaismi..zip gibi olur

narunocli --wallet 1

narunocli -bon




## Nodu silmek için 

pip3 uninstall naruno address_ping_system -y


aps --password password --port 4569 ping c923c646f2d73fcb8f626afacb1a0ade8d98954a


