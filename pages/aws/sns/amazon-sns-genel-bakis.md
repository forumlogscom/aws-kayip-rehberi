---
title: Amazon SNS Genel Bakış
tags:
keywords: 
summary:
sidebar: aws
permalink: amazon-sns-genel-bakis
---


<img src="https://forumlogs.com/uploads/default/original/2X/c/c70c02617ae8b07d1f57b1daa136d14e8bb3f95d.png" width="544" height="363">

Amazon Basit Bildirim Hizmeti (SNS), abone olan uç noktalara veya istemcilere mesajların gönderilmesini veya gönderilmesini koordine eden ve yöneten bir web servisidir. 

Amazon SNS'de, üreticiler ve tüketiciler olarak da bilinen iki tür müşteri (yayıncı ve abone) vardır. 

### Yayıncılar

Yayıncılar, bir konuyu mantıksal bir erişim noktası ve iletişim kanalı olan bir mesaj üretip göndermek suretiyle abonelerle iletişim kurar. 

### Aboneler
Aboneler, (yani, web sunucuları, e-posta adresleri, Amazon SQS kuyrukları, AWS Lambda işlevleri) desteklenen protokollerden (Amazon SQS, HTTP / S, e-posta, SMS, Lambda) biri üzerinden abone oldukları konu için mesaj veya bildirim alırlar.