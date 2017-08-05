---
title: Ev Ağı Benzetimesi
keywords: 
summary:
sidebar: aws
permalink: ev-agi-benzetmesi
folder: aws
layout: page
---


## Ev Ağı Benzetmesi

<img src="https://forumlogs.com/uploads/default/original/2X/4/4cdd6dcd8507190b3a8d9ab57331924bf2c512e0.png" width="423" height="500">


###### Bu örneklemedeyi, [Linux Academy AWS Essentials: VPC Basics](https://www.youtube.com/watch?v=7XnpdZF_COA&index=14&list=PLv2a_5pNAko0Mijc6mnv04xeOut443Wnk) videosundan esinlenerek yaptım

Evden internete bağlanmak için gerekli olan şeylere baktığımızda 

### İnternet Servis Sağlayıcısı ISP 
İnternet Servisini aldığımız kurum kuruluş. 

Örneğin: Turktelekom, Turkcell, Vodafone, Turknet (Favorim). Bu VPC'de de aynı sonuç olarak internet.

### Modem

Modem, internet sağlayıcısından gelen sinyalleri karşıladığımız yer. Bu VPC'de İnternet Gateway olarak geçiyor yani İnternet geçidi.

### Router (Yönlendirici)
Genellikle günümüzde router modemin içinde olur yani yönlendirme durumu modem tarafından halledilir. Fakat router kullanan ev ağları da olabilir. 

Router özetle yönlendirmeyi yapar. VPC'de karşımıza route table olarak çıkmaktadır.

### Firewall (Güvenlik Duvarı)

Güvenlik duvarı veya ateş duvarı, bir kural kümesi temelinde ağa gelen giden paket trafiğini kontrol eden donanım tabanlı ağ güvenliği sistemidir. Birçok farklı filtreleme özelliği ile bilgisayar ve ağın gelen ve giden paketler olmak üzere İnternet trafiğini kontrol altında tutar. İP filtreleme, port filtreleme, Web filtreleme, içerik filtreleme bunlardan birkaçıdır.

<img src="https://forumlogs.com/uploads/default/original/2X/2/29f4bd6b5f228074b0a3f6839bba7ed82b75a76b.JPG" width="690" height="159">
#####  <center> Örnek bir güvenlik duvarı ayarı paneli </center>

Güvenlik duvarına modem ayarlarından girebilirsiniz. Güvenlik duvarı gelen trafikle ilgilidir.

VPC'deki güvenlik duvarı A network access control list (NACL) - Ağ erişim kontrol listesi olarak adlandırılır. Görevi güvenlik duvarına benzemektedir.

### Bilgisayar, Laptop veya Akıllı Telefon

Ev ağındaki son nokta Bilgisayar yani Müşteri (Client). 

VPC'de burada Amazon servisleri yer almaktadır. 

Şuana kadar bildiğimiz servisler EC2, S3 veya RDS (İlişkisel Veritabanı Hizmeti) sunucusu gibi.
## Ev Ağından VPC'ye Geçiş.

<img alt="vpc" src="https://forumlogs.com/uploads/default/original/2X/e/e5578c61f2757372e66b08c2b7cb9c876f7eaf9e.png" width="423" height="500">

VPC tasarımı ise karşımıza böyle çıkmaktadır.

### Internet Gateway (IGW)  - İnternet Geçidi

Bir İnternet geçidi, yatay olarak ölçeklendirilmiş, yedekli ve VPC ve Internet'inizdeki örnekler arasında iletişim kurmaya imkan tanıyan yüksek oranda erişilebilir bir VPC bileşenidir. Bu nedenle, ağ trafiğinizde kullanılabilirlik riskleri veya bant genişliği kısıtlamaları uygulanmaz.

Mantığını kavramak çok kolay İnternet Geçidi yoksa internet oluşturulan ağa internet girmez tıpkı modem olmayan evde internet olmayacağı gibi. 


### Route Table (RT) - Yönlendirici Tablosu

