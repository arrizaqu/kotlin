# Variable dan Tipe Data
## Variable
Sebuah variable akan mereferensikan ke dalam sebuah memori ketika data tersimpan, maka hal itu akan memiliki nama dan asosiasi terhadap tipe data, Tipe dari Variable akan mendefinisikan panjang nilai, dan operasi operasi yang dapat dilakukan terhadap nilai tersebut.

kita dapat mendeklarasikan sebuah variable dalam kotlin mengguanakan 'keyword' var dan val 

sebuah variable di deklarasikan dengan val jika variable tersebut bersebut immutable (tetep), hal ini mirip dengan java dengan hadirnya keyword final, dimana tidak akan bisa diubah setelah dinisialisasi nilai tertentu.
```kotlin
var negara = "NUSANTARA";
negara = "INDONESIA" // works.. 
```

## Type Inference
Bisa dikatan kelebihan atau kekurangan dari kotlin itu sendiri bahwa kotlin merupakan bahasa 'statcially type', namun kotlin juga dapat mengabaikan saat pendefinisian tipe data variable.

```kotlin
var name = "arrizaqu";
var age = 17;
println("name "+ name + ", age : "+ age);
```
