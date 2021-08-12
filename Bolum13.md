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
while True:
  x = input("Bir sayı girin: ")
  if not x:
    break
  print(float(x)*2)


```python
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

1. Programcı Hatası (Error)
2. Program Kusurları veya Mantık Hatası (Bug)
3. İstisnalar (Exception)
