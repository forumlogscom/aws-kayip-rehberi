---
title: S3 Yasam Dongusu
keywords: 
summary:
sidebar: aws
permalink: s3-yasam-dongusu
folder: aws
layout: page
---


## Amazon S3 Yaşam Döngüsü (Lifecycle)

Yaşam döngüsü yapılandırması, bir kovadaki nesnelerin yaşam döngüsü yönetimini belirtmenizi sağlar. Yapılandırma, bir veya daha fazla kural grubudur, burada her kural, Amazon S3 için bir nesne grubuna uygulanacak bir eylemi tanımlar. 

Bu eylemler aşağıdaki şekilde sınıflandırılabilir:

**Geçiş eylemleri** - Nesnelerin ne zaman başka bir saklama sınıfına geçeceğini tanımladığınız. Örneğin, nesneleri oluşturulmadan 30 gün sonra STANDARD_IA (IA'ya nadir erişim için) depolama sınıfına veya arakesit nesneleri yaratıldıktan bir yıl sonra GLACIER depolama sınıfına geçirmeyi seçebilirsiniz.

**Sona erme eylemleri** - Nesnelerin süresi dolduğunda belirttiğiniz süre. Sonra Amazon S3 süresi dolan nesneleri sizin adınıza siler.

## Amazon S3 Yaşam Döngüsü Nasıl İşler?



<img alt="s3 bucket ayrıntısı" src="https://forumlogs.com/uploads/default/original/2X/0/003ca3cd35af383d9b30dbfa8c6ad3a9cc96a609.JPG" width="377" height="500">

Elimizde bir bucket olduğunu varsayalım.Tıkladığımızda sağ tarafta şöyle bir panel ile karşılaşmamız gerekecek.
Management kısmına tıklayalım. 

<img src="https://forumlogs.com/uploads/default/original/2X/a/a3e3e404972764f922365b718e758a4410031871.JPG" width="690" height="374">

Yeni bir yaşam döngüsü eklemek için add lifecycle rule'a tıklayalım.

<img alt="s3 lifecycle ekleme" src="https://forumlogs.com/uploads/default/original/2X/7/775be229f688ea6628ada80de1d70f4c2dde9a4f.JPG" width="501" height="500">

Yaşam döngüsü kovanın tamamında mı yoksa belli bir klasör  de mi olacak onu belirlediğimiz kısım. Ben Bucket'ın tamamını etkileyecek bir kural olsun diye * kullandım.

<img alt="geçiş" src="https://forumlogs.com/uploads/default/original/2X/f/f91c66762c1382a203fd982d17629169024955dc.JPG" width="509" height="500">

Burada current version (mecvut versiyonu) seçtiğimizde bu versiyona transition yani geçiş kuralları vermemize olanak veriyor. 

İki kural ekledim. 30 gün sonra Stanadart Genel Amaçtan Standart-IA daha sonra 60 gün sonra Amazon Glacier'e geçecek.

<img alt="s3 bitiş kuralı" src="https://forumlogs.com/uploads/default/original/2X/d/da6e9fd3c8f9eefb2b7a17e57afab9c0476555fb.JPG" width="494" height="500">


Yine mevcut versiyonu seçtiğimizde 425 günün sonunda bu silme görevi vermiş oluyoruz.

<img alt="yaşam döngüsü gözden geçirme" src="https://forumlogs.com/uploads/default/original/2X/8/88171f2a8bb0f33fb8f3ae4bb0a05943826c7922.JPG" width="498" height="500">

Gözden geçirdikten sonra yaşam döngüsünü kaydedebiliriz.

<img alt="yaşam döngüsü silme"  src="https://forumlogs.com/uploads/default/original/2X/7/78af68805232da1e41393686c63e89e4bfd17c1a.JPG" width="690" height="244">

Yaşam döngüsü kuralını silmek için yapmamız gereken. Kurala tıklayıp sil demek olacak.

Yaşam döngüsünde söyleyeceğimiz en son şey. Yaşam döngüsünü; bucket'ın tamamına, klasör bazlı veya nesne bazlı ekleyebiliriz.