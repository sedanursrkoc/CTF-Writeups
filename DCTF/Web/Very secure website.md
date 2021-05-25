## Very secure website

![](https://i.ibb.co/1fh3hDb/secureweb1.png)

<br>

Soruda verilen linke gittiğimizde böyle bir sayfayla karşılaşıyoruz.

<br>

![](https://i.ibb.co/qMrmX3j/secureweb2.png)

<br>

Sitede belirtilen source code:

<br>

![](https://i.ibb.co/BLpyKqs/secureweb3.png)

<br>

Bu koddan username ve password için girdiğimiz değerlerin tiger128,4 göre hash’i koddaki hash’e eşit olduğunda flag’i elde edeceğimizi çıkartabiliriz.

<br>

https://md5hashing.net/search?q= burdan “51c3f5f5d8a8830bc5d8b7ebcb5717df” hash değerini arattığımızda “admin” değerinin hashlenmiş hali olduğunu buluyoruz.

<br>

![](https://i.ibb.co/GMG1qMx/secureweb4.png)

<br>

“0e132798983807237937411964085731” hash değerini ise ne kadar araştırdıysam da karşılığını bulamadım.

<br>

Php ile ilgili biraz araştırma yaptıktan sonra "Magic Hashes" kavramıyla karşılaştım. 
Magic Hashes `"0e"` ile başlayan hashlere deniyor ve bu hashler `‘==’` ile karşılaştırma yapıldığında true değeri dönüyor. 
Bunun nedeni ise php’de `"0e"` ile başlayan hash değerleri float oluyor ve `"0"` değerine eşit oluyor. 
Yani password hash değerinin karşılığını bulmaktansa `"0e"` ile başlayan bir tiger128,4 hash değeri bulmamız yeterli.

<br>

Daha fazlası için: https://github.com/spaze/hashes 

<br>

Bu soru için ise bu linkten yararlanıyoruz: https://github.com/spaze/hashes/blob/master/tiger128%2C4.md 

<br>

Burdan aldığımız herhangi bir değeri password kısmına yazıp username kısmına da önceden bulmuş olduğumuz admin değerini giriyoruz. 
Submit butonuna tıkladığımızda flag’i elde ediyoruz.

<br>

![](https://i.ibb.co/61Qnswt/secureweb5.png)


