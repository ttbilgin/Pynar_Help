# Modül 13 
# HATA YAKALAMA VE İSTİSNALAR
## 13.1. Hata Kavramı

Kodları yazarken Python, birtakım hata mesajları verir. Bu hata mesajları programda yapılan söz dizimi
(syntax) hatalarının görülmesini sağlar. Programcılar her durumu düşünüp hataları önceden belirlemelidir. Hata mesajlarını kullanıcıların görmesi istenmediğinde Python, olası hata oluşumlarına karşı önlemler alınmasını sağlayan ifadeler sunar. 

## 13.2. Hata Yakalama
Beklenmedik durumlarda programın bir hata mesajı vermesi ve çalışmayı durdurması yerine, hataya
kullanıcının istediği şekilde cevap vermesini sağlamanın bir yolu olarak adlandırılmaktadır. Hata yakalama Python programlama dilinin önemli bir parçasıdır ve kaynak kodunu çok karışık hâle getirmeden
programınızın güvenilir bir şekilde çalışmasını sağlar.

Kullanıcıdan sayılar alan ve aldığı sayıların 2 katını ekrana yazan ve boş satır okuduğunda program
sonlandırılmasını sağlayan bir uygulama yapınız.


**Örnek 1**
```python
while True:
  x = input("Bir sayı girin: ")
  if not x:
    break
  print(float(x)*2)
  
>>> Bir sayı girin: 4
>>> 8.0
>>> Bir sayı girin: 3
>>> 6.0
>>> Bir sayı girin: ali
>>> Traceback (most recent call last):
      File "<ipython-input-89-66782bace4ab>", line 5, in <module>
        print(float(x)*2)
    ValueError: could not convert string to float: 'abc'
 ```

Örnek 1’de girilen “ali” ifadesi sayıya dönüştürülemediği için float() fonksiyonu bir ValueError hatası (Python terimiyle “exception”) verdi. Böyle hatalar programın çalışmasını durdurur. Oysa, bir hata
yakalama (exception handling) yapısı kullanılır ise bu tür sorunları programı durdurmadan halletmek
mümkün olmaktadır.

## 13.3. Hata Türleri

**1.** Programcı Hatası (Error)
**2.** Program Kusurları veya Mantık Hatası (Bug)
**3.** İstisnalar (Exception)

## 13.3.1. Programcı Hatası

Geliştiricilerden kaynaklanan bir hatadır. Programcının syntax yazım yanlışı vb. yaptığı hatalardır. Bu
hata giderilmeden program hiçbir şekilde çalışmaz. Bu tür hataların hangi satırda ve hangi kodlardan
dolayı yapıldığı bellidir. Bu yüzden fark edilmesi ve çözülmesi kolaydır.

**Örnek 2**

```python
print "Hata Ayıklama"

>>> File "<ipython-input-86-230c524677dc>", line 1
      print "Hata Ayıklama"
         ^
    SyntaxError: Missing parentheses in call to 'print'. Did you mean print("Hata
    Ayıklama")?
```


Örnek 2’de print kullanılmış parantez içine alınmadığı için kullanıcıdan kaynaklı SyntaxError hatası vermiştir. Eksik parantez var, diye mesaj verir.
Python’da sıklıkla karşılaşılan hataların bazıları aşağıda verilmiştir:


**a)** SyntaxError
**b)** ValueError
**c)** IndexError
**d)** ZeroDivisionError
**e)** NameError
**f)** IOError
**g)** TypeError
**h)** KeyError

Program hatası türünün fark edilmesi zordur. Sebebi ise program çalışır durumdadır herhangi bir hata
vermez. Ama istenilen sonuçtan farklı bir sonuç verir. Örnek 3’te kullanıcıdan karenin kenar uzunluğunu
alınır ve bu değere göre karenin alanını hesaplanır.

**Örnek 3**

```python
kenar = int(input("Kenarı Girin :"))
alan = 4*kenar
print("karenin alanı :",alan)

>>> Kenarı Girin :6
>>> karenin alanı : 24
```

## 13.3.2. İstisnalar (Exception)

Program bazı istisnalardan dolayı hata vermektedir. Bu tür hatalarda da program hata düzeltilmeden
çalışmaz. Örnek 4’te kullanıcıdan iki sayıyı alıp birinci sayıyı ikinci sayıya bölüp sonucu ekran yazdıran programa bakınız.

