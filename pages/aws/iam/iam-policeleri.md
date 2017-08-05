---
title: IAM Poliçeleri
tags:
keywords:
summary: 
sidebar: aws
permalink: iam-policeleri
folder: aws
layout: page
---


## IAM Policies

Aslında daha önce hazır IAM Policy kullanmıştık. Şimdi ise biraz daha derinlere dalacağız. Yeni başlayan birisi için bu konu çok anlam ifade etmeyecektir. Fakat genel bir fikir sahibi olmak şuanlık yapabileceğiniz en iyi şeydir.

## IAM Policies

Bir kullanıcıya, gruba, role veya kaynağa izinler atamak için, izinleri açıkça listeleyen bir belge.

IAM Policies, json formatında yazılmaktadır. Fakat Amazon bize Policy Generator sunara bunu arayüz ile yapmamızı sağlamaktadır. Ayrıca ilk zamanlar hazır poliçeler kullanmak en mantıklısı.

Örnek bir IAM Policy

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource": "*"
        }
    ]
}
```

### Effect :

Ya Allow olur ya da Deny kullanıcıya verilen yetki izin vermek mi yoksa yasaklamak mı onu belirler.Varsayılan değer, kaynakların kullanıcılara verilmemesi olduğundan, genellikle kullanıcıların kaynağa erişmesine izin vereceğinizi belirtmiş olursunuz.

### Action:

Her AWS hizmetinin kendi eylem(action) seti vardır. Hangi eylem setini vereceğini belirleriz. Yukarıdaki örnekte S3 servisinin bütün yetkileri verilmiş. 


### Resource:

Verilen yetkilerde hangi kaynakların kullanımına izin verilecek o belirlenir. Yukarıdaki S3'de bütün kaynaklara erişim izni verilmiş.

### Sid

Sid (Startment  id), policy statement için sağladığınız isteğe bağlı bir tanımlayıcıdır. IAM'de, Sid değeri benzersiz olmalıdır.

### Condition

İsteğe bağlı olan bir alan olmakla birlikte girdinin bir durumla hangi koşulları gerçekleştirse yetki verileceğini belirlemek için kullanılır.

### AM Policies Türleri

AM Policy Türleri, ikiye ayrılmaktadır.

Managed Policy ve Inline Policy

#### Managed Policy 

Managed Policy, yönetibilen poliçeler için verilen isimdir.

Managed Policy  ikiye ayrılmaktadır.

##### Amazon tarafından hazır gelenler 
 Kullanıcıya atadığımız yönetici poliçesi Amazon tarafından hazır gelen. İlk başlarda bunları kullanmak en mantılı seçim olacaktır.
##### Bizim tarafından oluşturulanlar
 Diğer yandan Amazon bize kendi poliçelerimizi oluşturma olanağı da sağlamaktadır. Kendi poliçemizi 3 şekilde oluşturabiliriz. 

**Hazır gelen bir poliçeyi kopyalayıp üzerine bir şeyler ekleyerek.**

<img src="https://forumlogs.com/uploads/default/original/2X/1/129260b0a331c84dae4af351d784814eb55669a8.JPG" width="168" height="291">


Policies açalım



<img src="https://forumlogs.com/uploads/default/original/2X/a/adaadb4d9bfd8f7fc14c79b12d9f5685b0a71088.JPG" width="690" height="256">

Create policy'ye tıklayalım

<img src="https://forumlogs.com/uploads/default/original/2X/5/597660e563442f3f53567113c50672f1dc88c68d.JPG" width="690" height="232">

Cop an AWS Managed Policy seçelim

<img src="https://forumlogs.com/uploads/default/original/2X/c/cdb651c26a4fc0680dcbf67a0d459817b3dd8973.JPG" width="690" height="402">

Bu gelecek karşımıza

Poliçeyi genişletmeye ne dersiniz.
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": "ec2:*",
            "Resource": "*"
        }
    ]
}
```
Policy Name s3andec2fullacess diyebiliriz
Policy Description'da anlamlı bir açıklama yazabilirsiniz.

<img src="https://forumlogs.com/uploads/default/original/2X/0/063a2c22204a4d98646a410e8523d96b6bd305de.JPG" width="690" height="399">

