# 11 İLERİ SEVİYE VERİ YAPILARI

## 11.1. Sayıların İleri Seviye Özellikleri

Bu bölümde sayı veri tipleri derinlemesine incelenecek, ayrıca sayılarla ilgili bazı fonksiyonlar anlatılacaktır.

**Onluk tabandaki bir sayıyı ikilik tabana çevirme:**

10’luk sistemdeki sayıları 2’lik sistemdeki bir sayıya çevirmek için **bin( )** fonksiyonu kullanılır.
Aşağıdaki örnek kodları etkileşimli kabuk üzerinde çalıştırınız.

```python
bin(5)
>>> '0b101'
```

Buradaki **0b** ifadesi sayının ikilik tabanda olduğunu belirtmektedir. 101 ifadesi ise sağdan itibaren “iki
üzeri sıfır çarpı 1 + iki üzeri bir çarpı 1 + iki üzeri iki çarpı 2 şeklinde tanımlanmaktadır.” Bu işlemin
sonucu (20*1) + (21*0) + (22*1) =5 olarak hesaplanmaktadır.

```python
bin(12)
>>> '0b1100'
```

( 2<sup>0</sup> * 0)+(2<sup>1</sup>*0)+(2<sup>2</sup>*1)+(2<sup>3</sup>*1) = 12

şeklinde hesaplanmıştır.

**Onluk tabandaki bir sayıyı onaltılık tabana çevirme:**

10’luk sayı sistemdeki sayıları 16’lık sistemdeki bir sayıya çevirmek için **hex(  )** fonksiyonu kullanılır

```python
hex(18)
>>> '0x12'
```

Buradaki **0x** ifadesi sayının 16’lık sistemde olduğunu göstermektedir.

```python
hex(18)
>>> '0x12'
```

(16<sup>0</sup>*2)+(16<sup>1</sup>*1) = 2+ 16 = 18
olarak hesaplanır.

##11.2. Sayılar Üzerinde Uygulanabilen Fonksiyonlar

**abs(  ) Fonksiyonu:** İngilizcede ‘mutlak’ anlamına gelen **absolute** adlı bir sözcüğünün kısaltmasıdır.
**abs(  )** fonksiyonu bir sayının mutlak değerini almak için kullanılır. Fonksiyon tek parametre alarak sayının mutlak değerini alır.

```python
abs(-10)
>>> 10

abs(15)
>>> 15

abs(-3.2)
>>> 3.2
```

**round(  ) Fonksiyonu: round(  )** fonksiyonu bir sayıyı belirli kriterlere göre yukarı veya aşağı yuvarlamak için kullanılır.

```python
round(5.7)
>>> 6

round(5.3)
>>> 5

round(5.5)
>>> 6
```

Eğer girilen değerin virgülden sonraki kısmı 5 ve üzerinde bir değerse yukarı, altında bir değerse aşağı
yuvarlama işlemi yapar.

**chr(  ) Fonksiyonu: chr(  )** fonksiyonu, kendisine parametre olarak verilen bir tam sayının karakter
olarak **(ASCII)** karşılığını verir.

```python
chr(65)
>>> 'A'

chr(100)
>>> 'd'
```

**max(  ) Fonksiyonu: max(  )** fonksiyonu, bir dizi içindeki sayıların en büyüğünü verir.

```python
max(3,5,7,8,9)
>>> 9

liste=[3,8,2,6,15]
max(liste)
>>> 15
```

**min(  ) Fonksiyonu: min(  )** fonksiyonu, **max(  )** fonksiyonunun tam tersi işlem yapar.

```python
min(4,7,1,2,9)
>>> 1

liste=[4,7,6,9,3]
min(liste)
>>> 3
```

**pow(  ) Fonksiyonu: pow(  )** fonksiyonu power sözcüğünün kısaltmasında türetilmiştir. Bir sayının üssünü almak için kullanılır. İki adet parametre alır, birinci parametre üssü alınacak sayıyı, ikinci parametre
ise kuvvetini ifade eder.

```python
pow(3,4)
>>> 81

pow(9,0.5)
>>> 3.0
```

**sum(  ) Fonksiyonu: sum(  )** fonksiyonu, dizi içerisindeki değerlerin toplamını bulmamızı sağlar. sum(  )
fonksiyonuna girilen değerler liste ya da tupple türünden olması gerekmektedir.

```python
sum([5,3,8,6])
>>> 22
```

## 11.3. İleri Seviye Karakter Dizileri (String)

**Karakter dizilerinin özel metotları:**

**replace(  ) Fonksiyonu:** replace(  ) fonksiyonu, bir karakter dizisi içindeki karakterleri başka karakterlerle değiştirmeyi sağlar. **replace(  )** fonksiyonu iki adet parametre alır. Birinci parametre değişecek
karakter ya da karakterleri, ikinci parametre ise yerine gelecek karakter ya da karakterleri ifade eder.

```python
a="python"
a.replace("p","P")
>>> 'Python'
```

**split(  ) Fonksiyonu: split(  )** fonksiyonu bir karakter dizisini verilen kurala göre bölme işlemi yapar.
Eğer **split(  )** fonksiyonuna parametre verilmezse boşluk karakterine göre yapar.

```python
a="Milli Eğitim Bakanlığı"
a.split(  )
>>> ['Milli', 'Eğitim', 'Bakanlığı']
```

Ya da belirli kriterlere göre bölme işlemi de yapılabilir.

```python
b="T.B.M.M"
b.split(".")
>>> ['T', 'B', 'M', 'M']
```

**upper(  ) ve lower(  ) fonksiyonları:** Bu fonksiyonlar karakter dizilerini büyük veya küçük harfe
çevirme işlemini yapar

```python
"Merhaba dünya".upper(  )
>>> 'MERHABA DÜNYA'

"Merhaba DÜNYA".lower(  )
>>> 'merhaba dünya'
```

**join(  ) fonksiyonu: split(  )** fonksiyonunun tam tersi işlem yapar. Liste içerisinde bulunan karakter
dizilerini verilen kurala göre birleştirmek için kullanılır.

```python
"-".join(["Merhaba","Dünya"])
>>> 'Merhaba-Dünya'
```

**capitalize fonksiyonu: capitalize(  )** fonksiyonu karakter dizilerinin sadece ilk harfini büyük yapmak
için kullanılır.

```python
a="python programlama dili"
a.capitalize(  )
>>> 'Python programlama dili'
```

**find(  ) fonksiyonu: find(  )** fonksiyonu karakter dizisi içerisindeki bir karakterin konumunu sorgular.
Bulduğu ilk değeri döndürür

```python
a="armağan"
a.find("a")
>>> 0
```

İlk bulduğu indis değerini verir.

**rfind(  ) fonksiyonu: find(  )** fonksiyonun benzeri işlemi yapar ancak arama işlemini sağ taraftan
başlayarak yapar.

```python
a="armağan"
a.rfind("a")
>>> 5
```

**isdigit(  ) fonksiyonu: isdigit(  )** fonksiyonu, karaktere dizisinin bir sayısal değer olup olmadığını kontrol eder. Eğer karakter dizisindeki tüm karakterler rakamdan oluşuyorsa True, değilse False değeri döndürür

```python
metin ="12345"
print(metin.isdigit())
>>> True

metin ="asd123"
print(metin.isdigit())
>>> False
```













