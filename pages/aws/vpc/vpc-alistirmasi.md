---
title: VPC Alıştırması
keywords: 
summary:
sidebar: aws
permalink: vpc-alistirmasi
folder: aws
layout: page
---


## VPC Alıştırması

Eğer alıştırma yapmazsak, bu konu havada kalacak.


> Başarı için plan yapmıyorsanız, o zaman hükmen başarısızlığı planlıyorsunuz demektir.

#### Rene Descartes

### Yapılacaklar Listesi

* VPC Oluştur
*  Subnet (Alt Ağ) oluştur
*  Internet Gateway (İnternet Geçidi) Oluştur.
*  Route Table'ı İnternet Gateway'e bağla
*  EC2 instance oluştur
*  EC2 instance'ı Elastic IP ile ilişkilendir
*  EC2 instance'a console'dan bağlan
*  VPC ve EC2 Sil



### VPC Oluştur


VPC, oluşturmak oldukça basit. İlk önce vpc paneline gelmemiz gerekli

<img alt="VPC sidebar" src="https://forumlogs.com/uploads/default/original/2X/b/bb509821b100e726c554f5faaefd3c008c9d5d36.JPG" width="174" height="415">

VPC panelinde sol taraftan Your VPCs'e gelelim.

<img alt="create VPC" src="https://forumlogs.com/uploads/default/original/2X/7/758f7f5e196bb3e9fd828adf1362dc74691dbf11.JPG" width="629" height="273">

create VPC tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/8/88dca0df3d0cada783cde44181ed9e9cc9622305.JPG" width="690" height="409">

Name tag, VPC'ye vereceğimiz isim etiketi

CIDR block, işte burada söyleceklerimiz var. 

#### CIDR Nedir?
#### Neden 10.0.0.0/16? diyebilirsiniz.

Konumuz Networking değil bu yüzden mümkün olduğunda kısa tutacağım.

CIDR adresleri, yönlendirme tablolarının boyutunu azaltır ve daha fazla IP adresi sağlar.

<img alt="CIDR hesaplama" src="https://forumlogs.com/uploads/default/original/2X/5/54496a0f012de8ca6efdc481fedce34d50177200.JPG" width="439" height="401">

10.0.0.0/16 yazdığımızda VPC'mizde 65536 tane ip barındırabileceğiz. Eğer 24 yaparsak 256 ip.

VPC oluşturduktan sonra bu değiştirme şansı olmadığı için 16 yapmak en mantıklısı.

