---
title: IAM Roller
keywords: 
summary: 
sidebar: aws
permalink: iam-roller
folder: aws
layout: page
---
## IAM Roles 

IAM'de  bahsetmediğimiz diğer  konu Roller. Roller, geçici olarak kullanabileceğimiz bir dizi yetkinin seçilmesinden oluşur. IAM kullanıcılarına çok benzer fakat Rollerin, kimlik bilgileri (şifre veya erişim anahtarları) yoktur. Bu yüzden bazı durumlarda çok daha mantıklı ve güvenli bir seçim olmaktadırlar.
IAM Role, çözdüğü problem kimlik bilgileri kullanmadan yetki sağlamak diyebiliriz. 

<img alt="iam role" src="https://forumlogs.com/uploads/default/original/2X/f/f1010ac5c301cc25a05aaeb8156c5f49425b396d.JPG" width="690" height="281">

Şu aşamada EC2 ve S3 ne onu bile bilmiyor olabilirsiniz. Rolleri kavramak zamanla olabilecek şeydir. 

### EC2

EC2 en basit tanımıyla, sanal bir sunucu servisidir.

### S3

S3 ise web siteleri için resimleri ve diğer öğeleri depolayan bir servis.

Şimdi bir senaryo düşünelim. 

EC2'in S3'den istek alması gerektiğini varsayalım bunu nasıl yapabiliriz?

Birinci yaklaşım, kullanıcı kimliğimizle bunu yapmak fakat bu güvenlik açısından riskli çünkü EC2 sistemimiz zor da olsa hacklendiğini düşünelim Hacker'ın bizim kimlik bilgilerimize ulaşması güzel bir şey olmaz.

Diğer yaklaşım ise, EC2'ye S3'e giriş yetkisi poliçesi atanmış bir AIM Role ile ilişkilendirerek bu problemi ortadan kaldırmış oluruz. 

### IAM Role Oluşturma

<img src="https://forumlogs.com/uploads/default/original/2X/0/0d06684c9b0e112317366cf1932fc871fda1f0d9.JPG" width="178" height="289">

Roles'a gelelim.

<img src="https://forumlogs.com/uploads/default/original/2X/2/2c0f51e7864587d09cae797a08ddffe9206d01ae.JPG" width="690" height="124">

Create Role Diyelim.

### IAM Role Türleri

<img src="https://forumlogs.com/uploads/default/original/2X/7/74f314db5e81c434f983362fcfe919efc6b3936f.JPG" width="689" height="309">

Karşımıza böyle bir ekran gelecek. Şimdi Rol türlerine baktığımızda 

4 Başlık görüyoruz.

* Aws Service Role
* Aws Service Linked Role
* Role for cross-accound access
* Role for identitiy provider access


<img src="https://forumlogs.com/uploads/default/original/2X/5/525c9fd05df41eb73e0c597149d2a146f5599862.JPG" width="690" height="287">

S3FullAccess yetkisi verip devam ediyoruz.

<img src="https://forumlogs.com/uploads/default/original/2X/4/451e06001f185ec1a7f2bdb10805f65f647c439a.JPG" width="690" height="296">

Role için gerekli isim ve açıklamayı yazıp devam ediyoruz.

<img src="https://forumlogs.com/uploads/default/original/2X/d/db9e577650ef2b61a60aa653991f8fb7d76d40d8.JPG" width="689" height="207">

Rolümüz hazır. Artık EC2'ye bunu atayabiliriz fakat daha EC2 konusuna gelmediğimiz için burada bırakıyoruz. Burası daha sonra anlam kazanacak.