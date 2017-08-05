---
title: Amazon SNS Genel Bakış
tags:
keywords: 
summary:
sidebar: aws
permalink: amazon-elb-genel-bakis
---


<img src="https://forumlogs.com/uploads/default/original/2X/6/6ac38945142af90aea0afbeff883dedfea8bbe1f.png" width="516" height="500">

Amazon ELB açılımı; Elastic Load Balancing, gelen trafiği Amazon AWS altyapınıza birden çok instance'a dağıtmanıza olanak tanır. 

Bu, uygulamalarınızdaki ve web trafiğinizdeki başarısızlıklardan kaçınmada mükemmel bir araçtır. ELB, EC2 instance'lardaki başarısızlıkları otomatik olarak algılar ve trafiği diğer mevcut örneklere yönlendirir.

## ELB Türleri

* Classic Elastic Load Balancer 
* App Load Balancer

### Classic Elastic Load Balancer 

AWS Classic Load Balancer (CLB), OSI modelinin Katman 4'ünde çalışır. Bu şu demektir, yük dengeleyici, istemciler ve arka uç sunucuları arasındaki trafiği IP adresine ve TCP bağlantı noktasına dayalı olarak yönlendirmesidir.

<img src="https://forumlogs.com/uploads/default/original/2X/c/c8151688aec865abb98ea60ff58c00cc7e930636.png" width="666" height="500">


### App Load Balancer
AWS Application Load Balancer, (ALB), OSI modelinin 7. Katmanında çalışır. Katman 7'de ELB, IP ve portu değil, uygulama düzeyindeki içeriği inceleme olanağına sahiptir. Bu, Classic Elastic Load Balancer'den daha karmaşık kurallara dayalı olarak yönlendirilmesini sağlar.

Yani, ELB Örneğin 80 port'a bakarak dengeleme sağlarken. ALB yanlıza port'a değil aynı zamanda url'ye de bakar.

ELB  Network Açısından İkiye ayrılır.

 * External load balancer
 * Internal load balancer

Extarnal ile genel (public) olan bir servisinizde dengeleme sağlarken, Internal ile özel private servisinizde dengeleme sağlarsınız. 
## WordPress Haber Sitesi
Örneğin WordPress ile bir haber sitesi kurdunuz. 

WordPress uygulamanız Ngnix Web Sunucusu üzerinden 443 Port'undan genel ağ olarak hizmet veriyor. 

Bu,  **External load balancer**

Diğer yandan Mysql Veri Tabanı servisiniz özel ağ olarak hizmet veriyor.

Bu ise, **Internal load balancer**



##  Auto Scaling

ELB'den bahsederken Auto Scaling'den bahsetmezsek olmaz

<img src="https://forumlogs.com/uploads/default/original/2X/6/605525cac8d075569e459ae48cdc4374dbc36c62.png" width="678" height="500">

Auto Scaling, uygulamanız  Amazon EC2 instance'ların doğru sayıda sahip olmasını sağlar.