---
title: AWS IAM
tags:
keywords:
summary: 
sidebar: aws
permalink: aws-iam
folder: aws
layout: page
---

## AWS IAM Nedir?

AWS  Identity and Access Management (IAM)  - Kimlik ve Erişim Yönetimi, kullanıcılarınız için AWS kaynaklara erişimi güvenli bir şekilde kontrol etmenize yardımcı olan bir web hizmetidir. 

## Ne İşe Yarar?

AWS kaynaklarınızı kimin kullanabileceğini (kimlik doğrulama) ve hangi kaynakları kullanabileceklerini (yetkilendirme)  ve hangi yolla kontrol etmek için IAM kullanırız.

Açıkcası Amazon'a üye olduktan sonra giriş yapma işlemini IAM servisi üzerinden sağlarız. Güvenlik açısından bakıldığında  IAM bilimesi en temel şeylerin başında gelir.

IAM olmadan güvenlik kontrolünün sağlanması mükmün değildir.

IAM sağladığı bileşenler sayesinde ile patronun kim olduğuna karar verirsiniz.


<img src="https://forumlogs.com/uploads/default/original/2X/e/e208eca328f807b9f01c32e8c0478cba016a3033.gif" width="480" height="324">

## Özetle 

* Erişim Kontrolü => Şifre, Multi Factor Access (MFA), Federal Access 

* Yetkilendirme =>  EC2'ye Full Erişim, RDS Sadece Okuma, S3 Sadece Bucket Oluşturma gibi.

## Diğer Platformlarda Benzer Servisler

* [Microsoft Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-whatis)

* [Oracle Identity Management](https://www.oracle.com/middleware/identity-management/index.html)

* [IBM Cloud Identity Service](https://www.ibm.com/security/cloud/cloud-identity-service/)

## Amazon IAM İle İlgili Bilinmesi Zorunlu Kavramlar


<img src="https://forumlogs.com/uploads/default/original/2X/a/abecd8e12f6fcc141c3ddca6957a2cee069b80bc.jpg" width="690" height="494">


*  Erişim Kontrol Mekanizması (Access Control Mecanism)

* Kullanıcılar (Users)

* Gruplar (Groups)

* Roller (Roles)

* Permissions (Yetkiler)