Yönlendirici tablosu, ağ trafiğinin yönlendirileceği yeri belirlemek için kullanılan ve rota adı verilen bir dizi kural içerir.

VPC'nizdeki her alt ağ bir rota tablosuyla ilişkilendirilmelidir; Tablo alt ağın yönünü kontrol eder. Bir alt ağ yalnızca aynı anda yalnızca bir rota tablosuyla ilişkilendirilebilir, ancak aynı rota tablosuyla birden fazla alt ağı ilişkilendirebilirsiniz.

### Network Access Control List Networks (NACL) - Ağ erişim kontrol listesi 

Ağ erişim kontrol listesi (ACL), VPC'niz için isteğe bağlı bir güvenlik katmanıdır ve bu güvenlik duvarı, bir veya daha fazla alt ağdaki ve dışındaki trafiği kontrol etmek için bir güvenlik duvarı görevi görür. VPC'ye ek bir güvenlik katmanı eklemek için güvenlik gruplarına benzer kurallarla ağ ACL'leri kurabilirsiniz.

AWS'de çoğu durumda, NACL kullanmak yerine Güvenlik Grubu özelliğini kullanarak ihtiyacımızı karşılayabiliriz.

### Security Group (Güvenlik Grubu)

Güvenlik grubu, EC2 Sunucunuzun gelen ve giden trafiğini kontrol etmesi için sanal bir güvenlik duvarı görevi görür. VPC'de bir sunucu başlattığınızda, sunucuya beş güvenlik grubunu atayabilirsiniz. Güvenlik grupları, alt ağ olarak değil, sunucu düzeyinde hareket eder. Bu nedenle, VPC'nizdeki bir alt ağdaki her sunucuya farklı bir güvenlik grubu grubuna atayabilirsiniz. 

Başlatma zamanında belirli bir grubu belirtmezseniz, örnek otomatik olarak VPC için varsayılan güvenlik grubuna atanır.

#### AWS Security Group ile NACL Arasında Fark nedir?

Security Group, sunucu yani; Amazon deyimiyle instance (örnek) bazlı güvenlik duvarı sağlarken. NACL ise alt ağ bazlı güvenlik duvarı sağlar. 


### Subnets (Subnetworks) - Alt Ağlar

Alt ağ (Subnet), bir IP ağının mantıksal alt bölümüdür. Bir ağın iki veya daha fazla ağa bölünmesi uygulaması alt ağ oluşturma olarak adlandırılır. 

> Subnet, Bilgisayar Ağ terimlerinden bir tanesidir.

#### Neden Alt Ağlar Oluşturuyoruz ki?

* Alt ağlar bize esneklik kazandırır. 
* Alt Ağlar Ağın izole edilmesini sağlar.Böylece Ağdaki problemlerin tespit edilmesi daha kolay ve anlaşılır olmaktadır. 
* Güvenlik sağlar

Örneğin iki tane alt ağımız olsun bu ağlardan birinde WordPress barındıralım diğerinde ise Mysql'i. Mysql'in  İnternet İnternet ile işi yok bu yüzden buna İnternet geçidi vermeyiz. Bu veritabanı için alt ağ olurken diğer yandan; WordPress uygulaması için oluşturduğumuz alt ağ İnternet Geçidi sayesinde internete bağlanırız.

Eğer alt ağın internete erişimi varsa **Public Subnet (**Genel Alt Ağ), yoksa **Private Subnet** (Özel Alt Ağ) demekteyiz.

### Availabilities - Erişilebilirlik

Diğer bir konu ise erişebilirlik. Amazon Veri Merkezleri Dünya'nın bir çok yerinde bulunmaktadır. Bu oluşturacağımız servislerin Erişilebilirlik bölgesine göre tasarlamamıza olanak sağlar. 

Ev örneğine geri dönecek olursak. Şimd büyük bir eve sahip olduğunuzu düşünün. İnternetten verimlik yararlanmak için internete her yerden aynı kalitede bağlanmak için acess point erişim noktaları kullanırız işte Amazon'un bize tanıdığı hizmetlerden birisi de buna benzer.