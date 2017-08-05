---
title: MFA'yı root hesabında etkinleştirme
tags:
keywords: 
summary: 
sidebar: aws
permalink: mfa-root-hesabinda-etkinlestirme
folder: aws
layout: page
---


## 2 - Activate MFA on your root account

MFA'yi aktif etmeden önce MFA ona bakalım. 

### MFA Nedir?

<img alt="MFA nedir?" src="https://forumlogs.com/uploads/default/original/2X/5/505d7e6411d90f65697cd0238c72a297a955e667.jpg" width="690" height="388">


Çok faktörlü kimlik doğrulama (MFA), bir oturum açma veya başka bir işlem için kullanıcının kimliğini doğrulamak için bağımsız kimlik bilgileri kategorisinden birden fazla kimlik doğrulama yöntemi gerektiren bir güvenlik sistemidir.


----------

Örneğin banka mobil uygulamaları bu yöntemle çalışır. Şifrenizi girmenizin yanında  Böylece sağlam bir güvenlik ortamı sağlanmış olur.

> [Facebook](https://www.facebook.com/notes/facebook-engineering/introducing-login-approvals/10150172618258920/), [google](https://www.google.com/landing/2step/), [twitter](https://support.twitter.com/articles/20171226) gibi sosyal medya hesaplarınızda da MFA'yi aktif ederek güvenliğinizi artırabilirsiniz.

### Amazon MFA Aktif Etme

Başlamadan önce ihtiyacımız bir adet akıllı telefona ihtiyacımız olduğunu ve telefonda internet olması gerektiğini belirtmeliyim.

<img alt="aws secutity status" src="https://forumlogs.com/uploads/default/original/2X/7/7d671f144da515c707b4733a3596f8a5c49565ad.JPG" width="690" height="280">

Manage MFA'ya tıklayalım.

### Manage MFA Device (MFA Cihazını yönet.)

<img alt="aws mfa yönetmek" src="https://forumlogs.com/uploads/default/original/2X/4/489482cd1509e067f4e4f1b0b469b1503b524e4f.JPG" width="615" height="286">

İki seçeneğimiz var. Birinciyi seçeceğiz. Hardware olan bir MFA cihazı alarak bu işlemi yapmak, ona değinmeyeceğim.

<img alt="MFA-compatible application" src="https://forumlogs.com/uploads/default/original/2X/c/cfb3e0bdb4330f48a04e76117e41bb7721f8d2e7.JPG" width="690" height="245">

Next Step Diyebiliriz.

### MFA compatible App' da neyin nesi?

<img src="https://forumlogs.com/uploads/default/original/2X/8/8837f51212c703a4ea75080c5e3b6af5b43f3f9c.JPG" width="690" height="158">

MFA'yı sağlayacak uygulama.

Ben Google Authenticator kullandım. 

[Google Authenticator Android](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2)

[Google Authenticator IOS]( https://itunes.apple.com/us/app/google-authenticator/id388497605?mt=8)

Ayrıntılı bilgi için [Amazon Multi-Factor Authentication](https://aws.amazon.com/iam/details/mfa/) sayfasını ziyaret edebilirsiniz.

Uygulamayı yükledikten sonra iki seçeneğimiz var. Bu seçenekler sizi delirtmiş olabilir ama hayat seçeneklerden ibaret malesef.


<img alt="scan a barcode or enter provided key" src="https://forumlogs.com/uploads/default/original/2X/6/6df18f10b28ff6d47b9760b74fabdcb3d1e871f4.png" width="600" height="368">

* Scan a barcode

* Enter a provided key

Scan a barcode kullanacağım

<img  alt="activate barcode" src="https://forumlogs.com/uploads/default/original/2X/0/0d53aef42139f0092cd6efd0bd947fb35ec1ec5e.jpg" width="572" height="500">

Kamerayı barkod'a doğrultalım, onaylayacaktır.

Daha sonra, uygulamada bize verdiği son iki numarayı ilgili yerlere yazalım ve Activate Virtual MFA diyelim.

<img alt="MFA " src="https://forumlogs.com/uploads/default/original/2X/d/d28ba77623252ccca50e004322e017a4714fd0d9.JPG" width="326" height="208">


Tebrikler! MFA aşarıyla ilişkilendirildi.

<img src="https://forumlogs.com/uploads/default/original/2X/e/e7be278ffd0519b955dfb9b372192d56ae35d386.JPG" width="690" height="204">