Siz de hesaplama yapmak isterseniz. Buyrunuz [CIDR hesaplama](http://www.ipaddressguide.com/cidr).


Bu arada 

> VPC, 16 - 65,536 IP adresi içerebilir.

 Yani 16 değeri verdiğimizde maksimum ip içeren ağı oluşturmuş oluruz.

Alıştırmamıza geri dönelim. 

10.0.0.0/16 yazdıktan sonra Yes, Create diyelim.

<img src="https://forumlogs.com/uploads/default/original/2X/c/cd6570d88aa1a8f02ef684840f929ac5682589b2.JPG" width="690" height="242">

oluşan panelde VPC'ye tıklayıp alt taraftaki summary kısmından VPC'nin özet bilgilerini inceleyebiliriz.

### Subnet (Alt Ağ) Oluştur

<img alt="subnet sidebar" src="https://forumlogs.com/uploads/default/original/2X/1/1cd3f11ee0671bb2bc2e57be0866c38ae08e49d2.JPG" width="164" height="388">

Subnets'e tıklıyoruz

<img src="https://forumlogs.com/uploads/default/original/2X/0/06fe3e3708b168108d5ae4e5899b2b38f48dd949.JPG" width="690" height="265">

Create Subnet

<img src="https://forumlogs.com/uploads/default/original/2X/6/6e8c58fe785a4150f725c67ce2d2a4cf9c706d17.JPG" width="690" height="370">

Burada VPC'yi ornek-vpc veya ismini ne koyduysanız onu seçiyoruz böylece 

Availability Zone us-west-2a seçtim ama şuan bu hiç fark etmez.

CIDR Block 24 seçiyoruz böylece 256 IP barındırabileceğiz.

Yes, Create diyoruz.

<img alt="subnet summary" src="https://forumlogs.com/uploads/default/original/2X/b/bf4f8242fd199e9b0da23eb4b0726d57ee5face0.JPG" width="690" height="221">


Bu da subnetimizi özeti

## İnternet Gateway (İnternet Geçidi) oluştur

<img src="https://forumlogs.com/uploads/default/original/2X/a/ac20d1a3e8be12f83a2252de20b72392499d2fa3.JPG" width="173" height="388">

İnternet Gateways'e tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/1/1535fdf879cce9abf95d6af7797132df1e511a25.JPG" width="690" height="285">

Create Internet Gateway

<img src="https://forumlogs.com/uploads/default/original/2X/9/9cb21e3e72a83e361c5195413176028a7828c57a.JPG" width="690" height="222">

İsim etiketini girelim ve yes create'e basalım.

<img src="https://forumlogs.com/uploads/default/original/2X/2/255767e3f2e507c092eeea67fce964d973f7e566.JPG" width="690" height="226">

İnternet geçidini oluşturduk şimdi sıra onu bağlamakta


<img src="https://forumlogs.com/uploads/default/original/2X/f/fc0849d919c761d66b83d964d02fe15a5680bd71.JPG" width="525" height="252">
Attact to VPC'ye tıklayalım
<img src="https://forumlogs.com/uploads/default/original/2X/0/0ce67bb5de243e00805de59560db87e10130d1e2.JPG" width="690" height="238">

VPC'mizi seçip Yes, Attach diyelim.

<img src="https://forumlogs.com/uploads/default/original/2X/a/adfc41e19a1ca999ddfc4a5ac10dd2bb5afa7e45.JPG" width="690" height="204">

Ve ilişkilendirildi.

## Route Table'ı İnternet Gateway'e bağla

<img src="https://forumlogs.com/uploads/default/original/2X/e/e5a4bf91dab2beefa70335812f26ab97834ef2a3.JPG" width="168" height="325">

VPC'imizle bağlı olan route table'ı seçelim.

<img src="https://forumlogs.com/uploads/default/original/2X/b/b55f558f3e2d135b1bd9e7263aac63401801c93c.JPG" width="690" height="200">

Routes'a gelip gerekli bilgileri girelim.

<img src="https://forumlogs.com/uploads/default/original/2X/5/523555f065ca2d9e00280b600144ceafda6d7d0f.JPG" width="690" height="251">

0.0.0.0/0 bizi internetten trafik almamızı sağlayacak.


<img src="https://forumlogs.com/uploads/default/original/2X/b/b39603bf158079bf281d880862186420fa1ecbe2.JPG" width="662" height="218">

Status active olması gerekli 

Fark ettiyseniz, Route Table oluşturmadık. VPC oluşturduğumuzda gelen main route table'ı kullandık. Bu yönlendirici tablosu oluşturulan bütün subnetlerle otomatik olarak ilişki kurar. Bu yüzden bu yönlenrici tablosunu subnet ile ilişkilendirmeye gerek duymadık ama istersek bunu yapabiliriz.

Subnet associations'tan bunu yapabiliriz.


<img alt="route table associations" src="https://forumlogs.com/uploads/default/original/2X/1/1577dccd78a82890f2ffd5e1e7c13cb806c7fdfc.JPG" width="628" height="179">


## EC2 İnstance Oluştur

EC2 servisine gelelim.

<img src="https://forumlogs.com/uploads/default/original/2X/8/8b94e4f5d0036639d0cd7668f1948f51968bbfe1.JPG" width="690" height="321">

Böyle bir panel gelmesi gerekli
<img src="https://forumlogs.com/uploads/default/original/2X/6/69f8d0fa245b3107aeccebde17d65fd965165d8f.JPG" width="690" height="276">

Linux'ü seçelim

<img src="https://forumlogs.com/uploads/default/original/2X/7/737d1251f35933306c3d946865cd829e4deb8fdb.JPG" width="690" height="319">

t2.micro diyip devam edelim

<img src="https://forumlogs.com/uploads/default/original/2X/8/8db7d88eb6678305ae30b3e7c4179d3821668224.JPG" width="690" height="220">

Burada

* Network ornek vpcp
* Subnet ornek subnet
* Auto-assign public IP enable olmalı

<img src="https://forumlogs.com/uploads/default/original/2X/e/eeaa8f748851c79bd930401f371246b1baf4eb32.JPG" width="690" height="163">

add storage buray şimdilik geçiyoruz. Varsayalan işimizi görecek.


<img src="https://forumlogs.com/uploads/default/original/2X/f/f3c6794829ec6c7232529a38714f7f8df0a4b7ac.JPG" width="690" height="268">
Burayı direk geçebiliriz. Bu alıştırmada etiket  eklemimize gerek yok. Daha sonra bu kısım detaylı bir şekilde anlatılacaktır.

<img src="https://forumlogs.com/uploads/default/original/2X/b/b6f7f5b6c9e3a06911b40b0bc9871910dccda8f8.JPG" width="690" height="309">

Güvenlik grubu eklemek istiyorsak burada yapabiliriz bunu örneğin ben sadece ssh ve http'yi açtım. Gerçek hayatta ssh'i  sadece ip adresime açmam en iyi pratiklerdendir. Ayrıca işlemim bittiğinde ssh güvenlik kuralını silmek güvenliği bir kat daha artırır.

<img src="https://forumlogs.com/uploads/default/original/2X/9/9057246dc7d0aa371fa3f37cf3f505de192c5a3c.JPG" width="690" height="295">
Oluşturduğumuz instance'in gözden geçirebiliriz.

<img src="https://forumlogs.com/uploads/default/original/2X/0/0232ae933e957a5390934ff59c6e96fce5541312.JPG" width="681" height="500">

ismini oluşturup bunu güvenlik bir yerde saklıyoruz


<img src="https://forumlogs.com/uploads/default/original/2X/f/f8c83a39c7bb12e0f8b9c13709a81ef8e89209ef.JPG" width="690" height="95">

Ve sunucumuz başlatıldı.

### EC2 instance'ı Elastic IP ile ilişkilendir

Elastik IP adresi dinamik bulut için tasarlanmış statik bir IPv4 adresidir. Elastik bir IP adresi AWS hesabınızla ilişkilendirilir.

İleri bir konu ama şunu diyebiliriz; statik bir IP'imizi domainimize bağlarız. Böylece sunucu değiştirirken domain için sunucunun public IP'si ile uğraşmak yerine yeni sunucuyu Elastic IP ile ilişkilendiririz.

<img src="https://forumlogs.com/uploads/default/original/2X/b/bd68bfdfa3e488deb079c6c2a6820e3e72a8051d.JPG" width="167" height="190">

Sağ taraftaki sidebar'dan Elastic IPs seçelim

<img src="https://forumlogs.com/uploads/default/original/2X/5/5eb9b11ef400d11d0b85c42eb06dc4f07ca3b20e.JPG" width="649" height="200">

Allocate new address tıklayalım

<img src="https://forumlogs.com/uploads/default/original/2X/2/2097e765b677bb6ba92cbe0fac304ddeebb88c69.JPG" width="620" height="230">

Allocate diyelim

<img src="https://forumlogs.com/uploads/default/original/2X/4/4b331487793b77a3a353ada702fcd59ab65dcf5a.JPG" width="393" height="249">

Elastic IP oluşturuldu instance'a bağlayalım. Associate address diyelim.

<img src="https://forumlogs.com/uploads/default/original/2X/d/d43204a60d8ed19beb41493a7267b75259970a69.JPG" width="690" height="258">

Buradan instance'a oluşturduğumuz sunucuyu diğerine de tıklayıp verilen ip'yi seçelim.



<img src="https://forumlogs.com/uploads/default/original/2X/4/41665151d6b389c4fa49ede43fbc60a303180aea.JPG" width="660" height="262">

Bu işlem de tamamdır.

Şimdi EC instance paneline gelerek.

<img src="https://forumlogs.com/uploads/default/original/2X/f/f6fc0424e1e2753dc59cba42c4f2f626b2e59f55.JPG" width="479" height="263">

Actions'dan connect'i tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/0/0a099eab5ca3e9b9cec231fe2c2bd0eb46d5abba.JPG" width="550" height="500">

Example kısmındaki linux komutunu alalım.

<img src="https://forumlogs.com/uploads/default/original/2X/3/3ca91676737c475cf5db775b6fbeadb5ee5207ca.JPG" width="541" height="115">

Console yapıştıralım. Özetle ssh bağlantısı yapacağız daha önce böyle bir şey yapmadıysanız veya windows kullanıcısıysanız bu işlemi şimdilik geçebilirsiniz.

Yes diyoruz bunu zaten klasiktir.


<img src="https://forumlogs.com/uploads/default/original/2X/2/2b345e928101399fed05f41ac2de04c9d3a557a8.JPG" width="460" height="227">


Ve sunucuya erişim sağlandı. 

### EC2 VPC Silme

<img src="https://forumlogs.com/uploads/default/original/2X/f/f6fc0424e1e2753dc59cba42c4f2f626b2e59f55.JPG" width="479" height="263">

İnstance State -> Terminate ile silebilirsiniz.

Aynı şekilde VPC'de de buna benzer işlem yaparak VPC'yi silebilirsiniz.

<img src="https://forumlogs.com/uploads/default/original/2X/4/4b331487793b77a3a353ada702fcd59ab65dcf5a.JPG" width="393" height="249">


Elastic IP de  release addresses tıklayarak silebilirsiniz.