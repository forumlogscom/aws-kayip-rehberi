---
title: S3 Alıştırması
keywords: 
summary:
sidebar: aws
permalink: s3-alistirmasi
layout: page
---

## Amazon S3 Alıştrması

### Yapılacaklar 

* S3 bucket Oluştur
* S3 bucket içinde klasör oluştur
* S3 dosya yükle
* Dosyanın yetkisini değiştir
* Set metadata on an S3 bucket
* S3 bucket ve dosyaları temizle

###  S3 bucket Oluştur

S3 Paneline geldiğimizde karşımıza böyle bir ekran gelecek.

<img alt="s3 panel " src="https://forumlogs.com/uploads/default/original/2X/f/f7dbb3a331963e2fe521ae473dea1d37bca6604d.JPG" width="662" height="500">

 S3 yeni tasarımıyla kullanımı çok daha kolay bir hal aldı.


<img alt="s3 bucket oluşturmak" src="https://forumlogs.com/uploads/default/original/2X/b/bcee2eb26df04e05d65ebdeeaa57eff4bf742e38.JPG" width="502" height="500">

Bucket name'e bucket ismini koyarak işe başlayabiliriz.

<img src="https://forumlogs.com/uploads/default/original/2X/8/88bb23f943df8fad482744e60466fcdfb9b9ece2.JPG" width="506" height="500">

S3 versiyonlama özelliğine de sahip bu ne demek oluyor? 

Yükleyeceğimiz nesnenin değiştiğinde eski versiyonlarının kalmasını istiyorsak versiyonlama tam ihtiyacımız olan olacaktır. 

Logging istekleri detaylarını takip edebiliriz bakabiliriz.

Tags ile etkiletler koyarak bucket'ımızı bulunması, takip edilmesi kolay bir hale getirebiliriz.



<img alt="s3 yetkiler" src="https://forumlogs.com/uploads/default/original/2X/a/a40b299bde9d4231731bd11a35ffe005a812592f.JPG" width="502" height="500">


Burayı varsayılan olarak bırakıyoruz. Burası ne işe yaramaktadır?

Nesnelerimizin yazma ve okuma izinlerinin yönetilmesiyle ilgili bucket'ımızı oluşturduktan sonra bile bunlar değiştirme şansımız bulunmakta.

<img src="https://forumlogs.com/uploads/default/original/2X/1/127f5f7ccd4b53681b54771e98d763ef98027c48.JPG" width="501" height="500">

Son olarak gözden geçiriyoruz. Her şey istediğimiz gibiyse create bucket diyoruz.

<img alt="s3 bucket oluşturuldu" src="https://forumlogs.com/uploads/default/original/2X/c/cc2ea23e8f3ef61b2c2ada634213966780dc5202.JPG" width="644" height="380">



### S3 Bucket İçinde Klasör Oluştur

<img alt="klasor oluşturma" src="https://forumlogs.com/uploads/default/original/2X/0/06c4cddebbceb2f37e92c4825df7beb182319710.JPG" width="626" height="499">

Bucket'a tıklayarak içine girebiliriz. Nesne yükleyebilir veya klasör oluşturabiliriz.

Klasör oluştur diyerek klasörümüzü oluşturmaya başlayabiliriz.

<img src="https://forumlogs.com/uploads/default/original/2X/1/1b5a8b4d8a6766afb5d0d8dbbd43d708cce8b122.JPG" width="644" height="500">

Save ile kaydetme işlemini yaptıktan sonra klasörümüz hazır.

### S3 dosya yükle

Panelde Upload'a tıkadıktan sonra karışımıza yükleme sihirbazı gelecek.

<img alt="s3 dosya ekle" src="https://forumlogs.com/uploads/default/original/2X/3/3935ab4022f470f1bcb67c560439f51730994c2a.JPG" width="508" height="500">


Add Files'a basarak yükleyeceğimiz nesneyi seçelim.

<img src="https://forumlogs.com/uploads/default/original/2X/4/49b8cea28f6f2ba873789ca31a9206dfc6b525f4.JPG" width="506" height="500">

İzinler kısmını aynı bırakıyoruz. İstersek nesnemizi manage public permissions kısmından public yani internete açık hale getirebiliriz.
Bu işlemi yükleme yaptıktan sonra yapacağız o yüzden burayı varsayılan olarak bırakıyoruz.

