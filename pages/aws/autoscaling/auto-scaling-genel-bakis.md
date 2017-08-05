---
title: Amazon Auto Scaling Genel Bakış
tags:
keywords: 
summary:
sidebar: aws
permalink: amazon-auto-scaling-genel-bakis
---


<img src="https://forumlogs.com/uploads/default/original/2X/6/605525cac8d075569e459ae48cdc4374dbc36c62.png" width="678" height="500">


Amazon Otomatik Ölçekleme (Auto Scaling), uygulama kullanılabilirliğini korumanıza yardımcı olur ve tanımladığınız koşullara göre Amazon EC2 kapasitesini otomatik olarak yukarı veya aşağı ölçeklendirmenize olanak tanır.

Otomatik Ölçeklendirme, hem istikrarlı talep desenleri olan, hem de saatlik, günlük veya haftalık kullanım değişkenliği olan uygulamalar için çok uygundur. 

Örneğin bir haber sitenizin olduğunu düşünün, otomatik ölçeklendirme özelliği olmayan bir sistemde, hep aynı sunucu kaynaklarını kullanırız bu da gereksiz yere maliyet ve bazende trafik yoğunluğudan dolayı kötü hizmet vermemize sebep olur.Diğer yandan Otomatik Ölçeklendirme sayesinde trafiğin yoğunluğu olduğu saatlerde ekstra kaynak sağlayarak bu sorunu ortadan kaldırabiliriz. 

### Amazon Otomatik Ölçeklendirme Sağladığı Avantajlar

* Daha az maliyet
* Otomatik altyapı yönetimi
* Daha iyi kullanıcı deneyimi 


Amazon Auto Scaling, ELB hizmeti ile birleştiğinde.Amazon Web Hizmetlerinin felsefesi olan güvenilir, hataya dayanıklı ve yüksek ulaşılabilirliğe sahip bir hizmet elde etmiş oluruz.


Amazon Otomatik Ölçeklendirme'nin EC2 ötesinde,  Amazon ECS, Amazon EC2 Spot Fleets, Amazon EMR Clusters, AppStream 2.0 fleets, and Amazon DynamoDB gibi AWS hizmetleri kaynaklarını otomatik olarak ölçeklendirmek için   Otomatik Ölçeklendirme Uygulaması kullanabilirsiniz