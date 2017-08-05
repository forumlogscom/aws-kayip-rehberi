---
title: S3 Depolama Sınıfları
keywords: 
summary:
sidebar: aws
permalink: s3-depolama-siniflari
folder: aws
layout: page
---


## Amazon S3 Storage Classes (Depolama Sınıfları)

Amazon S3 farklı kullanım durumları için tasarlanmış bir dizi depolama sınıfı sunar. Bunlara sık erişilen verile için **Amazon S3 Standard Genel Amaç Depolama**, **Amazon S3 Standard - Sık Olmayan Erişim**, daha az sıklıkla erişilen veriler için ve **Amazon Glacier** ile uzun vadeli arşivler bulunur.

Yani Amazon Depolama Sınıfları 3'e Ayrılmaktadır.

* Amazon S3 Standart - General Purpose (Genel Amaçlı)
* Amazon S3 Standard - Infrequent Access (Sık Olmayan Erişim)
* Amazon Glacier - Archive (Arşiv)


### Amazon S3 Standart - General Purpose (Genel Amaçlı)

Amazon S3 Standard, sık erişilen veriler için yüksek dayanıklılık, kullanılabilirlik ve performans nesnesi saklama alanı sunar.Düşük gecikme süresi ve yüksek verimlilik sağlayan **Standart**; bulut uygulamaları, dinamik web siteleri, içerik dağıtımı, mobil ve oyun uygulamaları ve büyük veri analizi dahil olmak üzere çok çeşitli kullanım kutuları için idealdir. 

#### Temel Özellikler:

* Düşük gecikme süresi ve yüksek verim performansı
* Nesnelerin % 99.999999.999'unun (11 tane 9) dayanıklılığı için tasarlandı 
* Yılda % 99.99 kullanılabilirlik - çalışma süresi için tasarlanmıştır
* Kullanılabilirlik için Amazon S3 Hizmet Seviyesi Sözleşmesi ile desteklendi.
* Transit ve geri kalan verilerin SSL şifrelemesini destekler.
* Nesnelerin otomatik olarak taşınması için yaşam döngüsü yönetimi

### Amazon S3 Standard - Infrequent Access  Sık Olmayan Erişim 

Amazon S3 Standard - Sık Olmayan Erişim  (Standart - IA), daha az erişilen, ancak ihtiyaç duyulduğunda hızlı erişim gerektiren veriler için Amazon S3 depolama sınıfıdır.Standart - IA, düşük GB depolama fiyatı ve GB alım ücreti ile, Amazon S3 Standard'ın yüksek dayanıklılığı, iş hacmi ve düşük gecikme süresi sunar.Düşük maliyetli ve yüksek performansın birleşimi, Standard - IA'yı, uzun vadeli depolama, yedekleme ve felaket kurtarma için bir veri deposu için ideal kılar. Standart - IA depolama sınıfı, nesne düzeyinde ayarlanır ve standart olarak aynı kovanda bulunabilir; bu, yaşam döngüsü ilkelerini herhangi bir uygulama değişikliği olmaksızın depolama sınıfları arasında otomatik olarak geçiş yapmak için kullanmanıza olanak tanır.


#### Temel Özellikler:

* Standardın ile aynı düşük gecikme süresi ve yüksek verim performansı
* Nesnelerin% 99.999999.999'unun dayanıklılığı için tasarlanmıştır.
* Yılda % 99.99 kullanılabilirlik - çalışma süresi için tasarlanmıştır
* Kullanılabilirlik için Amazon S3 Hizmet Seviyesi Anlaşması ile desteklendi
* Transit ve geri kalan verilerin SSL şifrelemesini destekler
* Nesnelerin otomatik olarak taşınması için yaşam döngüsü yönetimi

### Amazon Glacier - Archive (Arşiv)

Amazon Glacier, veri arşivleme için güvenli, dayanıklı ve son derece düşük maliyetli bir depolama hizmetidir. Herhangi bir miktarı, kurum içi çözümlerle rekabet eden ya da daha ucuz maliyetlerle güvenilir şekilde depolayabilirsiniz. Maliyeti düşük tutmak için, alım ihtiyaçlarını değiştirmek için uygun olan Amazon Glacier, arşivlere birkaç dakika ila birkaç saat arasında erişmek için üç seçenek sunmaktadır. Amazon Glacier, depolama sınıfları arasında otomatik geçiş için yaşam döngüsü politikalarını destekler.


* Nesnelerin% 99.999999.999'unun dayanıklılığı için tasarlandı
* Transit ve geri kalan verilerin SSL şifrelemesini destekler
* Apps Kasası Kilidi özelliği sayesinden kilitlenebilir politika ile uygundur.
* Son derece düşük maliyetli tasarım, uzun vadeli arşiv için idealdir.
* Nesnelerin otomatik olarak taşınması için yaşam döngüsü yönetimi


<br>

<table> 
   <tr>
            <td >&nbsp;</td> 
             <td ><b>Standard<br> </b></td> 
             <td><b>Standard - IA<br> </b></td> 
             <td ><b>Amazon Glacier<br> </b></td> 
            </tr> 
            <tr> 
             <td>Dayanıklılık için tasarlandı<br> </td> 
             <td>99.999999999%</td> 
             <td>99.999999999%</td> 
             <td>99.999999999%</td> 
            </tr> 
            <tr> 
             <td >Kullanılabilirlik için tasarlandı </td> 
             <td>99.99%<br> </td> 
             <td >99.9%</td> 
             <td >N/A<br> </td> 
            </tr> 
            <tr> 
             <td>Kullanılabilirlik HDA****<br> </td> 
             <td >99.9%</td> 
             <td >99%</td> 
             <td >N/A</td> 
            </tr> 
            <tr> 
             <td>En Düşük Nesne Boyutu</td> 
             <td >N/A</td> 
             <td >128KB*</td> 
             <td >N/A</td> 
            </tr> 
            <tr> 
             <td >En Düşük Depolama Süresi</td> 
             <td >N/A</td> 
             <td >30 gün</td> 
             <td >90 gün</td> 
            </tr> 
            <tr> 
             <td >Geri Alma Ücreti</td> 
             <td >N/A</td> 
             <td >Alınan GB başına</td> 
             <td >Alınan GB başına**</td> 
            </tr> 
            <tr> 
             <td >İlk Bit Geçikme Süresi</td> 
             <td >milisaniye</td> 
             <td>milisaniye</td> 
             <td >seçilen dakika ve saat içinde***</td> 
            </tr> 
            <tr> 
             <td >Depolama Sınıfı<br> </td> 
             <td style="text-align: center;">nesne düzeyinde</td> 
             <td style="text-align: center;">nesne düzeyinde</td> 
              <td style="text-align: center;">nesne düzeyinde</td> 
            </tr> 
            <tr> 
             <td>Yaşam Döngüsü Geçişleri</td> 
             <td >evet</td> 
             <td>evet</td> 
             <td >evet</td> 
             </tr>
</table>



'* Standart - IA'nın minimum nesne boyutu 128KB'dir. 128KB depolama alanından daha küçük nesneler için 128KB olarak ücretlendirilir.

** Amazon Glacier, verilerinize ulaşmanız için önceden saat veya dakika bazında ayarlama yapmanıza olanak sağlar.

*** HDA (SLA) - Hizmet düzeyi anlaşması (Service Level Agreement)

***