#Ar.io yeni domain aldıktan sonra yapılması gerekenler

⚠️Öncelikle domain aldığımız namecheap veya vs. nerden aldıysak oraya gidip eski domain den kayıtlı keyleri silelim.

1️⃣ "nano .env"
içine girelim yeni domani girelim

ARNS_ROOT_HOST=<yeni-domain-adresiniz>

2️⃣şimdi certbot kaydı yapalım 
CERTBOTTA YAPACAĞIMIZ BU İŞLEM EN ÖNEMLİ KISIM
Tırnakların arasını doldurup tırnakları kaldırın

sudo certbot certonly --manual --preferred-challenges dns --email <mailAdresiniz@gmail.com> -d <yeni-domainadresiniz.xyz> -d '*.<yeni-domainadresiniz>'

3️⃣devam edelim:
sudo nano /etc/nginx/sites-available/default

burda 6 tane değişmesi gereken yer var eski domaini bulup yenisini yapıştırıp kaydedin

4️⃣Daha sonra nginx konfigrasyonu ayarlayalım ve resetleyelim:
sudo nginx -t
sudo service nginx restart

5️⃣buraya gelip cüzdan bağlıyken kendi gateway adresimize girip sağ üstten edit tıklayıp yeni adresi girip save changes diyelim
https://network-portal.app/gateways#/gateways