**Örnek 4**
```python
s1 = int(input("Birinci Sayı :"))
s2 = int(input("İkinci Sayı :"))
sonuc = s1/s2
print("Sonuc :",sonuc)

>>> Birinci Sayı :32
>>> İkinci Sayı :4
Sonuc : 8.0
Birinci Sayı :32
İkinci Sayı :0
Traceback (most recent call last):
 File "<ipython-input-98-62c9318aa9da>", line 4, in <module>
 sonuc = s1/s2
ZeroDivisionError: division by zero
```
 
Örnek 4’te birinci sayı sayı için 32 ikinci sayı için 4 değeri girilmiştir. Sonuç olarak 8 değeri yazılmıştır.
Uygulamayı tekrar çalıştırdığınızda birinci sayıya 32, ikinci sayıya ise 0 değeri verildiğinde ise herhangi bir sayının sıfıra bölümü tanımsız olduğu için hata mesajı verecektir.

## 13.4. Try-Except Blokları

Python programlama dili beklenilen veya beklenmeyen hataları ayıklamak için iki ana blok sunmaktadır.
Bunlar try ve except bloklarıdır.

## 13.4.1. Try

Bir blok içerisinde hata olması durumunda, Python except bloğuna atlar ve oradaki kodların çalıştırılmasını sağlar. Hata ile karşılaşılacak yerler blok içine alınan kısım olarak da bilinir.

## 13.4.2. Except

Try bloğunda herhangi bir hatanın olması durumunda burada yazılmış kodlar çalışır. Try bloğunda herhangi bir hata olmaması durumunda buradaki kodlar çalıştırılmayarak atlanır.
Örnek 4’teki uygulamayı try ve except blokları kullanarak yapmaya çalışınız. Örnek 5‘e bakıldığında
s1 değerine 5, s2 değerine ise 0 girilmiştir. Bir sayının sıfıra bölümü tanımsız olduğu için except bloğu çalışıp, ekrana Bir sayıyı sıfıra bölemezsiniz sıfır dışında bir sayı girin, diye mesaj yazmıştır.


**Örnek 5**

```python
S1 = int(input("Birinci Sayı :"))
S2 = int(input("İkinci Sayı :"))
 try:
 sonuc = s1/s2
 print("Sonuc :",sonuc)
except ZeroDivisionError:
 print("Bir sayıyı sıfıra bölemezsiniz lütfen sıfır dışında bir sayı girin")

>>> Birinci Sayı :5
>>> İkinci Sayı :0
>>> Bir sayıyı sıfıra bölemezsiniz lütfen sıfır dışında bir sayı girin
```

Örnek 6’da görüldüğü üzere sayıları sıfırdan farklı ve sadece sayı verilirse herhangi bir hata vermeyecek ve sadece try bloğu çalışacaktır. Ama sayılardan herhangi birine sıfır veya farklı veri türünde değer
girilmesi hâlinde except bloğu çalışıp bilgilendirme yapacaktır. Bu örnekte de ikinci sayıya “a” girildiği
için kullanıcıya lütfen sayısal bir karakter girin, diye mesaj yazacaktır. Except bloğuna hatanın türü yazılmadığında yorumlayıcı tarafından bütün hataları kapsayacaktır. Bunu da sadece except bloğu ile genel
olarak beklenmeyen bir hata oluştu, diye mesaj ile belirtilebilir.

**Örnek 6**

```python
try:
 s1 = int(input("Birinci Sayı :"))
 s2 = int(input("İkinci Sayı :"))
 sonuc = s1/s2
 print("Sonuc :",sonuc)
except ZeroDivisionError:
 print("Lütfen ikinci sayıya sıfırdan farklı bir değer girin…")
except ValueError:
 print('Lütfen sayısal bir karakter girin..')
except:
 print("Beklenmeyen bir hata oluştu")
 
>>> Birinci Sayı :20
>>> İkinci Sayı :a
>>> Lütfen sayısal bir karakter girin.
```

## 13.4.3. Try Except as

```python
try:
 s1 = int(input("Birinci Sayı :"))
 sonuc = s1**2
 print("Sonuc :",sonuc)
except ValueError as hata:
 print('Lütfen sayı giriniz')
 print(hata)

>>> Birinci Sayı :d
>>> Lütfen sayı giriniz
>>> invalid literal for int(  ) with base 10: 'd'
```
 