**Validate Policy** tıklayarak, poliçenin uygunluğunu onaylayabilirsiniz.


<img src="https://forumlogs.com/uploads/default/original/2X/1/1599f0a314b9077401065c2ba1e1a7bbe29d5b3c.JPG" width="627" height="96">

Ve poliçemiz başarılı bir şekilde oluşturuldu.

**Amazon Policy Generator** 


Şimdi aynı işlemi Policy Generator ile yapalım

<img src="https://forumlogs.com/uploads/default/original/2X/a/adaadb4d9bfd8f7fc14c79b12d9f5685b0a71088.JPG" width="690" height="256">

Create policy'ye tıklayalım

<img src="https://forumlogs.com/uploads/default/original/2X/5/597660e563442f3f53567113c50672f1dc88c68d.JPG" width="690" height="232">

Policy Generator'ı seçelim

<img src="https://forumlogs.com/uploads/default/original/2X/9/9108abb9d0f0465f79575dedd41c6f64533841c0.JPG" width="690" height="399">

Aws service'te s3 ve ec2 all arayalım. Action all seçelim. Amazon Resource Name * kolalım ve add statment diyerek bunu her iki servis için tekrarlayalım.

Next step'e tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/8/8de76eb7c3e6fb6e497aaed7173237f9322cf1fe.JPG" width="690" height="404">

Burada Poliçe ismini ve açıklmasını yapabiliriz daha sonra poliçeyi oluşturabiliriz.

<img src="https://forumlogs.com/uploads/default/original/2X/0/03297ecb706f5717fca3ffd6281d285a07075d82.JPG" width="582" height="111">

Ve poliçemizi oluşturduk.




**Json olarak**

Son olarak json formatında nasıl oluşturulur ona bakalım.

<img src="https://forumlogs.com/uploads/default/original/2X/a/adaadb4d9bfd8f7fc14c79b12d9f5685b0a71088.JPG" width="690" height="256">

Create policy tıklayalım.

<img src="https://forumlogs.com/uploads/default/original/2X/5/597660e563442f3f53567113c50672f1dc88c68d.JPG" width="690" height="232">


En altıtakini Create your own policy seçelim


<img src="https://forumlogs.com/uploads/default/original/2X/9/9418e4a3a29914cdc005c0eb40b8b68f8996ff68.png" width="690" height="404">

Karşımıza bu gelecek. Şimdi Policy Document kısmına json formatındaki poliçemizi yazabiliriz.


```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1499815829000",
            "Effect": "Allow",
            "Action": [
                "s3:*"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Sid": "Stmt1499815886000",
            "Effect": "Allow",
            "Action": [
                "ec2:*"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
```
Bu json dosyası Policy Generator kodumuz ile aynı bunu kopyalayıp yapıştırıp Json olarak da poliçe oluşturmuş olabilirsiniz.

Json olarak poliçe oluşturmak oldukça ileri seviye bir görevdir. Bu yüzden, en başlarda Policy Generator ile devam edip json dosyasını görüntüleyerek kendinizi bu konuda geliştirebilirsiniz.

İstediğini poliçeye tıklayarak girip daha sonra 
<img src="https://forumlogs.com/uploads/default/original/2X/3/384980ab5e94f41e3205163f18a6994ed9535342.JPG" width="634" height="322">

Edit policy'e tıklayarak bu işlemi gerçekleştirebilirsiniz.

#### In-line Policy


In-line Policy, bir ana varlıkta (bir kullanıcı, grup veya rol) gömülü olan bir politikadır; yani ilke, ana varlığın bir parçasıdır. Ana varlık oluşturduğunuzda ya da daha sonra bir politika oluşturup ana öğeye yerleştirebilirsiniz.

<img src="https://forumlogs.com/uploads/default/original/2X/e/e99b0b0f3d0471c69f3f92693b94eaf0a88eac1f.JPG" width="502" height="405">

In-line Policy, bir politika ile uygulandığı ana varlık arasında sıkı bire bir ilişkiyi korumak isterseniz kullanışlıdır. In-line Policy varlığa özel olduğu için, dışarıda kullanılamaz. 

> Başka bir varlıkta kullanmayı düşünmediğiniz bunu da genel bir poliçe yapmak yerine in-line olarak kullanmak mantıklı bir karar olacaktır.


