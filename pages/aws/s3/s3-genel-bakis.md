---
title: S3 Genel Bakış
keywords: 
summary:
sidebar: aws
permalink: s3-genel-bakis
folder: aws
layout: page
---

## Amazon S3 Nedir?

Simple Storage Service  yani Basit Depolama Hizmeti (Amazon S3), web üzerindeki herhangi bir yerden herhangi bir miktarda veri depolamak ve almak için basit bir web hizmeti arayüzü bulunan nesne saklama alanıdır. 99,999999999% devamlılık ve Dünya çapında trilyonlarca objeyi barındırmaktadır.

Yani S3 kullanımı **basit** bir **depolama** **servisidir**. Neredeyse her türlü veriyi herhangi bir biçimde saklayabilirsiniz.


<iframe width="100%" height="400px" src="https://www.youtube.com/embed/rKpKHulqYOQ" frameborder="0" allowfullscreen></iframe>


Amazon S3 servisini kullanmak oldukça kolaydır. Google Drive kadar kolay diyebiliriz.

S3 ile ilgili bilinmesi gereken kavramlardan bahsedecek olursak.

* Buckets (Kovalar)
* Objects (Nesneler)
* Keys (Anahtarlar)
* Regions (Bölgeler)

### Buckets (Kovalar)

S3'de Buckets, bilgidiğimiz bilgisayarda kullandığımız ana klasör ile aynı diyebiliriz. Ana klasör derken root yani en üst klasör gibi düşünebiliriz.

Bucket içine klasör (folder) açarak alt klasörler de oluştabiliriz.

### Objects (Nesneler)

S3'de depoladığımız varlıkların hepsi, resim, video her ne ise ona verilen isim obje yani nesnedir.

###  Keys (Anahtarlar)


Anahtar, bir kova içindeki bir nesnenin benzersiz tanımlayıcısıdır. Kovadaki her nesnenin tam bir anahtarı vardır. Bir kova, anahtar ve sürüm kimliği kombinasyonu, her nesneyi benzersiz şekilde tanımladığından, Amazon S3 "kova + anahtar + sürümü" ile nesne arasındaki temel bir veri haritası olarak düşünülebilir.

Örneğin
```
http://kovaadi.s3.amazonaws.com/20016-03-01/Nesne.png
```

İnceleyecek olursak.

"kovaadi" kısmı nesnein barındığı kovanın adını belirtiyor. Bu kısım ise /20016-03-01/Nesne.png anahtarı.

###  Regions (Bölgeler)

Amazon S3'ün oluşturduğunuz kovaları depoladığı coğrafi bölgeyi seçebilirsiniz. Gecikmeyi optimize etmek, maliyetleri düşürmek veya düzenleyici gereksinimleri karşılamak için bir bölge seçebilirsiniz. Amazon S3 şu anda aşağıdaki bölgeleri desteklemektedir:

* US East (N. Virginia) Region 
* US East (Ohio) Region 
* US West (N. California) Region 
* US West (Oregon) Region 
* Canada (Central) Region 
* Asia Pacific (Mumbai) Region 
* Asia Pacific (Seoul) Region 
* Asia Pacific (Singapore) Region 
* Asia Pacific (Sydney) Region 
* Asia Pacific (Tokyo) Region 
* EU (Frankfurt) Region 
* EU (Ireland) Region 
* EU (London) Region
* South America (São Paulo) Region