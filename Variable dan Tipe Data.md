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
Bisa dikatan kelebihan atau kekurangan dari kotlin itu sendiri bahwa kotlin merupakan bahasa 'statcially type', namun kotlin juga dapat mengabaikan saat pendefinisian tipe data variable, contoh seperti berikut : 
```kotlin
var name = "arrizaqu"; //as String
var age = 17; //as Int
println("name "+ name + ", age : "+ age);
```

namun yang perlu diperhatikan adalah mandatory harus mendefinisikan tipe data jika tida inisialisasi data 

