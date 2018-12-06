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

namun yang perlu diperhatikan adalah mandatory harus mendefinisikan tipe data jika tidak ada inisialisasi data, contoh : 
```kotlin
var location; //error
location = "seputih banyak";
```
## Tipe Data
Tipe data biasanya digunakan untuk mengkategorikan kumpulan dari nilai yang saling terkait dan mendefenisikan operasi operasi yang bisa dilakukan terhadap variable.

Sama dengan bahasa pemrogrammannya lainnya, kotlin memiliki tipe yang sudah ada (predefine) seperti, Int, Double, Boolean, Char dan lainnya. Di dalam kotlin semua termasuk seperti Int dan Boolean adalah object, maka biasa terlihat di awal Huruf adalah capital.

Kotlin dapat mewakili beberapa tipe dasar seperti angka, karakter dan boolean sebagai nilai primitif pada saat runtime untuk meningkatkan kinerja, tetapi untuk end user, semuanya adalah objek.

Ini bertentangan dengan bahasa seperti Java yang memiliki tipe primitif terpisah seperti int, double, dan jenis wrapper yang sesuai seperti Integer, Double, dll.

berikut ini adalah tipe data dasar basic kotline, diataranya : 

### Number
Tipe data Numeric di kotlin sama dengan ada di java, dimana bisa dikategorikan untuk integer dan float.

### Integer
- Byte : 8 bit
- Short : 16 bit
- Int : 32 bit
- Long : 64 bit

contoh : 
```kotlin
// Kotlin Numeric Types Examples
val myByte: Byte = 10
val myShort: Short = 125

val myInt = 1000
val myLong = 1000L	// The suffix 'L' is used to specify a long value

val myFloat = 126.78f   // The suffix 'f' or 'F' represents a Float 
val myDouble = 325.49
```

dapat juga dipakai dengan disisipkan underscore dalam nilai tipe data numeric
```kotlin
val hundredThousand = 100_000
val oneMillion = 1_000_000
```
### Boolean
Seperti biasanya boolean akan merepresentasikan nilai logika, yaitu true dan false
