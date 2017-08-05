---
title: Kişisel IAM Kullanıcısı oluşturmak
tags:
keywords: 
summary: 
sidebar: aws
permalink: kisisel-iam-kullanicisi-olusturmak
folder: aws
layout: page
---

## 3 - Create Individual IAM Users

Kişisel IAM kullanıcıları yönetmeye başlamadan önce IAM Kullanıcı, nedir, ne işe yarıyor ona bakalım.

<img src="https://forumlogs.com/uploads/default/original/2X/2/25a2a693e058958b1a02f3338e1c96e7688f20a8.jpg" width="638" height="275">

IAM kullanıcısı, AWS ile etkileşim kurmak için kullanan kişiyi veya hizmeti temsil etmek üzere AWS'de oluşturduğunuz bir varlıktır. AWS'deki bir kullanıcı ad ve kimlik bilgilerinden oluşur.

### Özetle IAM Kullanıcısı
IAM kullanıcısı bir organizasyondaki kişi veya hizmeti temsil eder.

### Kişisel IAM Kullanıcısı Oluşturma


<img src="https://forumlogs.com/uploads/default/original/2X/9/9ff023f74a115a5a2a3edde001b66bd87735dd16.JPG" width="690" height="283">



Kullanıcı oluşturmayı 4 adımda yaparız.

<img src="https://forumlogs.com/uploads/default/original/2X/e/efeee8483fdf5e0fdf268cea0850b0ce4f040b3b.JPG" width="618" height="161">

Amazon, root hesabımızı mümkün olduğu kadar en az kullanmamızı önermekte, bu yüzden bir tane admin kullanıcı oluşturup ona yönetici yetkisi atamak hem en iyi pratikler açısından hem de kullanıcı oluşturmayı kavrama açısından iyi bir deneyim olacaktır.

Manage users'a tıklayarak işe başlayabiliriz.

#### Details



<img src="https://forumlogs.com/uploads/default/original/2X/e/ecf222e5f63fbb2bf2193813a900c33080287ee6.JPG" width="690" height="322">
Detaylar kısmında, detaylardan bahsecek olursak.

#### Acess type - Erişim türünü nasıl olmalı?

Kullanıcı programla yani API CLI SDK kullanarak erişebilsin mi eğer öyleyse bir tık alırım diyor.

Örneğin bir geliştiriciniz var ona kullanıcı açıyorsunuz, Programatic acess mantıklı bir karar olabilir.

#### Create password 

Diğer yandan kullanıcı pasaportunu siz mi ayarlamak istiyorsunuz yoksa  otomatik mi olsun?
####  Request password reset

Kullanıcı giriş yaptıktan sonra parolasını değiştirsin mi?


Next permissions  tıklayarak devam edebiliriz.

#### Set permissions

Burada üç tane ayar yapma şansımız var. 

* Bir gruba ekleme (Add user to group)  - Daha o konuya gelmedik. 

* Var olan bir kullanıcının yekilerini kopyala (Copy permisions from existing user) - Bu ilk kullanıcımız

*  Var olan bir poliçeyi bağla (Attach exsiting policies) - AWS tarafından hazır olarak gelen yönetici poliçesini bağlayabiliriz.


<img src="https://forumlogs.com/uploads/default/original/2X/5/550cbfd0c979ef61950452be3378f554f06fdf30.JPG" width="690" height="286">

AdministratorAccessi'e bir tık verip add review'e tıklayalım.


<img src="https://forumlogs.com/uploads/default/original/2X/e/e224c45767f20b6455107c9334c689e812c17aaa.png" width="690" height="133">


<img src="https://forumlogs.com/uploads/default/original/2X/2/2c46bb744e8b0ff3c059b4b27a929c1a30f8e495.JPG" width="690" height="304">

Son olarak create user'ı tıklayarak işlemi tamamlamış olacağız.

Tebrikler yönetici yetkisine sahip bir kullanıcımız var artık.