<img alt="s3 depolama sınıfları kısmı" src="https://forumlogs.com/uploads/default/original/2X/8/859752c449f75537f56b405a3a0c2e24abf72ad9.JPG" width="494" height="500">

Depolama sınıflarının ne anlama geldiğini az çok biliyoruz. Burasını da varsayılan olarak bırakıyoruz.

<img src="https://forumlogs.com/uploads/default/original/2X/d/d99af5fdd4f75d15ee991f8e194396c7bfd68a7e.JPG" width="505" height="500">

Nesnemizi gözden geçirdikten sonra yükleyebiliriz. 

<img alt="s3 yüklenmiş nesne" src="https://forumlogs.com/uploads/default/original/2X/8/889d4d07047cd4775b3739d159c97aff4a87936f.JPG" width="648" height="308">

Nesnemize tıklayarak ayrıntıları görebiliriz.

<img src="https://forumlogs.com/uploads/default/original/2X/f/fdfec597923c07e477f692e8bfe578c1ccbf5e95.JPG" width="455" height="500">

Linke tıkladığımızda çalışmadığını göreceksiniz. Neden?


Çünkü internete açık değil.
<img alt="s3 public yapma" src="https://forumlogs.com/uploads/default/original/2X/9/964d298fe98e5a603df900e028399a4d13c4623e.JPG" width="216" height="499">

Make public diyerek internete açık hale getirebiliriz.

Veya nesnemizin içine girerek

<img src="https://forumlogs.com/uploads/default/original/2X/e/e884b1b38302f34d2ccc8737cd6f478c234d568f.JPG" width="555" height="476">

Make public kısmından erişime açık hale getirebiliriz.

<img alt="s3 ayarlar" src="https://forumlogs.com/uploads/default/original/2X/d/df6e78c79a374270bde1df49934306b1767d3d06.JPG" width="690" height="198">

Bu kısımda ayarlarımızı değiştirmemize olanak tanımakta.

<img alt="s3 metadata" src="https://forumlogs.com/uploads/default/original/2X/5/52c9b8e08562030c299495b424dc5cd98b3aa5b1.JPG" width="540" height="322">

S3'de metadata iki türdür. 

* System-Defined Metadata 
* User-Defined Metadata

Amazon, User-Defined Metadata sayesinde kendi meta verilerimizi eklememize izin vermektedir.



Bir nesneyi yüklerken, nesneye meta veri de atayabilirsiniz. Nesneyi oluşturmak için bir PUT veya POST isteği gönderdiğinizde, bu isteğe bağlı bilgiyi bir ad-değer (anahtar-değer) çifti olarak sağlarsınız. Nesneleri REST API'sını kullanarak yüklerken, isteğe bağlı kullanıcı tanımlı meta veri isimleri, bunları diğer HTTP üstbilgilerinden ayırt etmek için "x-amz-meta" ile başlamalıdır. Nesneyi REST API'sını kullanarak aldığınızda, bu önek döndürülür. SOAP API'sini kullanarak nesneler yüklerken, önek gerekli değildir. Nesneyi SOAP API'sini kullanarak geri getirirseniz, nesneyi yüklemek için hangi API kullandığınızdan bağımsız olarak önek kaldırılır.

#### Ayrıntılı bilgi için

<a target="_blank" href="http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingMetadata.html">Using Metadata</a>



<img alt="s3 yetkiler" src="https://forumlogs.com/uploads/default/original/2X/4/44b54f1c098af6c24c10ef71f2634d87927c2ef6.JPG" width="690" height="366">

Yeni bir kullanıcı eklediğimiz, izinleri yönettiğimiz bölüm.

### S3 Bucket ve Dosyaları Temizle

<img alt="s3 bucket silme" src="https://forumlogs.com/uploads/default/original/2X/2/234ce8472f0c65ac00b6cd402e9e3bad4faec837.JPG" width="690" height="318">


Delete Bucket diyerek Bucket'ı silebiliriz. Empty Bucket ile içini boşaltabiliriz.


<img alt="s3 bucket silme onay" src="https://forumlogs.com/uploads/default/original/2X/3/329f84ca411faefe338bb643c96647a60bd79a2c.JPG" width="640" height="500">

Sileceğimiz bucket isimini onaylayarak silme işlemini gerçekleştirebiliriz.