---
title: Amazon EC2 Fiyatlandırma
keywords: 
summary:
sidebar: aws
permalink: amazon-ec2-fiyatlandirma
folder: aws
---


## Amazon EC2 Fiyatlandırma

Amazon'da fiyatlandırma 4 Bölümde incelenebilir

* On-Demand (Talep Üzerine)
* Spot Instances
* Reserved Instances
* Dedicated Hosts

### On-Demand  (Talep Üzerine)

Talep üzerine oluşturduğunuz örneklerle, hesaplama kapasitesini, uzun vadeli taahhütler veya ön ödemeler olmaksızın saat başına ödersiniz. Hesaplama kapasitenizi, uygulamanızın taleplerine bağlı olarak artırabilir veya azaltabilir ve yalnızca kullandığınız örnekler için belirtilen saatlik ücreti ödeyebilirsiniz.

On-Demand örnekleri aşağıdakiler için önerilir:

* Amazon EC2'nin düşük maliyet ve esnekliğini herhangi bir ön ödeme veya uzun vadeli taahhüt etmeden tercih eden kullanıcılar
* Amazon EC2'de ilk kez geliştirilen veya test edilen uygulamalar

Fiyatlara bakmak için


[https://aws.amazon.com/ec2/pricing/on-demand/](https://aws.amazon.com/ec2/pricing/on-demand/)



### Spot Instances

Amazon EC2 Spot örnekleri, On-Demand fiyatından % 90'a varan oranda düşük fiyata EC2 örneklerini kullanmanıza olanak tanır.

Spot örnekleri aşağıdakiler için önerilir:

* Esnek başlangıç ve bitiş saatleri olan uygulamalar
* Yalnızca çok düşük hesaplama fiyatlarında uygulanabilir uygulamalar
* Büyük miktarda ek kapasite için acil hesaplama ihtiyacı olan kullanıcılar

Fiyatlara bakmak için


[https://aws.amazon.com/ec2/spot/pricing/](https://aws.amazon.com/ec2/spot/pricing/)


### Reserved Instances (Rezerve Edilmiş Örnekler)


Rezerve Edilmiş Örnekler, İsteğe Bağlı Örnek Fiyatlandırma ile karşılaştırıldığında önemli bir indirim (% 75'e kadar) sağlar. Buna ek olarak, Rezerve Edilmiş Örnekler belirli bir Kullanılabilirlik Bölgesine atandığında, onlara ihtiyacınız olduğunda örnekleri başlatma konusunda size ek bir güven veren bir kapasite rezervasyonu sağlarlar.

Ayrılmış Örnekler aşağıdakiler için önerilir:
* Kararlı hal kullanımı olan uygulamalar
* Ayrılmış kapasite gerektirebilecek uygulamalar
* Toplam bilgisayar giderlerini azaltmak için 1 veya 3 yıl içinde EC2'yi kullanmaya karar verebilen müşteriler

Fiyatlara bakmak için


[https://aws.amazon.com/ec2/pricing/reserved-instances/pricing/](https://aws.amazon.com/ec2/pricing/reserved-instances/pricing/)


### Dedicated Hosts

Dedicated Hosts, kullanmanız için ayrılmış fiziksel bir EC2 sunucusudur. Dedicated Hosts, Windows Server, SQL Server ve SUSE Linux Enterprise Server da dahil olmak üzere sunucuya bağlı mevcut yazılım lisanslarınızı kullanmanıza izin vererek maliyetleri azaltmanıza yardımcı olabilir.

* İsteğe bağlı olarak satın alınabilir (saatlik).
* İsteğe bağlı fiyata% 70'e kadar indirim imkanından yararlanmak için rezerve edilip alınabilir.

Fiyatlara bakmak için

[https://aws.amazon.com/ec2/dedicated-hosts/pricing/](https://aws.amazon.com/ec2/dedicated-hosts/pricing/)