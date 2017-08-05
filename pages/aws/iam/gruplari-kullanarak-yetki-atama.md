---
title: Grupları Kullanarak Yetki Atama
keywords: 
summary: 
sidebar: aws
permalink: gruplari-kullanarak-yetki-atama
folder: aws
layout: page
---

## 4 - Use groups to assign permissons

Öncelike AIM gruplara bir göz atalım.

###  AIM Groups Nedir?

IAM kullanıcılarının bir koleksiyonudur. Bir kullanıcı koleksiyonu için izinlerin, kullanıcılar için daha kolay yönetilmesini sağlayacak izinleri belirtmek için grupları kullanabilirsiniz.

Örneğin Kullanıcılar mesleklerini ile ilgili teker teker yetkiler vermek yerine grupları oluşturabiliriz. Böylece bu kişileri kolayca gruplara atayabiliriz. 

<img src="https://forumlogs.com/uploads/default/original/2X/5/520886995f39fc01533421f815027c7e7532b267.JPG" width="690" height="275">

Bu bölümde Admins diye bir grup oluşturacağız. Bu gruba yönetici yetkisi vermek istediğimiz kişileri atayabiliriz.

Grup oluşturmak oldukça kolay 

<img src="https://forumlogs.com/uploads/default/original/2X/1/19da211c32d24b7255a4a0286695a75d3ef190fb.JPG" width="690" height="268">

Create New Group'a tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/6/67f1a96a16ebf59586e8ed090796bb30680a57b4.JPG" width="690" height="307">

Grup İsmini belirleyelim.

<img src="https://forumlogs.com/uploads/default/original/2X/a/ae4035ee56ea95063761987f9143c5eef6890c4b.JPG" width="690" height="360">

Yetki Poliçesi ile ilişkilendirelim.

<img src="https://forumlogs.com/uploads/default/original/2X/d/d1683aa135246006ca3dde2b98b740826e01ad58.JPG" width="690" height="324">

Create group diyerek grubumuzu oluşturalım.

Grubumuzu kişi atamaksa çok kolay.

IAM resorces'tan grup sayasına gelelim.

<img src="https://forumlogs.com/uploads/default/original/2X/8/8710beea6a484a4e812130855b0257cf48139a63.JPG" width="559" height="204">

Add Usuers to gruop'a tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/a/a05ea3b0020593c4348d053c6dfb12b90c46ae5b.JPG" width="496" height="214">

Grup için kullanıcı seçelim.

Add Users tıklayalım ve hepsi bu kadar.