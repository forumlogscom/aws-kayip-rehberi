---
title: Amazon RDS Veritabanı Oluşturma
tags:
keywords: 
summary:
sidebar: aws
permalink: rds-olusturma-alistirmasi
---


## RDS Oluşturma Alıştırması

<img src="https://forumlogs.com/uploads/default/original/2X/7/7bb204b6def36b3cf00eff797835331ce874d805.JPG" width="211" height="410">

Subnet Groups'a gelelim. İlk önce subnet oluşturmamız gerekli.

<img src="https://forumlogs.com/uploads/default/original/2X/4/498df7d6fcced567a627da8f0ceb58a1ee7e2dff.JPG" width="461" height="205">

Create DB Subnet Group tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/1/1ef95ee56514c9c295fa6acaaa6fa8322197319e.JPG" width="690" height="489">

İsim ve açıklama kısmını dolduralım

VPC kısmından içinde olmasını istediğimiz VPC seçelim.

add all subnets diyerek var olan bütün subnetleri seçebiliriz. 

<img src="https://forumlogs.com/uploads/default/original/2X/b/bda866a58720f8cb640c16debea6e635dd3cdd7f.JPG" width="690" height="245">


Ve subnet grubumuz hazır.

<img src="https://forumlogs.com/uploads/default/original/2X/7/7bb204b6def36b3cf00eff797835331ce874d805.JPG" width="211" height="410">

Instances tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/2/2716ef4fb8c64d485b7b71aca7ec3e26a43bf9de.JPG" width="662" height="403">

Launch DB instance tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/b/b2ce96bca670b6100f9eb5d8afb277d9e132cec5.JPG" width="690" height="465">

Free tier eligible only tıklayara sadece ücretsiz sevisleri gösterebiliriz.

MySQL kuracağız. Select'e tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/f/fc5bbfaee7492e8e354e352bc12058ccdb923b6d.JPG" width="690" height="325">

Deneme bir örnek oluşturacağımız için Dev/Test'i seçip next step tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/9/92b899df1e69068cc30990d84439c8e8ea53a064.JPG" width="399" height="500">


Veritabanı örnek sınıfını seçebiliriz.

Ayarlar kısmında gerekli yerleri dolduralım ve bunları daha sonra kullanacağımızı unutmayalım.


<img src="https://forumlogs.com/uploads/default/original/2X/7/70a18bb0fcf5bf517a8743e03d8f2c3e0ed94c4c.JPG" width="432" height="500">

Subnet grubunu daha önce oluşturduğumuz ornek-rds siz ne ad verdiyseniz onu seçelim.

Veritabanı ismini belirleyelim.

<img src="https://forumlogs.com/uploads/default/original/2X/d/d55d509503a93bd795a8880ed7e05021023332af.JPG" width="690" height="373">

Yedekleme, İzleme ayarlarını yaptığımız kısım

Örnek olduğu için yedeklemeyi 0 yapabilirsiniz.

<img src="https://forumlogs.com/uploads/default/original/2X/0/0920011d8c91dbcdb0401961d5377f6b6572cd09.JPG" width="690" height="245">

Veritabanının bir süre sonra hazır hale gelecektir.

<img src="https://forumlogs.com/uploads/default/original/2X/1/13ab4e6763d89c2c26840a07bcd7a9da363a29e5.JPG" width="690" height="383">

Veritabanı hazırlanırken bize Güvenlik grubundan rds-launch-wizard yani veritabanımız için oluşturulmuş güvenlik ayarını

172.31.0.0/16 yaparak ağ içi iletişimi izin verelim.

<img src="https://forumlogs.com/uploads/default/original/2X/f/f45118888e91376ea0c179a3cf568773dfe160ba.JPG" width="690" height="350">

EC2 paneline giderek bir tane EC2 örneği oluşturalım.

<img src="https://forumlogs.com/uploads/default/original/2X/7/7a1fe68ec7cc7e216a55f625dc7e4b76c5504723.JPG" width="530" height="231">

Daha önce bu aşamaları yaptığımız için direk olarak Terminal kısmından devam ediyoruz.

<img src="https://forumlogs.com/uploads/default/original/2X/a/a48018573118cdf10585844496297592ad9d0ea1.JPG" width="472" height="139">

> sudo yum -y install msql

komutu ile mysql yükleyelim.

<img src="https://forumlogs.com/uploads/default/original/2X/0/0b761a113fb15b5e6f399cc5d8b5fa1508f0ce4d.JPG" width="591" height="368">

daha sonra mysql örneği paneline giderek endpoint kısmını alalım.

> mysql -h endpointkısmı -u kullanıcıadı -p veritabanıismi

<img src="https://forumlogs.com/uploads/default/original/2X/7/74d16adaa39c8cd95478e2a4ca18a599901dc72d.JPG" width="690" height="134">

Yani özetle klasik veritabanı bağlanma işlemi yapmış olduk. Komutu yazarken port kısmını yazmayacağınızu unutmayın.

<img src="https://forumlogs.com/uploads/default/original/2X/b/bd3d65e9564aa883c7805d15cfb414b50b0bac74.JPG" width="192" height="386">

Veritabanını silmek için instance actions kısmından delete ile silebilirsiniz.