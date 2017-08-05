---
title: Amazon EC2 Linux Örneği Oluşturma
keywords: 
summary:
sidebar: aws
permalink: amazon-ec2-ornegi-olusturma
folder: aws
---

## Amazon EC2 Linux Örneği Oluşturma

VPC, bölümünde EC2 örneği oluşturmuştur. Şimdi ise hemen hemen aynı işlemi yapacağız fakat biraz konuyu biraz daha ayrıntılı işleyeceğiz.

Planımız oldukça basit

* EC2 oluştur
* Pem anahatarını ppk anahtarına çevir  (Windows kullanıcıları için)
* Ssh ile bağlan
* EC2 örneğini sonlandır

## EC2 oluştur

Bu kısım 9 adımdan oluşmaktadır.

### Örnek Uygulama Başlat
<img alt="ec2 paneli" src="https://forumlogs.com/uploads/default/original/2X/4/484da1b846e0d3a46c941ca54435c52009cdbe29.JPG" width="690" height="326">

Launch instance tıklayarak işe başlayabiliriz.

### AMI Seç
<img alt="ami seç" src="https://forumlogs.com/uploads/default/original/2X/0/0413949d5ab24e72ee8fa5a433d54575c8316241.JPG" width="690" height="210">

İşletim seçme kısmı, linux ami ile başlayabiliriz ama normal şartlarda ihtiyacınıza göre işletim seçebilirsiniz tabii ki.

### EC2 uygun Örnek Türü Seç

<img alt="örnek türü seç" src="https://forumlogs.com/uploads/default/original/2X/e/e5549c3b7545d14e348d3b7bac252567632bd51f.JPG" width="690" height="391">

Örnek alıştırma için t2.micro seçtik.

### Bazı EC2 Örnek Ayarlarını Düzenle

<img alt="ec2 örnek ayarları" src="https://forumlogs.com/uploads/default/original/2X/a/a3bd4ccd34a8052e04e1743349c08c46050f3388.JPG" width="690" height="337">

Bu kısımdan hiç bir şeyi değiştirmedik ama gerçek senaryoda

Network'ten daha önceden tasarladığımız vpc seçmek
Subnet kısmından uygun subnetimiz seçmek
IAM role atamak 

Gibi kısımları ihtiyaçlarımıza göre değiştirmemiz gerekli. VPC bölümünde bunların ne işe yaradıklarını kavramıştık. Daha sonra gerçek senaryoya yakın bir alıştırmada buları daha iyi kavramış olacağız.

Şimdilik burayı böyle bırakıyoruz ama VPC Subnet size çok yabancı geliyorsa o bölüme dönüp, konuları gözden geçirmenizi öneririm.

### Depolama Ayarları


<img alt="ec2" src="https://forumlogs.com/uploads/default/original/2X/f/f1a41329533556d9c52c95f0a99dbb2ef9370b0c.JPG" width="690" height="289">

Depolama ayarı kısmında EBS yani örneğimize ssd veya hdd eklediğimiz kısım. Add new Volume diyerek ekstra alanlar ekleyebilir veya root depolama alanımızın boyutunu yükselte biliriz. Volume type'tan ihtiyacımıza göre en uygun olanı seçebiliriz. 

Delete on Termination işaretliyse

EC2 örneğini sonlandırdığımızda bu EBS depolama alanınında onunla birlikte silinmesi demektir. 


### Etiket Ekle

<img alt="ec2 etiket ekle" src="https://forumlogs.com/uploads/default/original/2X/9/91e49476b647f4878ac92cb931f40c743c03e170.JPG" width="690" height="316">


Etike kısmı EC2 örneklerini kolay bulmak için tasarlanmış bir bölümdür. Add Tag tıklayarak etiket ekleyebiliriz.
### Güvenlik Grubunu Ayarla


<img src="https://forumlogs.com/uploads/default/original/2X/9/903709416301bf8907afc78d807fd4b7e87feb44.JPG" width="690" height="315">


Güvenlik grubu ayarı EC2 örneğimiz için güvenlik duvarı oluşturduğumuz kısımdır.

Bu alıştırmada SSH 22 her ip'den istek alabiliyor. Source kısmından bunu myip yapabiliriz böylece sadece ssh ile sizin ipden istek alabilir.

Önceden oluşturduğumuz güvenlik ayarlarını da kullanabiliriz.



###Ayarları Gözden Geçir

<img src="https://forumlogs.com/uploads/default/original/2X/b/b50a4a7e139c5f1ea34a4908f1e4162d0c1f9a2c.JPG" width="690" height="313">

Ayarları istediğimiz gibi olduğunu gözden geçirip daha sonra oluştura tıklayabiliriz.

### Pem Dosyası Oluştur


