---
title: Amazon Route53 Yönlendirme İlkeleri
tags:
keywords: 
summary:
sidebar: aws
permalink: amazon-route53-yonlendirme-ilkeleri
---



## Yönlendirme İlkeleri (Routing Policy)
Amazon Route53'ün bize sağladığı en önemli özelliklerden birisi bize sunduğu yönlendirme ilkeleridir.

Bir kaynak kayıt grubu oluşturduğunuzda, Amazon Route 53'ün sorgulara nasıl tepki vereceğini belirleyen bir yönlendirme ilkesi seçeriz:

* **Basit yönlendirme ilkesi (Simple routing policy)** - etki alanınız için belirli bir işlevi yerine getiren tek bir kaynak için kullanmak istediğimizde (örneğin, example.com web sitesi için içerik sunan bir web sunucusu).

* **Yük devretme yönlendirme ilkesi (Failover routing policy)** - Etkin ve pasif devre dışı bırakmayı yapılandırmak istediğimizde kullanırız.

* **Coğrafi Konum Yönlendirme ilkesi (Geolocation routing policy)** - Trafiği kullanıcılarınızın bulunduğu yere göre yönlendirmek istediğinizde kullanırız.

* **Gecikme yönlendirme ilkesi (Latency routing policy)** - Birden fazla lokasyonda kaynağa sahip olduğunuzda ve en iyi gecikmeyi sağlayan kaynağa trafik yönlendirmek istediğimizde kullanırız.

* **Çok değerli yanıt yönlendirme ilkesi (Multivalue answer routing policy)** - Amazon Route 53'ün rastgele seçilen en fazla sekiz sağlıklı kayıt içeren DNS sorgularına yanıt vermesini istediğimizde kullanırız.

* **Ağırlıklı yönlendirme ilkesi (Weighted routing policy)** - Trafiği, belirttiğiniz oranlarda birden çok kaynağa yönlendirmek için kullanırız.