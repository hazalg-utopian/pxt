
# Öğreticiler

Öğreticiler adım adım "Başlarken" öğreticisi gibi markdownda yazılmış ve metin düzenleyicisi tarafından otomatik şekilde dönüştürülmüştür. Bu sayfa bu öğreticiler için biçimi tanımlar.


## Öğreticiler nasıl çalışır

Öğreticiler blok kullanımını ve bir hedefi görüntülemeye yardımcı olur. Öğreticiler **Öğreticiler** altındaki **Projeler** penceresinden seçilir. Buradan bir öğretici seçildiği zaman metin düzenleyici içindeki bir kullanıcı etkileşimi olarak yürütülür. Öğretici bir markdown belgesinde yazılmış bir sıra adımdan geçerek ilerler.


Öğreticinin her basamağının adım ve muhtemel bir öbek örneği için faaliyetin kısa bir tasviri ya da açıklaması vardır. Eğer adım bir öbek örneği içeriyorsa metin düzenleyicisi, yalnızca örnekte kullanılan araç kutusundaki blokların seçilimini bloklarla kısıtlayacaktır. Diğer bloklar yine de gösterilir fakat adım sırasında seçimler devre dışı bırakılır. Bu, etkileşimin sadece tanımlanan bloklara odaklanmasına yardımcı olur ve adımın doğru şekilde tamamlanmasını kesinleştirir.


## Öğretici belgeleri

Öğreticiler hedef belge ağacında dokümanlar olarak _/docs/tutorials_ dosyası altında oluşturulmuştur. '**Light blaster**' başlığıyla birlikte bir öğreticinin şunun gibi bir yolu olurdu: _/docs/tutorials/light-blaster.md_.


Metin düzenleyicide bir öğretici seçildiği zaman öğretici çark, öğretici markdownun içeriğini kullanıcı etkileşimlerine dönüştürür. Eğer yardım menüsünden seçilirse bir öğretici herhangi bir yardım belgelesi ile aynı görüntülenir.


### ~ ipucu


**Gerçek bir örnek**