<img src="https://forumlogs.com/uploads/default/original/2X/3/39d44652cde1b6a2b6f61986e087fcc5e7472def.JPG" width="669" height="500">

En son olarak EC2 örneğimize ulaşmak için key pair indirmemiz gerekli eğer. Bu dosyayı güvenli bir yerde saklamalıyız yoksa EC2 örneğine giriş yapamayız. 

##  Pem anahatarını ppk anahtarına çevir  (Windows kullanıcıları için)

Buradan ilk olarak [puttygen.exe](https://the.earth.li/~sgtatham/putty/0.68/w32/puttygen.exe) indirmemiz gerecek.

Kurmaya gerek olmayan bir uygulama. Puttygen'i açalım

<img alt="putty gen" src="https://forumlogs.com/uploads/default/original/2X/6/62ffe8cd1202029a0e7e0d86375acd744688eaf2.JPG" width="475" height="468">

Load kısmından indirdiğimiz. key pair sonu pem ile biten dosyayı yükleyelim. Burada dikket etmemiz gereken seçmek isterken all files seçeneğine getirelim ki .pem dosyasını görsün.

Daha sonra save private tıklayarak dosyayı kaydedelim.

Hepsi bu kadar

## Ssh ile bağlan

### Linux veya Macos'tan kullanıcıları için

Bu kısım linux yöneticisi kısmı ile ilgili aslında. Normal olarak ssh bağlantısını bilen birisi bunun rahatlıkla yapacaktır.

<img src="https://forumlogs.com/uploads/default/original/2X/0/025e4365cd83ff9839c20254e89c3bb4970989a7.JPG" width="483" height="295">

EC2 örnekleri panelinden connect kısmından direk olarak ssh komutunu alabiliriz.

<img src="https://forumlogs.com/uploads/default/original/2X/6/689858a64dc52cbcb51a886f8bda61e2377e7977.JPG" width="546" height="500">

Bu kısım bize nasıl yapılacağını göstermekte. 

Güvenlik açısından 
pem dosyamızın yetkisini kısıtlayabiliriz. Çünkü pem dosyası EC2 örneğine girme anahatarını barındırmakta.

Example kısmındaki komutu alıp terminale direk olarak yazabiliriz burada dikkat etmemiz gereken nokta .pem dosyasının aynı dizinde olması eğer değilse -i den sonra pem dosyasının dizin adresi yazılmalı, 

<img src="https://forumlogs.com/uploads/default/original/2X/d/d987eeac7e374bb07c8bfd794052d2ca368ed2f4.JPG" width="532" height="255">

<img src="https://forumlogs.com/uploads/default/original/2X/9/980b152e5874e7724092c23f9971ccd6d87d743a.JPG" width="542" height="179">

Ve işlem tamamdır.

### Putty ile girme - Windows kullanıcıları için

[putty 64 bit kullanıcıları için](https://the.earth.li/~sgtatham/putty/latest/w64/putty-64bit-0.70-installer.msi)
[puıtty 32 bit kullanıcıları için](https://the.earth.li/~sgtatham/putty/latest/w32/putty-0.70-installer.msi)

Putty indirdikten sonra açalım.

<img src="https://forumlogs.com/uploads/default/original/2X/b/b93788e28a4761e9ef99be3c53ef719cd17f91d9.JPG" width="445" height="435">

host name veya ip address kısmına ip adresimizi yazalım.


ip veya host adımız nereden bakalıyoruz?

EC2 örneklerinin çalıştığını kısımdan veya connect seçeneğinde bize nasıl ssh ile bağlanacağını gösteren kısımdan

<img src="https://forumlogs.com/uploads/default/original/2X/f/f748f09d229404be1c271749d79c267e446755f8.JPG" width="448" height="434">

Bu kısımda browse tıklayarak .ppk dosyamızı seçiyoruz ve open diyoruz.

<img src="https://forumlogs.com/uploads/default/original/2X/9/99e8b1a6d8825c0b3c10b94361e709880d8ef6a1.JPG" width="427" height="290">

Bu uyarı ile karşılaşmamız gerekli

<img src="https://forumlogs.com/uploads/default/original/2X/c/c99fff180935d0a16892889076ab5b591d3f57e6.JPG" width="524" height="151">

login as çıkacak root adımız ec2-user bu yüzden ec2-user yazıyoruz ve bağlantı gerçekleşti.

## EC2 Örneğini Sonlandır

<img src="https://forumlogs.com/uploads/default/original/2X/7/7689124d4b56848157ea3382cb3d39ad638f26f5.JPG" width="323" height="304">

Oldukça kolay EC2 örneğimiz seçiliyken.

Actions'a tıklayıp oradan instance state daha sonra terminate tıkladığımızda bu işleme başlamış olacaktır.