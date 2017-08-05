---
title: Root Erişim Anahtarını Silmek
tags:
keywords: 
summary:
sidebar: aws
permalink: root-erisim-hesabini-silmek
folder: aws
layout: page
---


## 1- Delete your root access keys

Amazon, root hesabınız için erişim anahtarı bulundurmamızı öneriyor ve varsayılan olarak erişim anahtarınız yok zaten. Bu yüzden ilk aşamayı geçmiş bulunuyoruz.

<img alt="sen de yalanmışsın dostoyevski" src="https://forumlogs.com/uploads/default/original/2X/3/37ccedab5b87daf05c2c3f83528f2c948da190e6.jpg" width="508" height="500">

### Peki Erişim anahtarı ne işe yarar?

Erişim anatharı, bir erişim anahtarı kimliğinden (örneğin, AKIAIOSFODNN7EXAMPLE) ve bir gizli erişim anahtarından (örneğin, wJalrXUtnFEMI / K7MDENG / bPxRfiCYEXAMPLEKEY) oluşur. **AWS SDK,** **REST** veya **Query** **API'a** yapacağınız programatik isteklere **girişi yapmak için** kullanırsınız.