Örnekler ile öğrenmek mi? Gerçek öğreticinin kaynağına bakın: [**getting-started.md**](https://github.com/Microsoft/pxt-microbit/blob/master/docs/tutorials/getting-started.md)

### ~

### 'Başlarken' öğreticisi 

'Başlarken' öğreticisi metin düzenleyicinin **BLOKLAR** görünümünde gösterilen **Başlarken** tuşuyla bağlantılı özel bir öğreticidir. Bu öğretici metin düzenleyicide blokları kullanmak üzere basit bir ilk sefer girişi vermek için yazılır.

Eğer düzenleyicide **Başlarken** tuşu (enabled in [pxtarget.json](/targets/pxtarget) ```"sideDoc": "tutorials/getting-started"```) ile etkinleştirilmişse öğretici bağlantısı _/docs/tutorials/getting-started.md_ adresinden alınır.

### Öğreticileri ekleme

'Başlarken'in dışında başka öğreticiler yaratabilirsiniz. Diğer öğretici tercihleri,  _/docs/tutorials.md_. dosyasındaki bir girişi kullanarak öğreticiler penceresinde gösterilir.

* **name**: öğretici adı

* **imageUrl**: isteğe bağlı bir ikon görünümü

* **url** öğretici belge izi

* **cardType**: "öğretici"ye ayarla

* **description**: öğreticinin ne yaptığının tanımı


İşte _tutorials.md_ dosyasındaki bir örnek giriş:

````markdown

# Öğreticiler

## Eğlence kısmı



```codecard
[{
    "name": "Light Blaster",
    "imageUrl":"/static/tutorials/light-blast.png",
    "url": "/tutorials/light-blaster",
    "cardType": "tutorial",
    "description": "Flash all the lights on the pixel strip!"
},{
    // another tutorial...
}]
```
````

Öğretici belge ağacının bu anahat düzeni vardır:

```
/docs/tutorials.md
/docs/tutorials/getting-started.md
/docs/tutorials/light-blaster.md
...
```
## Biçim

Öğretici markdownun öğretici çarkının bir seri etkileşim oluşturmasına yön veren bir biçimi vardır:

### Başlık

Birinci satırdaki başlık ve aşağıdaki gibi bir _level 1_ başlık kullanıyor:

```text
# Light blaster
```

### Adımlar

Bir öğretici basit adımların bir dizisini takip eder. Çark, her bir _step_ bölümünden bir etkileşim kurar. Bir adım bir _level 2_ başlık (``##``) ile başlar ve herhangi bir metin içerebilir. Yine de,her başlık için _Step 1, Step 2,...Step n_ dizisi kullanmak yaygındır. Bunun gibi:

```markdown
## 1. Adım

1. adım için talimatlar burada...

## 2. Adım

2. adım için talimatlar burada...

## 3. Adım

3. adım için talimatlar burada...
```

Başlıktaki metin sadece öğretici yardım sayfası olarak görüntülendiğinde gösterilir. Başlıkta ek metin olmasında sorun yok. Öğretici çarkı sadece başlık etiketi altındaki içerikten adımlar listesini oluşturacağından 'Adım' kelimesi bile dışarıda bırakılabilir ``##``. Bunlar geçerli başlıklar:



```markdown
### 3. Adım: Yeni bir değişken oluşturun
```

>--or--

```markdown
## Tüm LEDleri iki kere açıp kapat
```

Metin düzenleyici otomatik biçimde markdownu çözümler ve her adım bölümünden kullanıcı arayüzünü doldurur.

Her adımda öğretici başlığında yalnızca ilk paragraf kullanıcıya görüntülenir. Kullanıcı başlık ya da ipucu tuşuna tıkladığı zaman tam metin,öbek örnekleri,vb. ``hint`` penceresinde gösterilir. Eğer kod parçalarını,görselleri ya da videoları eklerseniz ipucu görünümünde de gösterilirler.


### ~ ipucu

**Basit, kısa tanımlar**

Bir etkileşim esnasında adım tanımının ilk paragrafı başlığın içinde sergilenir. Eğer paragraf uzunluğu resim yazısı uzunluğununun gösterimini aşarsa paragrafın kalanını görüntülemek için bir kaydırma çubuğu belirir. En iyisi paragrafı yeteri kadar kısa tutmaktır ki böylece tamamı kullanıcının hepsini görüntülemek için kaydırmasını gerektirmeden başlıkta görünür. Talimatlarınız daha fazla metin gerektirirse faaliyeti bölmek için sadece ek bir adım yaratabilirsiniz.




### ~

### Tam ekran

Eğer dramatik bir tanıtım eklemek isterseniz ya da özel bir mesajın görüldüğünü kesinleştirirseniz ``@ fullscreen`` etiketini kullanabilirsiniz. Bu genellikle öğretici belgenin ilk ksımına yerleştirilir. Bölüm, öğretici ekranın üstündeki bir yardımcı pencerede görüntülenir ve öğretici akışının parçası olarak simge yazısının içinde gösterilmez. Öğreticinizin kapsamına şu şekilde alırsınız:

```markdown
# Flash-a-rama

## Kodlama zamanı! @fullscreen

Gerçekten parlak olalım. Devre kartınızdaki tüm ışıkları yanıp söndüreceğiz!

![Flash lights](/static/tutorials/lights-flashing.gif)


## 1. Adım: Yeni bir değişken oluşturun
...
```


## Örnek


Takip eden örnek basit bir 2 adımlı öğreticiyi gösterir.

````markdown

# Başlarken

## 1. Adım


Hoşgeldiniz! Adınızı kaydırmak için ``||basic: on start||`` sırasındaki `` ||basic: show string||`` öbeğini yerleştirin.

```blocks
basic.showString("Micro!")
```

## Step 2
## 2. Adım


@ boardname@ adresinizdeki kodunuzu aktarmak için ``|Download|`` tıklayın.
````

## Çeviriler

Öğreticiler [Crowdin] (/translate) yoluyla herhangi diğer belge sayfaları gibi tercüme edilir.
